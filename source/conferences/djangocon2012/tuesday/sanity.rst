==============================================================
Maintaining Your Sanity While Maintaining Your Open Source App
==============================================================

**Presenter:** Mark Lavin

**Track:** I

**Description:**

    Django has a thriving community of open source pluggable applications. Maintaining an external application can be a rewarding experience and doesn't need to take over your life. Learn what it takes to package, document and test your Django app so that others can use and contribute to what you've built.



Brewedbyus.com

Packaging
---------

* Package to use PIP
* Direct users to use PIP first
* Setuptools find_packages

``` Include Package Data ```

* Pull description from ReadMe
* Follow PEP386
* 3 Numbers
* Be consistent in version numbers
* MANIFEST.in
* Register on Pypi!

Documentation
-------------

* No Giant READMEs
* Docs should be available online
* Use sphinx and Read the Docs

Things To Document
------------------

* How to install
* Description of the project
* How to configure the app
* Release Notes
* Be clear

Hosting Docs
------------

* Setup post commit hook
* Link to your repo

Testing
-------

* Tests should not fail without an example project
* Tests should not depend on small settings changes
* Test only models
* Run tests.py

Test with TOX
-------------

* User virtualenv to test
* Test different versions of python/django
* Test different DBs

Goals
-----

* State your goals
* Set expectations

License
-------

* Always include a License
* Prepare for the future

Be Ready for Python 3
---------------------

* 