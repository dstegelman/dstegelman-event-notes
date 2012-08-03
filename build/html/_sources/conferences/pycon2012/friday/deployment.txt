================================
Practicing Continuous Deployment
================================


**Presenter:** David Cramer of Disqus.  Wrote Sentry.

**Track:** I

**Description:**

    Practice iterative development like the pros. Release sooner, faster, and more often.

    https://us.pycon.org/2012/schedule/presentation/12/
    
    
    
Workflow
========

* Continuous integration server runs test suites
* Fast rollback (Why not rollforward and fix)


Good
----
* Develop features incrementally
* Release frequently
* Smaller doses of QA
* Because manual tests are ``awful``


Bad
---

* Culture shock
* Statbility depends on test coverage
* Time investment

Keep Development Simple
=======================

* Automated testing is required.
* Simple can be better than complete
* Puppet, Chef, Buildout, Fabric
* ``Packaging your App`` as tag 1.0?

CI Server
---------

* Can be stripped down, don't need to test apache, nginx

Bootsrapping Local
------------------

* Git clone it
* Simple command to make everything work 
* Next step would be python manage.py runserver
* Need to test dependencies?  - Virtualbox + vagrant


Progressive Rollout
===================

* Actively release to smaller group before public
* Feature flipping (Gargoyle)
* Bump up features 
* Early adopters are free QA
* Sign up to get new stuff

Review All Commmits
===================

* Phabricator from facebook

Integration
===========

* Jenkins
* Painless setup
* Suppoer proper reporting - Coverage.py

Bad
---

* False positives
* Bad tests
* Services fail
* Feedback delay
* Integration tests vs Unit Tests

http://jenkins-ci.org/


Fixing False Positives
----------------------

* Rerun tets several times on a failure
* Report continually failing tests to dev

Maintain Coverage
-----------------

* Commit tests with code
* Utilize code review
* Coverage against a single diff.

Speed up Tests
--------------

* Write true unit tests
* Mock external services
* Distruted and parallel testing

Reporting
---------

* Rate of traffic (not just hits)
* Response time (database, web)
* Exceptions
* Social Media/Twitter

Sentry!
-------

Getting Started
---------------

* Package your app
* Value code review
* Ease deployment/fast rollbacks
* Setup automated Tests
* Gather some easy metrics
* Automate deploys
* Continueous deployment doesn't mean deploy all the time, it means deploy any time.
* Consider the ramifications of schema changes. DO NOT DROP columns 





















