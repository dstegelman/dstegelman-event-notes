===============
Advanced Celery
===============


**Presenter:** Ask Solem Hoel

**Track:** V

**Description:**

    This talk will delve deep into advanced aspects of the Celery task queue and ecosystem. Previous experience with task queues and message oriented middleware is beneficial.
    

    https://us.pycon.org/2012/schedule/presentation/81/
    
    

* Lead Celery developer
* Task Queue
* Tasks are just dictionaries
* Subtasking

Task Granularity
================

* Coarse-grained - More Computation
* Chunking can make very granular tasks good
* Chunks can use threads, reduce latency

Chords
======

* Synchronization Primitive
* Barrier
* Header is a taskset
* Body is applied with the results of the headers
* Native support for Redis and Memcached

Consider Subtasking
-------------------

::
    def smothing():
        subtask.delay()
    
Blocking 
========

* Bad
* Use timeouts and retry if possible to stalled tasks.
* Be smarter about routing.

::

    socket.settimeout()
    socket.setdefaulttimeout()

* Reroute tasks to machines/workers with free CPU


Cyme
====

* Cyme node is a branch
* No Master (Decentralized)
* Branches know neighbors
* API

API
---

* Create and manage
* Create worker instances
* Queues
* Configure workers


::

    pip install cyme
    
    cyme-branc -D 





