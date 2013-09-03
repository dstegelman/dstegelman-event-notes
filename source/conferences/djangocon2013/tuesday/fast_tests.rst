================================================
Writing Fast and Efficient Unit Tests For Django
================================================

**Presenter:** Casey Kinsey

**Track:** I

**Description:**

	Many developers have difficulty finding clear guidelines and best practices for how to test efficiently, leading to a flimsy, slow, and ineffective test suite. This talk will cover some basic (but oft overlooked) principles of unit and integration testing, and dive into more advanced topics such as testing with read only data and using Mock ultra-focused and fast testing.
	
	
Writing Faster Tests
--------------------
	
A real need for test speed
==========================

* Made an initial production release of a real product for a national media company
* Test Coverage not great
* Started seeing regressions
* Aggressively pursue greater test coverage
* Results were successful, but needed faster tests.

Should I be concerned?
======================

* You probably have lots of tests
* You probably run them frequently
* Slow tests will cause developers to stop running them
* Preparing code for integration becomes painful
* Deployment speed is directly affected

How to write better tests
=========================

* Many project suites are comprised of integration tests
* Write unit tests
* Unit test calls a small "unit" of code
* Integration tests, test the contracts between the units
* Using the django test client is a giveaway that its an integration test.
* Write unit tests that are very limited in functionality/scope

Unit Vs Integration
===================

* For each function that contains business logic, there should be a unit test
* for each page/view/user path of your project there should exist an integration test.
* Setup tests

Set up tests cautiously
=======================

* Be judicious about how you use setUp/tearDown
* Think like middleware.  Do I really need this for every test in this case?
* One inefficient computation can cripple the whole test case.
* Add @classmethod.  very effective for read only data.  Data will persist between tests!

The Database is Hot Lava
========================

* If you touch it, you will die
* Not really, but its one of the slowest things your application will do in a unit test.
* Work with read only, non persisted data.
* Use in memory model instances

::

	model = ModelName(attribute=x)
	
* Avoid fixtures
* Fixtures don't adapt
* Schema changes will result in failures

Fake it Till You Make It With Mock
==================================

* Library that lets you create stub objects
* Configure behavior for testing
* Use mock to emulate model instances
* No model/ORM overhead
* Use mock.patch to focus your tests
* Patch sys.modules with your own module
* Use mock in more complex situations
* Track the way objects are used - test assertions, know which attributes that have been called and can report on it.


