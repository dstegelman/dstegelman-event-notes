==========================================
The Dungeon Master's guide to Django's ORM
==========================================

**Presenter:** MALCOLM TREDINNICK

**Track:** II

**Description:**

    If you've ever been curious about Django's ORM implementation, you will have noticed the required learning curve. Some of the code is fairly complicated. Other bits are worse. Here comes a 30 or 40 minute guided tour of the uncharted realms: how the pieces fit together, where to look for things, why the current design is what it is. A portion of this is my fault; I should probably explain myself.
    
    
Me
--

* Python since 1997
* Django user since Sept 2005
* Django committer in May 2006

History
-------

* 12 July 2005, import from private svn repo
* Magic removal branch - 1 May 2006
* 3 Ways of structuring the ORM were attempted
* 4 July 2007 - Merge new ORM back in (Unicode)
* 2008 - 1.0

Worth It
--------

* Code structure has remained fairly stable
* Abstraction feels right
* Minor code duplication in recent times
* Mostly logical code flow.

Useful Rule
-----------

* Developers who were here before you where probably not insane.

Layers
------

* django/db/modles/query.py - 1800 lines
* django/db/models/sql/query.py - 2000 lines
* django/db/backends/* - base.py, operations.py

Down the Rabbit Hole
--------------------

* Simple filter query Article.objects.filter()

* db.models.query.QuerySet
* db.models.sql.query.Query
* db.models.sql.where.WhereNode
* db.models.sql.compiler.SQLCompailer

* Continually filter from previous filters.

Background
----------

* Nested queries
* QuerySets can be merged
* All aliases in a QuerySet can be changed at once.
