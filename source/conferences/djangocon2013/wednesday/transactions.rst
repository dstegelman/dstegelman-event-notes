===============================
Transactions for Web Developers
===============================

**Presenter:** Aymeric Augustin

**Track:** I

**Description:**

	Django has since long outgrown its roots in publishing. It's used in enterprise systems, under write-heavy workloads and strong data integrity requirements. But transaction management barely changed since the 0.9x days. Even veterans pull their hair out fighting DatabaseErrors when they use it. At last transaction handling will be overhauled in Django 1.6. How does the new system work, and why?
	
Transaction Management
----------------------

* SQL-92 standard
* A transaction is a sequence of SqL statements that is atomic with respect to recovery.
* All or nothing.
* Lifecycle (Transaction initiating statement -> commit, explicit rollback)

SQL-1999
========

* Save points (Like sub-transactions)
* Statements always run in a transactions
* Transactions are opened automatically
* Transactions are advanced technology.

Dreaded Error
=============

* Current Transaction is aborted, commands ignored until end of transaction block
* Means - A previous statement failed, the application must perform a rollback
* Recovery must be done in the application (Any auto-recovery scheme breaks transactional integrity)

Auto Commit
===========

* Commit implicitly after each statement.
* Wrap each statement in ints own transaction
* Just execute my query!
* Most databases default to auto commit.

Auto Commit in PostgreSQL
=========================

* Server always auto commit
* Client libs can emulate standard behavior
* in psql: \set autocommit off

Auto Commit in SQLite
=====================
* Transaction semantics are tightly related to the implementation of atomic commit
* Sqlite automatically starts a transaction before all statements except select
* It automatically commits such transactions as soon as all statements finish executing
* Transactions are always serializable

Python client libraries
=======================

* PEP 249
* Connection, performs commits and rollbacks
* Cursor, Executes queries, fetches results.
* Auto-commit should be initially off
* Interface should be provided to turn it back on
* Closing a connection without committing the changes first will cause an implicit rollback to be performed.

Transactions in psycopg2
========================

* Tracks transaction state
* Inserts a BEGIN before each statement unless there is already a transaction in progress
* Even before select statements
* Idle in transactions
* cnx.autocommit = True disables this behavior.

Transactions in SQLite
======================

* Track state
* Parses statements to insert BEGIN or COMMIT
* SELECT:COMMIT, INSERT, UPDATE, DELETE, REPLACE: Begin
* Any other statement uses COMMIT
* Broken by design

Key Learnings
=============

* DB API requires the same transactional behavior as the SQL standard
* Client libraries for Databases that always auto commit have to emulate this behavior
* You can turn it off

Django <= 1.5
=============

* Django runs with an open transaction
* Django auto-commits in save(), delete(), update(), and bulk_create()

Transaction middleware
======================

* One HTTP request = one transaction. Commit on success, roll back on exception.
* High level apis transaction.autocommit() transaction.commit_on_success()

Behind the Scenes
=================

* Django maintains a stack of transaction management states
* Auto: the ORM commits every change
* Managed: Django doesn't commit
* Django maintains a "dirty" flag: set automatically by the ORM after writes, must be set manually after raw SQL queries.
* Nesting doesn't work well

Default Django 1.6
==================

* Database-level auto commit
* ATOMIC_REQUESTS
* ATOMIC can be used as decorator or as context manager
* commit on success, roll back on exceptions
* Guarantees atomicity.
* Low level API to implement your own transaction management

Key Learnings
=============

* If you don't understand transactions read the docs in django 1.6
* ATOMIC_REQUESTS is still a reasonable idea
* Use the atomic decorator when you need aotmicity.