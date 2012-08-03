==================
Testing and Django
==================


**Presenter:** Carl Meyer

**Track:** V

**Description:**

    A deep dive into writing tests with Django, covering Django's custom test-suite-runner and the testing utilities in Django, what all they actually do, how you should and shouldn't use them (and some you shouldn't use at all!). Also, guidelines for writing good tests (with or without Django), and my least favorite things about testing in Django (and how I'd like to fix them). 

    https://us.pycon.org/2012/schedule/presentation/412/
    
    github.com/carljm/django-testing-slides
    

* Tests are slow
* Not necessary to run some third party tests
* Django test discovery is broken
* unittest2 discovery
* Test_RUNNER setting (code example)

::

    """
    An alternative Django ``TEST_RUNNER`` which uses unittest2 test discovery from
    a base path specified in settings, rather than requiring all tests to be in
    ``tests`` module of an app.
    
    """
    from django.conf import settings
    from django.test import TestCase
    from django.test.simple import DjangoTestSuiteRunner, reorder_suite
    from django.utils.importlib import import_module
    from django.utils.unittest.loader import defaultTestLoader
    
    
    
    class DiscoveryDjangoTestSuiteRunner(DjangoTestSuiteRunner):
        """A test suite runner that uses unittest2 test discovery."""
        def build_suite(self, test_labels, extra_tests=None, **kwargs):
            suite = None
            discovery_root = settings.TEST_DISCOVERY_ROOT
    
            if test_labels:
                suite = defaultTestLoader.loadTestsFromNames(test_labels)
                # if single named module has no tests, do discovery within it
                if not suite.countTestCases() and len(test_labels) == 1:
                    suite = None
                    discovery_root = import_module(test_labels[0]).__path__[0]
    
            if suite is None:
                suite = defaultTestLoader.discover(
                    discovery_root,
                    top_level_dir=settings.BASE_PATH,
                    )
    
            if extra_tests:
                for test in extra_tests:
                    suite.addTest(test)
    
            return reorder_suite(suite, (TestCase,))


* unit test
* system/integration/functional tests
    
Unit Tests
==========

* Test one single piece of code
* Should be fast

Integeration Tests
==================

* Integration is slow, less usefull failures
* Database makes your tests slow
* Write tests that don't hit the database

Don't hit the DB
================

* Slow
* ``self.save()``

::

    def frobnicate_thing(thing):
      # ... do something complicated
      return thing
    
    
    class Thing(models.Model):
      def frobnicate(self):
        """Frobnicate and save the thing."""
        frobnicate_thing(self)
        self.save()
    
    
No to Fixtures
--------------

* Hard to maintain 
* Increase test interdependence
* Slow

Model Factories
---------------

::

    def create_profile(**kwargs):
        defaults = {
            "likes_cheese": True,
            "age": 32,
            "address": "3815 Brookside Dr",
        }
        defaults.update(kwargs)
        if "user" not in defaults:
            defaults["user"] = create_user()
        return Profile.objects.create(
            **defaults)


* Using

::

    def test_can_vote(self):
        """A user age 18+ can vote in the US."""
        profile = create_profile(age=18)
        self.assertTrue(profile.can_vote)
        
Factory Boy
-----------

::

    class ProfileFactory(factory.Factory):
        FACTORY_FOR = Profile
    
        likes_cheese = True
        age = 32
        address = "3815 Brookside Dr"
        user = factory.SubFactory(UserFactory)
    
    profile = ProfileFactory.create(
        age=18, user__username="carljm")

Why Use Factories
-----------------        

* Test data local to test code (explicit).
* Easy to maintain.
* Don't create any data you don't need for that test.
* Works great even for large/complex test data sets (helper functions).
* Mock Library


::

    from django.utils.unittest import TestCase
    
    import mock
    
    cursor_wrapper = mock.Mock()
    cursor_wrapper.side_effect = \
        RuntimeError("No touching the database!")
    
    
    @mock.patch(
        "django.db.backends.util.CursorWrapper",
        cursor_wrapper)
    class NoDBTestCase(TestCase):
        """Will blow up if you database."""
        
Views
=====

* Write less view code
* Use RequestFactory()
* Call the view callable directly

Web Test
--------

::

    url = "/case/edit/{0}".format(case.pk)
    form = self.app.get(url).forms["case-form"]
    form["steps-1-step"] = "Click link."
    form["steps-1-expected"] = "Account active."
    
    response = form.submit()
    
* Markup matters
* If it can break, it should be tested

::

    self.assertEqual(
       response.json, ["one", "two", "three"])
    
    self.assertEqual(
        resp.html.find("a", title="Login").href,
        "/login/"
        )
        
Selenium
========

* ``pip install selenium``
* Django 1.4

::

    from django.test import LiveServerTestCase
    from selenium.webdriver.firefox.webdriver import WebDriver
    
    class MySeleniumTests(LiveServerTestCase):
    
        @classmethod
        def setUpClass(cls):
            cls.selenium = WebDriver()
            super(MySeleniumTests, cls).setUpClass()
    
        @classmethod
        def tearDownClass(cls):
            super(MySeleniumTests, cls).tearDownClass()
            cls.selenium.quit()
    
        def test_login(self):
            self.selenium.get(
                "%s%s" % (self.live_server_url, "/login/"))
            username_input = self.selenium.find_element_by_name(
                "username")
            username_input.send_keys("myuser")
            password_input = self.selenium.find_element_by_name(
                "password")
            password_input.send_keys("secret")
            self.selenium.find_element_by_xpath(
                '//input[@value="Log in"]').click()


Other
-----

* Write system tests for your viwes
* Write selenium tests for ajax other js
* Write unit tests for everything else.
* Avoid multiple step tests

::

    @override_settings(ALLOW_COMMENTS=True)
    def test_comments_allowed(self):
      # ...