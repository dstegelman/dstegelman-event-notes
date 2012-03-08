=================
Python Epiphanies
=================

March 8 2012 

* Instructor - Stuart Williams

Introduction
============

* Static vs Dynamically typed language.
* Compiler must now ahead of time what type an object is
* In python you do not have to do that, because is not a static type language
* Type is checked at run time, not typed at compile time.  It is a dynamic language
* Compiler allocates memory.
* In python creates types and assigns names to them (not variables)

** These are references to other objects not actual objects themselves.
* Names are implemented like ditionaries


Dictionaries and Namespaces
===========================

Python Objects and Vars
-----------------------

* Things like a = 17 are essentially dictionaries.  These are added to ``object land``.
* Python object has
* Single value
* Single Type
* Some number of attributes
* Single ID
* Zero or one or more names in one or more namespaces
* One or more base classes
* When lists are appened IDs do not change, strings do.
* Can't set attributes of built in types.
* IDs match because there only needs to be one actual object in memory

Namespaces
----------

* _namespace['s] - Directly accessble namespace
* indirect, using dot notation dict.__doc__ or sys.version.major

Namespace Search Order
----------------------

* Local names
* Namespaces of encolsing function, search starting with the nearst closing scope

Excersise::

    locals().keys()
    globals().keys()
    locals() == globals()
    locals() is globals()

In this case locals() is globals()




