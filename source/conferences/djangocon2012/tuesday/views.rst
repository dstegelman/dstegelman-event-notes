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

Why Use CBV
-----------

* Faster implementation
* Keep views.py concise
* Everything is a class (Models, Forms, Templates)
* Special cases are not special enough to break the rules, Views should be classes too.

Batteries Included

Object Based Views
------------------

* Single object
* Multitple object mixins
* Detail/List View

Form Based Views
----------------

* Form View
* Create View
* Update View

Date based Views
----------------

* Year
* Month
* Day
* Date

Utility Views
-------------

* Template Response
* Template View
* Redirect
* View

Common Methods
--------------

* Dispatch, (Get, Post, Put, Delete)
* get_context_data
* get_object
* get_queryset
* get_form_class
* get_form_kwargs
* get_success_url
* form_valid
* Demo
* Add base classes for common functionality in views.  Convert them into Mixins.

Customizing
-----------

* context_object_name










