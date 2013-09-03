========================
Performance Optimization
========================

**Presenter:** Joseph Jasinski

**Track:** II

**Description:**

	Your site is slow. But why is your site slow? There are a myriad of different problems that can cause this slowness. Drawn from real world experiences, this talk will help identify different problem areas and techniques for increasing performance. This involves both evaluating your performance on the backend and understand bottlenecks on the frontend.

Front End
---------

* Large and unoptimized payloads
* Static medai/images
* slow load of CSS
* Slow third party resources loading
* Blocking IO
* Chrome Tools
* External Analyizers (Google pagespeed insights)
* Browser Plugin
* Pingdom speed tools (DNS checker)
* Yslow browser plugin

Backend
-------

* SQL Quantities
* Blocking code
* Django Debug Toolbar
* Extending Django Debug toolbar (Cache panel & template timings)
* See what blocks take the longest
* Profiling middleware
* Get information on calls.

Improve Front End
-----------------

* Remove comments/whitespace
* HTML Minification
* Django-htmlmin
* Combine and compress css/js
* django compressor
* Compress images/Cache
* Image sprites/logos/icons

Resource Order
--------------

* Load first styles in critical path
* Place JS after other resources, ideally at the end of the file.
* Inline some CSS at the top.
* Lazy loading (Load images/assets only if the user gets there)

Assets CDNS
-----------

* Geographically serve assets
* Improve load time

Improve Backend
---------------

* SQL Queries
* Use "values_list"
* Verify same queries aren't running multiple times
* Select_related and prefetch_related

Select Related and Prefetch Related
--------------

* Get foreign keys
* If getting foreign keys use select_related
* Prefetch related can work for many to many queries

Cache
-----

* How should I cache?
* Memcache
* Use low level cache?

Low Level
---------

* Flexibility
* Reduce lookups
* get() set() delete() methods
* Flexibilty to develop your own cache scheme
* Template fragment cache
* Can accept context variables
* example (Get cache template for different users)

Per Site Cache
--------------

* Great for heavy read sites
* Not really approprate for immediate change sites
* Difficult to delete cache backend
* Google analytics can have issues

Cache Frameworks
----------------

* Johnny Cache
* Cache Machine
* ORM Model cacheing

CDNs
----

* Browsers support 6 connections per hostname
* More maximum connections
* Hashring with CDN domains
* Each domain is a seperate DNS lookup.
* Limit what you need to do inside of a request.
* Defer 

Job Queue
---------

* Process queues off line
* Requires more configuration

Server Level
------------

* Set expires header
* Cache control headers
* Gzip responses
