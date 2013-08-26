========================
Django Class Based Views
========================

**Presenter:** Nick Lang


**Description:**

Class Based Views

Background
----------

* Developer at Lab 305
* Worked at Journal World

Overview
--------

* Class version of generic function views.
* Base, Dates, Detail, Edit, List
* CRUD Views
* Subclassed (Mixins)

Mixins
------

Object with methods that can be overridden to customize behavior.

* ContentMixin
* TemplateResponseMixin (Adds context variables)
* Date Views, Many.

Detail Views
------------

* Single object
* Primary key or slug

Mixins
------

* SingleObjectMixin
* SingleObjectTemplateResponsemixin

Crud Views
----------

* Create/Read/Update/Delete
* Form View/CreateView/UpdateView/DeleteView

Mixins
======

* FormMixin
* MomdelFormMixin

List view
---------

* Mixins - MultipleObjectMixin


Base View
---------

* ContentMixin and TemplateView
* Nav item names

Why
---

* Custom mixins
* Elegance
* can push constants to the template by declaring class properties
* Lots of possibilities for mixins.
* Django Braces











