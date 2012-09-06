============================================
Accelerating and Enhancing Django with Redis
============================================

**Presenter:** JOSHUA "JAG" GINSBERG

**Track:** II

**Description:**

    This tutorial introduces Redis, an in-memory key-object NoSQL datastore. We discuss out-of-the-box ways Redis can help improve the performance of your Django deployments, ways that using Redis instead of SQL for some data management can accelerate your apps, and more advanced and unconventional uses for Redis to solve real-time and big-data problems.
    
What is Redis
-------------

* Absurdly Fast
* All in memory
* Keys and objects
* lists, strings, sets


What isn't redis
----------------

* Not NoSQL
* data structures limited and not nestable
* No views
* Not a simple key value store
* Not memcached


Crash Course
------------

* Get and Set right away
* Doesn't care about char encoding
* Linked lists
* Sets
* Scores, floating point values
* Dictionary keys not ordered

Boring
------

* Basically a cache
* Clearing house


Case Study
----------

* Run hundreds of ads on Facebook and snapshot their performance as fast as possible.
* Facebook API does not update stats in real time
* Gather stats and store as a hash map


Drop In
-------

* Celery
* Cache for Django
* Use Redis for celery instead of RabbitMQ

Give SQL A break
----------------

* Counting


Good Ideas
----------

* Use hierarchy
* Atomic transactions
* Different keyspaces for difference apps
* Do not store large values in Redis
* Do not count on persistence
* Don't forget that operations are Atomic

LUA - Lightweight Embeddable Scripting
--------------------------------------

* Construct and deconstruct JSON

