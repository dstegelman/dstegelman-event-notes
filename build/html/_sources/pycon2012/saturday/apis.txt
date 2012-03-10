==========================
RESTful APIs With Tastypie
==========================


**Presenter:** Daniel Lindsley

**Track:** I

**Description:**

    Providing full-featured REST APIs is an increasingly popular request. Tastypie allows you to easily implement a customizable REST API for your Python or Django applications.

    https://us.pycon.org/2012/schedule/presentation/61/
    
    
    
What is Tastypie
================

* REST framework for Django
* Designed for Extension
* Supports both Model and non Model Data
* tastypieapi.org


Philosophy
==========

* Make good use of HTTP
* Use REST methods/status codes properly
* Graceful Degradation (Backwards Compatable)
* Flexible everything
* Data can round trip (Anything you can GET you should be able to PUT and POST)
* Reasonable defaults - but easy to extend


HATEOAS
=======

* Hit API at the highest level and you should be able to explore it without documentation.
* Users shouldn't have to know anything in advance

Tastypie
========

* Builds on top of Django and plays nicely
* Full GET/POST/DELETE/PATCH
* Any data source (not just models)
* Designed to be extended
* Supports JSON, XML, etc.
* Well tested
* Lots of hooks
* Decent documentation

``References to the Install Docs http://django-tastypie.readthedocs.org/en/latest/index.html ``


* Going over resources, and API structure
* api, api/__init__.py, api/resources.py

Automatic
---------

* /api/v1/
* /api/v1/user/
* /api/v1/user/2/
* /api/v1/user/schema
* /api/v1/user/multiple/1;4;5/

Next
----

* Filter
* Leaking senstive info
* Auth

More
----

* Exclude
* Authentication
* Authorization
* Filtering
* Cache
* Throttling

Extensibility
=============

* Why classes - It makes it easy to extend
* Composition > inheritance
* Why so many methods - Hooks, Hooks, Hooks.
* Reasonable defaults, probably want JSON.
* Serialization
* Override or extend as you need.
* Resource has lots of methods, many of which are pretty granular

* Remove some formats

::

    serializer = Searizalier(formats=['json', 'xml'])
    
 
Fields
======

* Control how data gets prepared for presenetation
* Full control over the API/Schema
* Hydrate and dehydrate













