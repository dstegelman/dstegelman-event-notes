==========================================
Models and Migrations and Schemas - oh my!
==========================================

**Presenter:** ANDREW GODWIN

**Track:** I

**Description:**

    A look at the past, current and future of schemas, migrations and Django, and what it means for both website developers and ops staff.
    
Past
----

* Databases hate schema changes
* Locks whole tables
* Hammer I/O
* Inconsistent
* Django-evolution
* dmigrations
* South 0.1 2008
* 0.2 - MySQL
* 0.3 - Dependencies
* 0.4 - Alter columns
* 0.5 - ORM Freezing
* 0.6 - Field introspection
* 0.7 - data/schema split, missing defaults for Not null, custom fields ignored.

Things to Change
----------------

* No rebase/collapse
* Opaque migrations (Impossible to peek inside migrations)

Databases
---------

* Code/schemas split
* Database isn't going to use Git
* Extra fields are fine
* Missing fields are not
* Painful/slow to sync

The Future
----------

* django.db.backends.schema
* Database abstraction layer
* contrib.migrations
* Migration creation/running, will replace South for these operations.
* No frozen ORM
* Raw SQL support
* SQL Output support


South 1.0
---------

* Python 3 support with Django 1.5
* Python 2.6 required



