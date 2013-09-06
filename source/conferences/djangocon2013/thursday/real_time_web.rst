======================================
State of the real-time web with Django
======================================

**Presenter:** Aymeric Augustin

**Track:** I

**Description:**

	In 2013, "real-time" is more than a buzzword: it's a reality on the Web. Unfortunately, for users of Django, it's still a foreign world that involves new concepts and new components, and it doesn't integrate well with traditional infrastructure. What is the real-time web? Why is it hard to support in Django? What are our options today? What can we expect in the future?
	
	
State of the real-time web with Django
--------------------------------------

Real Time
=========

* Systems responding within deadlines
* Simulations running at wall clock time
* Processing events without perceivable delay
* Set of technologies and practices taht enable users to recive info as soon as its published, rather than refreshing.

Use Cases
=========

* chat
* games
* VOIP
* Notifications
* Live Data
* Social feeds
* PUSH information

Request - Response model doesn't allow for this.

Early Solutions
===============

* Java Applets
* Pushlets - call back from java apps into DHTML
* Comet - Long lived HTTP connections to reduce latency.

HTTP Long Polling
=================

* Server keeps request onhold and only send respond when an event to deliver
* As soon as client gets the response it sends another request

HTTP Streaming
==============

* Server sends a series of events ina single HTTP response
* Chunked
* Client processes each incoming event.

Server Sent Events
==================

* Built on top of HTTP Streaming
* Format text/event-stream
* Javascript API

Web Socket
==========

* Provides bidirectional communication in the context of the existing HTTP infrasturcutre
* RFC 6455
* Binary
* Socket.IO
* SockJS

Long Polling
============

* Locks up a gunicorn worker

Web Sockets

Execution Model
===============

* Based on an event loop
* Handle multiple socket connections in a single thread
* More efficient than one thread per connection
* Suitable for network prgoramming

Programming Model
=================

* Callbacks
* coroutines
* Based on explicit cooperative multi-threading
* In python: yeild (from)
* Suitable for concurrent applications

Pep 3156
========

* Pluggable event loop API
* Callbacks, transports, protocols
* High level scheduler based on coroutines
* REference implementation code-named Tulip
* Effort led by Guido

Django C10k Demo
================

https://github.com/aaugustin/django-c10k-demo



Django isn't async
==================

* @websocket

HTTP != real-time
=================

* Execution - threads vs events
* Programming preemptive vs cooperative
* Stateless vs stateful
* CPU vs I/O Bond
* Request-response vs message streaming

Key
===

* Django isn't designed for explicitly cooperative multi threading and its unlikely to change
* Robust client and server stacks are emerging
* Better best practices
* Simplified development setups
* Getting more useable.
