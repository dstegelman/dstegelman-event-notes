============================================================================
Certainty in an Uncertain World: Gaining Confidence through Security Testing
============================================================================

**Presenter:** Geremy Condra

**Track:** I

**Description:**

    Nobody thinks you have to be a performance expert to write performance tests- why assume that you have to be a security expert to write security tests? During this presentation I'll show you how to use fuzzers, attack tools, and other simple techniques to help protect your users, improve the strength of your existing tests, and gain confidence in the security of your code. There will be demos!

    https://us.pycon.org/2012/schedule/presentation/48/
    
Introduction
============

* User behavior
* Normal tests + adversary = security tests

Common Attacks
--------------

* Common Weakness Enumeration cwe.mitre.org/top25
* Protect against these

* OS Command Injection
* Cross Site Scripting
* Path Traversal


OS Command Injection
====================

::

    from commands import getoutput
    
    def list_directory(attacker_input):
        return getoutput("ls -la " + attacker_input)
        

* Avoid shell
* Sanitize
* FuzzDB http://code.google.com/p/FuzzDB

Cross Site Scripting
====================

* Inputing script straight into a page.
* Can't put client data straight into an html page
* Removing tags does not work.
* Sanitizing library, Bleach
* Problems with CMS's, blogs, etc.
* Django has built in escaping.


Directory Traversal
===================

A directory traversal (or path traversal) consists in exploiting insufficient security validation / sanitization of user-supplied input file names, so that characters representing "traverse to parent directory" are passed through to the file APIs.

The goal of this attack is to order an application to access a computer file that is not intended to be accessible.


Fixing
======

* Find attack tool
* Testing
* Integrate
* Fix
* Repeat 

What Doesn't Work
=================


* Finding really app specific bugs
* Large search spaces slow it down
* Hard to define problems
* Heavily analytic problems.

Wrap Up
=======

* Security testing isn't hard
* Can be very effective
* You don't have to be an expert








