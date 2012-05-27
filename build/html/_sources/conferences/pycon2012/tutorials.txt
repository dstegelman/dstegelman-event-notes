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
* These are references to other objects not actual objects themselves.
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

Exercise::

    locals().keys()
    globals().keys()
    locals() == globals()
    locals() is globals()

In this case locals() is globals()


Namespace Changes
-----------------

* assignment
* del
* (globals() and locals())
* import 
* def
* class

When you make an assignment you are just assigning a second name (alias) to the original function::

    from pprint import pprint as pprint_function
    
* __init__.py required for modules

Functions
---------

* You can add arbitrary attributes to functions
* Passing in a dictionary as an argument

::

    >>> def f(a1, a2, kw1='k1', kw2='k2'):
    ...     print(repr((a1, a2, kw1, kw2)))
    ... 
    >>> f(1)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: f() takes at least 2 arguments (1 given)
    >>> f(1, 2)
    (1, 2, 'k1', 'k2')
    >>> f(1, 2, 3)
    (1, 2, 3, 'k2')
    >>> t = 1, 2
    >>> t
    (1, 2)
    >>> d = dict(kw1=3, kw2=4)
    >>> d
    {'kw1': 3, 'kw2': 4}
    >>> f(*t)
    (1, 2, 'k1', 'k2')
    >>> f(**d)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: f() takes at least 2 non-keyword arguments (0 given)
    >>> f(1, 2, **d)
    (1, 2, 3, 4)
    
    
Another example::

    >>> name = 'Dad'
    >>> 'Hi {name}'.format(**locals())
    'Hi Dad'
    

Lists are Mutable, Strings are Not
----------------------------------


* Lists can be changed.  Strings create new objects.

Class Statement
---------------

* single ID
* Single value
* Number of attributes
* Single Type
* one or more namespaces
* One or more base classes


::

    ClassName()
    ClassName().__init__()
    
::

    Class Num(object):
        
        def __init__(self, amount):
            self.amount = amount
            
        def add(self, value):
            return self.amount + value
            
* You can add a method as an attribute of a class by simply assigning it.
* ``is`` comparison has been helpful 

::

    Class Prefixer(object):
    
        def __init__(self, prefix):
            self.prefix = prefix
    
        def prepend(self, listing):
            for l in listing:
                l = l + self.prefix
            
* Need to brush up on some basic python iterators, loops, etc.
* Metaclasses

Iterators
---------

* A for loop evaluates and expressiosn to get an iterable and then calls iter() to get an iterator.
* The iterators next() method is called until StopITeration is raised.

* Iterable items get the iter() method called.

::

    m = [1, 2, 3]
    it = iter(m)
    it.next()
    it.next()
    it.next()
    
    
Generators
----------

::

    def list123():
        yield 1
        yield 2
        yield 3
        
        
    it = list123()
    it.next()
    it.next()
    it.next()
    
* Look at next (David Beazley talk on Generators)

::

    import operator
    ops = {
        '+': operator.add,
        '-': operator.sub,
    }
    
    
    ops[op] (lhs, rhs)
    
    def calc(expr):
        lhs, op, rhs = expr
        lhs, rhs = int(lhs), int(rhs)
        return ops[op] (lhs, rhs)





    



