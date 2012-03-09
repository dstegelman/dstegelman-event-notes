=====================
Interfaces and Python
=====================

**Presenter:** Eric Snow

**Track:** IV

**Description:**

    In 2.6, Python introduced the Abstract Base Classes. Before that we had "protocols" (and we still do). In this talk we'll look at how the general concept of interfaces fits into today's Python. We'll also look at some of the alternate proposals of the past, some of the controversies around ABCs, and the direction interfaces might go in the future.

    https://us.pycon.org/2012/schedule/presentation/126/

    http://goo.gl/hwkTy


Object Interfaces
=================

* Code as documentation
* Adaption
* Static analysis

What is it
----------

* Communication
* Documentation
* Doc strings
* Comments
* Progromatic Interfaces

What is it in Python
--------------------

* Abstract base classes
* Protocols
* Build your own

Protocols
---------

* iterator
* context manager
* sequence
* descriptor
* No Validation is done to make sure they are following the protocol

EAFP vs LBYL
------------

``It's easier to ask forgiveness than permission``

Call it and worry about the failing later.

::

    # EAFP
    def is_dead(obj):
        try:
            obj("only a flesh wound")
        except TypeError:
            raise MyError("expected a callable object")



``Look before you leap``

Check a variable/method for something before you call it.

::

    # LBYL    
    def is_dead(obj):
        if not hasattr(obj, "__call__"):
            raise MyError("expected a callable object")
        obj("only a flesh wound")

Duck-typing
-----------

``polymorphism by capability`` vs ``polymorphism by type``

``Requiring a specific interface instead of a specific type.``


Abstract Base Classes
=====================

Write Your Own
--------------

::

    class Entree(metaclass=ABCMeta):
    
        @abstractmethod
        def with_spam(self):
            """spam spam spam spam"""
    
        @abstractproperty
        def spamcontent(self):
            """Lovely spam! Wonderful spam!"""
            
* Decorators make your methods Abstract.
* If a class has abstract methods then that class will be abstract.
* ABCMeta marks class as abstract


Use Existing
------------

* Register an existing class as an implementation 

::

    >>> class MyDict(Mapping): pass
    ... 
    
    >>> issubclass(MyDict, Mapping)
    True
    
    >>> isinstance(MyDict(), Mapping)
    True
    
    >>> MyDict.__bases__
    (<class 'collections.abc.Mapping'>,)
    
    








