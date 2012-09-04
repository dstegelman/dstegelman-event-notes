===============
API Design Tips
===============

**Presenter:** Daniel Lindsley

**Track:** I

**Description:**

    The focus of this talk will be on some pragmatic tips on how to design programmatic (non-web-based) APIs for use by other developers.

What
----

* Not HTTP APIs
* Programmatic APIs
* Libraries

Why
---

* Other people use your code all the time
* You might be not happy with past you.

You cannot make everyone happy
------------------------------

* You make assumptions about your environment
* These don't always apply for other people
* More people are happy if they can extend libraries
* No copy-paste should be needed
* Good docs matter
* Real world use is the best use.

Design
------

* Bottom up
* Top down
* Bottom up sucks
* Top down feels better
* Everything fits together
* Less duplication
* Test Driven Design

Things you Should Do
--------------------

* Small components
* Reflection (To and From)  Be able to reverse operate
* Narrow Familiarity - How similar is the code itself.
* Assume the worst
* Use it, then step back and ask yourself how to make it better, easier for the user
* Quick wins
* Return values should be consistent


Things you should NOT do
------------------------

* Low level API is good enough
* Wildly different return values
* If its diffcult to test, its probably wrong

Django Specific
---------------

* Pluggable backend all the things
* Declaritive syntax
* Avoid global state (Use __init__ )
* Decrease reliance on self
* Resist urge to use magic



