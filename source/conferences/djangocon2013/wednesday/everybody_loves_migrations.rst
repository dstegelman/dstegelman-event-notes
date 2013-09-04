==========================
Everybody Loves Migrations
==========================

**Presenter:** Andrew Godwin

**Track:** II

**Description:**

	Times are changing - schema migrations are finding their way into core Django and becoming quite different in the process. Come and learn what's happening, why it's being done this way, and how you can best start using them.
	
	
Migrations
----------	

Why is it so hard
=================

* Versioning not easy in Dbs
* hard to roll back
* every change has a side effect
* Difference databases (Mysql, Postgres, etc.)
* Not necessarily up front.

South
=====

* Released 2008
* Most popular solution
* Not without issues
* 6 or 7 year old design

Basic Layout
============

* schemamigration (have to always add --auto)
* datamigration
* migrate apply only migrations
* syncdb
* complex and evolved design

Issues
======

* Migrations build up over time
* VCS merges suck OUCH
* That file format

django.db.migrations
--------------------

* 5 years in the making. 

Design Goals
============

* Clean migrations - Readable diffs are really important.
* Squashable migrations - No need for those hundreds of old ones.
* Better merge protection 
* Better commands --auto is pointless
* Automatic dependencies - stops silent errors
* Reuseable schema API - There are valid reasons to change tables
* Third-party compatability

Migrations
----------

* Make migrations
* migrate - Applies migrations and legacy collection.  Syncdb removed
* Autodetector - Makes new migrations
* Executor - Plans and runs migrations

Better Format
-------------

* Compound history
* Stores history as statements in a list
* Series of Operations
