============================
Selenium Testing with Django
============================

Quick Start
-----------

Install python selenium::

    pip install selenium
    
Create a new Test case::

    from django.test import LiveServerTestCase
    from selenium import webdriver
    from selenium.webdriver.support.ui import Select
    import time
    
    class SomethingAppTest(LiveServerTestCase):
        fixtures = ['groups.json']
    
        def setUp(self):
            self.browser = webdriver.Firefox()
            # Use factories to create objects
            
        def tearDown(self):
            self.browser.quit()
            
        def test_mentor_login_no_mentor(self):
            
            self.browser.get(self.live_server_url)
            self.browser.find_element_by_id('clickme').click()
    
    
Testing Tid Bits
----------------

* It's a good idea to prime your test cases with data.  Either prime the test case with a fixture or better yet, an object factory.