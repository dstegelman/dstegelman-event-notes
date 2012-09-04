===================
Views Can Be Classy
===================

**Presenter:** Kenneth Love

**Track:** II

**Description:**

    An overview of what class-based views (CBVs) are, which ones are available, and how to use them in your projects. I'll also cover creating mixins, where function-based views still make sense, and how to test CBVs. As part of this, I'll be covering my django-braces (https://crate.io/packages/django-braces/) package.


Who Am I
--------

* @kennethlove

Class Based Views
-----------------

* Bad right?

Bad
---

* Decorators must be wrapped around dispatch()
* Inheritance chains.  Not very obvious what is going on.
* Combining mixin and views creates order exceptions
* So much more going that you can't see.

MRO
---

* Two classes that inherit from the same base class, but has methods in different orders.
* Bit.ly/PythonMRO
* A little enterprise-ish



