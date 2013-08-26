================
Django on Gevent
================

**Presenter:** Cody Soyland

**Track:** II

**Description:**

    This is an introduction to using the Gevent networking library to empower your Django application with realtime features and resource-efficient cooperative concurrency. Django's synchronous APIs make it impractical to use in a callback-based networking library, but fast single-threaded concurrency is still possible using the mind-blowing capabilities of coroutines.


Real Time Web
-------------

* Delivery of information as it happens
* Open connections
* C10K Problem 0 How do web servers handle thousands of connections at once

New Challenges
--------------

* Non blocking I/O
* Low resource overhead
* Distributed


Concurrent Systems
------------------

* Processes
* Threads
* Callbacks
* Coroutines

Threads
-------

* Memory Overhead
* Readable, synchronous interface
* Guaranteed cooperation

Callbacks
---------

* Call stack not preserved
* Simple things are intuitive
* Complex things become confusing

Coroutines
----------

* Call stack preserved
* Synchronous API
* Benefits of threads without the non-determinism

Greenlet
--------

* True coroutines in Python
* Expands upon greenlet to provide "green threads"
* Provides an event loop


Green Threads
-------------

* POSIX threads are pre-emptive
* Green threads are cooperative
* Very light weight
