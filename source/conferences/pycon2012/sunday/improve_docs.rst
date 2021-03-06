===============================================================================
Improving Documentation with "Beginner's Mind" (or: Fixing the Django Tutorial)
===============================================================================


**Presenter:** Karen Rustad

**Track:** III

**Description:**

    This talk evaluates a well-known free software tutorial (the official Django tutorial) from the perspective of a web development novice in order to point out omissions and common sticking points and suggest improvements. More generally, this talk is useful to anyone looking to improve their project's tutorials and other newcomer-targeted documentation by approaching them with "beginner's mind".

    https://us.pycon.org/2012/schedule/presentation/422/
    
    
Documentation Six Audiences and Purposes
========================================

* First contact ( new users )
* Education ( New )
* Support ( Experienced )
* Troubleshooting
* Internals
* Reference 

Documentation for New Users
===========================


Most Important docs
-------------------

* Install/setup
* Tuts

What Makes a Good Tut
---------------------

* Advertises what is cool or unique
* Enjoyable - not too long
* Consistently likely to succeed, (platform agnostic, testing)
* Prepares the reader for using it on their own
* These Goals can conflict

``New users use tutorials as a scaffold for building whatever they wanted to build using your project.``

Hypothetical Tutorial Using Persona
===================================


Kira
----

* CS Undergrad
* Familiar with python
* New to web dev

Kevin
-----

* Designer
* Knows basic

Django Tutorial Runthrough
==========================

* Installation should come first.
* Bad installation hygiene
* Django doesn't lead users to isolate using virtualenv.
* How do I debug?
* Where to find help?
* Projects vs Apps , what is the difference?
* Idea of code reuse.
* No real discussion of test-driven development
* What is tests.py used for?
* Schema migrations - no talk of South
* How to style forms
* Static and Media files - not explained in the tutorial
* Template inheritance
* Deployment


Target Audience Chnage
----------------------

* Build a community or a library
* If you want a long running project and a community you'll need longer, more complete tutorial
* Example: Railsbridge, PyStar.org
* Comprehensive tutorials are longer, takes more time.
* Modular structure can make this easier
* Blind searching is hard, put linke in your docs instead
* Better doc, "Intro to web programming using Django"


Issues
======

* Assuming familiarity with base
* Unstated assumptions
* List of directions withou why
* Code samples
* No obvious place for help

Better Docs
-----------

* Remember you were a novice once
* Realize your own expertise
* Have a user test your docs
* Announce audience
* Explicit Dependencies
* Different tutorials for different audiences










