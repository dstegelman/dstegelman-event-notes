===============================
Decorators and Context Managers
===============================


**Presenter:** Dave Brondsema

**Track:** IV

**Description:**

    Learn how decorators and context managers work, see several popular examples, and get a brief intro to writing your own. Decorators wrap your functions to easily add more functionality. Context managers use the 'with' statement to make indented blocks magical. Both are very powerful parts of the python language; come learn how to use them in your code.

    https://us.pycon.org/2012/schedule/presentation/131/
    
Decorators
==========

* Pass functions to other functions
* Example

::

    @property
    
Instead of 

::
    
    var = property(method)
    
::

    def expose(func):
        func.exposed = True
        return func
        
* Do this:

::

    @expose("template.html")
    
::

    def expose(template):
        def mark_exposed(func):
            return func
    return mark_exposed
    
    
* Decorators replace the original function in memory.
* Decorator for decorators
* Allows you to not nest methods
* Classes can be decorators
* Decorators can be placed on classes
* @classmethod decorator - 
* Restrict.post or something

::

    pip install decorator
    
    
Context Managers
================

* __enter__ and __exit__ methods
* @contextlib.contextmanager
* contextlib


http://speakerdeck.com/u/brondsem















