===========================
Django Deployment with Salt
===========================

**Presenter:** Nick Lang


**Description:**

Django deployment with Salt

Background
----------

* Developer at Lab 305
* Worked at Journal World

What is Salt
------------

* Config management in Python similar to Chef/Puppet
* Remote code execution
* Awesome!
* salt.readthedocs.org
* Good install docs

Master & Minion
===============

* Master server
* Minions ping masters for updates or can be pushed to by Master
* Has states
* Masters can also be minions
* Minion can be db server, app server, mail server, etc.

Master Configuration
====================

* Specify backends
* Point it at a Git Repo! FTW.
* Quick updates


Minion Config
=============

* Just connect to master
* Salt key to connect

Quick Dive into Config
----------------------

Salt State
==========

* Packages to install and versions
* Files
* Symlinks
* Databases
* Web Servers
* Fine grain control
* Create users/groups











