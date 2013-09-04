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

* Savepoints (Like sub-transactions)
* Statements always run in a transactions
* Transactions are opened automatically
* Transactions are advanced technology.

Dreaded Error
=============

* Current Transaction is aborted, commands ignored until end of transaction block
* Means - A previous statement failed, the application must perform a rollback