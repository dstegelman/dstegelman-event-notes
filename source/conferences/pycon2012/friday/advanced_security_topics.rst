========================
Advanced Security Topics
========================

**Presenter:** Paul McMillan - Django Security Developer

**Track:** II

**Description:**

    If your Python application has users, you should be worried about security. This talk will cover advanced material, highlighting common mistakes. Topics will include hashing and salts, timing attacks, serialization, and much more. Expect eye opening demos, and an urge to go fix your code right away.

    https://us.pycon.org/2012/schedule/presentation/467/


Hasing and Encryption
=====================

* MD5, SHA1, SHA256
* If you are typing md5 you are doing it wrong
* Did this file get corrupted?
* Use has for Message signing.
* It is hard to generate a file that duplicates your stored hash.
* Use HMAC for message signing.

::

    hash(secret + hash)

* Salt your secret key

::


    salt = 'session_cookie_signing'
    hmac.new(salt + secret_key, msg)

* When using has algorithims do not use MD5.
* SHA1 is better, but use SHA256
* Web could use SHA512 as its not 32 bit.

Why Need Encryption
-------------------

* Do not implement yourself.
* Use SSL/TLS

Random Numbers
==============

* Default random number is predictable.
* Use ``SystemRandom()`` instead


::

    from random import SystemRandom()


Timing attacks
==============

* String comparison does not compare the entire string at once.
* Not safe
* Compare the length first
* Compare different sets of characters, even if the previous ones worked.

Pickle
======

* Do not put data straight into pickle.
* Use JSON for untrusted data


Always verify your assumptions
==============================

* PIP installing.
* I trust django developers
* I truse the people who wrote pip
* PIP verifies MD5 hash

Am I Safe?
----------

* All these things require you to trust everyone on the internet
* You ``must`` verify
* Python doesn't make it easy to check SSL certs.
* Consider using Crate.io
