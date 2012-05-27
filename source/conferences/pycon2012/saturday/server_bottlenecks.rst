=============================================
Web Server Bottlenecks And Performance Tuning
=============================================


**Presenter:** Graham Dumpleton

**Track:** V

**Description:**

    New Python web developers seem to love running benchmarks on WSGI servers. Reality is that they often have no idea what they are doing or what to look at. This talk will look at a range of factors which can influence the performance of your Python web application. This includes the impact of using threads vs processes, number of processors, memory available, the GIL and slow HTTP clients.

    https://us.pycon.org/2012/schedule/presentation/275/
    
    
Big Picture
===========

* Many moving parts in the whole system
* Main User grief is on teh front end. (Static, Network isues)
* 80% - 90% of the end user reponse time is spent on the front end.  Start There.
* Database/Application Server

Are Benchmarks Stupid
---------------------

* Little value
* People reference them, and they are often wrong
* Test only a single narrow use case.
* Hitting a site with extram load will only show you whtat i till likely fail under a denial of service attack.
* Should test corner cases, typical use cases

Environment
===========

* Memory
* Processors
* Threads
* Golbal Interpreter Lock

Client Impacts
--------------

* Slow HTTP Browsers/clients
* Need to handle static assets ( Don't use same server )

Use Cases
=========

* Memory USage
* Threads
* Long Running Requests
* HTTP Clients

Memory Usage
------------

* Web server base memory usage
* Web server per thrad memory usage
* Application base memory usage
* Loaded before forking?
* Adding more processes increases memory quicker.
* Issue is mainly about configuration
* Change and evaluate what your config is, don't just use the defaults.
* Number of overall threads, dictated by overall concurrent users.


Threads
-------

* More processes, more memory
* Find a balance
* If CPU is slow, more processes
* IO Wait

Long Running Request
--------------------

* Uploads
* Slow HTTP
* Large Response

Slow HTTP Clients
-----------------

* Proxy NGINX with Gunicorn
* Offload static
* Put Nginx in front of apache workers -> mod_wsgi dameons

Restarts
--------

* Restarts to fix issues
* Reloading of the application 
* Requests continue to backload
* Should do a full shut down if backlog cannot be cleared.

Pre load Everything
-------------------

* Load maximum processes into server at the begninng
* No auto scaling

Horizontal Scaling
------------------

* Use more servers

``If you treat your server like a black box you will never know what is going on.``

Tools
=====

* New Relic
* Sentry - Captures errors, but not performance problems

Conclusion
==========

* Don't trust server defaults
* Monitor live production systems
* Use benchmarks to explore a specific system, not to compare different systems.













