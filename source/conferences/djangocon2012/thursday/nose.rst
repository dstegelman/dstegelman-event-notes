===========
Django Nose
===========

**Presenter:** ERIK ROSE

**Track:** II

**Description:**

    Django's testrunner gets you started quickly, but you soon hit your head on its limitations as your project grows. By trading it for nose, a testing framework popular in the wider Python community, we can reduce boilerplate, boost performance, and improve testing UI, with only a few lines of setting changes. Re-use your test DBs, integrate with Jenkins, split your suite into pieces, and more.
    
Django Tests Pain
-----------------

* Crowded
* Slow
* Overbroad
* Rough
* Extensible but not scalably so

Installation
------------

* pip install django-nose
* django_nose
* django_nose.NoseTestSuiteRunner

Discovery
---------

* Find test by reg ex
* @istest
* Subclasses of TestCase
* No more accidental shadowing
* No more forgotten imports


Functions as tests
------------------

* Package level setup and tear down


Test Generators
---------------

* 