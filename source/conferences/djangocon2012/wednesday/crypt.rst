====================================
Cryptography for Django Applications
====================================

**Presenter:** ERIK LABIANCA

**Track:** II

**Description:**

    A review of encryption in the context of a web application storing sensitive information. Topics covered include choosing whether to use crypto, selection of tools, proper usage (including examples), and operational considerations with respect to security assessment.
    
    
Who
---

* Developer, Not cryptographer
* Should you trust me? Maybe.

TLDR
----

* Analyze risks
* Don't write your own
* Operate correctly
* Commit to keeping up

Hacks happen all the time
-------------------------


Analyze
-------

* Data
* Systems
* Identify Vulnerabilities (Backups, Laptops, Compromised systems)
* Analyze controls (Locked safe, Cryptography)

Hash Properties
---------------

* No Keys
* Easy to compute the has value
* Very hard to generate a message for a known hash value, modify without changing the hash.
* Used for signed cookie and sessions in Django
* Password verification

Symmetric Encryption Algorigthms
--------------------------------

* Secret Key
* Reversible
* Requires shared secret

Public Key Cryptography
-----------------------

* Asymmetric
* N-way
* 2 + keys