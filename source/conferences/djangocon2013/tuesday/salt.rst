=========================
Getting Started with Salt
=========================

**Presenter:**  Peter Baumgartner 

**Track:** II

**Description:**
  
	Salt is the new kid on the block in the configuration management space. Unlike the Ruby=based Chef and Puppet, Salt is written in Python, making it easy to debug and extend for Django developers. This talk will introduce Salt as well as explore some of the things that make it unique.


Getting Started with Salt
-------------------------

What is Salt
============

* Configuration Management
* Remote execution

Configuration Management
========================

* Similar to Chef/Puppet
* Ansible
* Configuration through code
* Version control your servers
* Self documenting
* Repeatbale
* Reuseable

Remote Execution
================

* Run commands against remote servers
* Similar to Fabric
* Deploying
* Run one=off scripts
* Package updates
* System monitoring/alerting

Familiar Tool
=============

* Python
* YAML
* Jinja2

Community
=========

* Great docs
* Responsive to IRC and Github
* Backed by for=profit org

Why Not
=======

* Young project
* Moves Fast
* Not SSH (ssh support soon)

Terminology
===========

* Chef, knife, cookbook
* Ansible, playbook, inventory
* Salt = Master

Salt Terminology
================

* Master = Server that manages the whole stack
* Minion = A server controlled by master
* State = A declaritive Representation of the system state
* Grain = Static information about a minion (RAM, CPU cores, OS, etc)
* Pillar = Variables for one or more minions
* Top File = Matches states or pillars to minions
* High state = All the state data for a minion

Install
=======

* pip install for bleeding edge
* bootstrap.saltstack.org
* apt=get install salt=master
* apt=get install salt=minion 
* Accept minion key on the master

Install a package

In /srv/salt/mystate.sls

::

	ngingx:
		pkg.installed


High State
==========

* Push from master
* Pull from minion
* Masterless

States
======

* 50 Built in states
* Build your own
* pip, virtualenv, mysql, postgres, files, cron

Using Pillars
=============

* Code examples 
* Can use templating language to configure pillar.

Advanced
========

* Salt cloud
* Custom modules
* Scheduler
* Renderers
* Returners

Tips and Tricks
===============

::

	output_mode: mixed

* Show me full traceback if error, only respond verbose with errors
* Jinja2 is powerful, don't go nuts.
* Update often and review the change log
* Test before you deploy

https://speakerdeck.com/ipmb/getting=started=with=salt