=================
Lesson on Testing
=================

**Presenter:** David Cramer

**Track:** II

**Description:**

    Learn from failures (and successes) around testing patterns and culture in a growing company, both in amount of code, and number of engineers. We'll dive into how DISQUS adopted testing, and the many challenges we've had to overcome.
    
 

Time Consuming to Write
-----------------------

 * Takes long time to write good tests
 * 10 lines of code has 36 lines of tests
 * 50% of time is spent writing tests
 * Legacy code is expensive to test
 * Spend more time running them, hardware is cheap.
 
 
 * Lots of Demos
 
 Mocking is Fragile
 ------------------
 
 * If path changes, mock fails
 * Tests break a lot on code changes
 * Mock is useful for testing external services
 
 
 Assume APIs don't change
 ------------------------
 
 * Test the lifecycle of requests
 
 Selenium
 --------
 
 * Kind of works
 * Brittle
 * Use Phantom JS for js tests
 
 Don't Admit Defeat
 ------------------
 
 * Start with a Goal
 * Write testable Code
 * Break up code
 * Create Structure
 * Put tests in the top level directory
 * Document best practices
 * Continuous builds
 * Tests should be a part of your culture
 * Code Review
 * Test throughout the process
 * Nose (nose.readthedocs.org)
 
 Sentry
 ------
 
 * Tests aren't enough
 * Deep trace
 
 Phabricator
 -----------
 
 