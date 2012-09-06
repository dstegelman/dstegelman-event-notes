================
Django Core Team
================

**Presenter:** Djanog Core

**Track:** I
    
Django Core
===========

What is a potential plan or way forward for Django to move forward in Real Time
-------------------------------------------------------------------------------

- Not confident about time (1 or 10 years)
- Web is going toward "Thick Clients" (Phone Apps)
- Adapt or Die
- Django must move forward but not sure about timeline

What is happening on the Schema change API
------------------------------------------

* South is the defacto solution for migrations
* Adding south abstractions in to 1.5
* Time to start rolling migrations into Django

Python 3 - Strategies and Tips for Migration
--------------------------------------------

* Not hard
* Django has documented how they approached the change
* Confident that 3rd party apps will be able to convert it easily.


New Areas of Interest for new dev
---------------------------------

* Real time
* Performance
* 2.0 game plan

How do you break contrib out and still maintain them (namespaces)
-----------------------------------------------------------------

* Support for better namespacing in Python 3.3
* In practice cannot use name spaced packages

What would be the thing that you think you could actually change in 2.0
-----------------------------------------------------------------------

* Everything is a view.

ORM is agnositc, should it be broken to allow performance improvements in Postgres
----------------------------------------------------------------------------------

* There should be more support for performance improvements in certain DB Backends
* 1.5 1.6 might have some improvements

Admin Radical restart?
----------------------

* Backend could serve an API and allow clients to provide better admin functionality
* Very challenging project
* Very large task
* A lot of the admin does not use django tools that exist now
* Admin does not use Class based views


Will a team approach to design help django?
-------------------------------------------

* Designers work best not solo
* Motivate each other
* Unified vision



