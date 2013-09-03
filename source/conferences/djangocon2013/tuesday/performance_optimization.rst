=======
Performance Optimization
=======

**Presenter:** Russell Keith MaGee

**Track:** II

**Description:**

    
Finding Probelms


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