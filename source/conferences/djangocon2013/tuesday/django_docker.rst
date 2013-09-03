=============
Django Docker
=============

**Presenter:** Ken Cochrane

**Track:** I

**Description:**

	Django and Docker: A marriage made in heaven
	
	
Who
---

* Corporate Sponsor of Docker (Dot cloud)

Survey
------

* 80% heard of docker

Where did Docker Come From
--------------------------

* Docker is a rewrite of similar code that powers DotCloud
* Original version in Python, new version in GO
* Very Young project

Timeline

* Jan 2013 internal project
* March PyCon talk
* Released March 27
* June add OpenStack comptatibility
* 5300 Github stars
* 125 Contributers


What Is Docker
--------------

* Docker is an OSS engine that automates deployment of containers
* Linux containers
* Control groups and Namespaces
* AUFS (file system)

Linux Containers
----------------

* Mini VMs
* Stacked on top of another LInux system
* Like a vm but very light weight

Why Containers
--------------

* boot in seconds
* 1000s of containers on single machine
* Containers all use same host OS
* Share bin/libs
* No guest OS.
* Layered approach for file system
* Build on top (diffs)

Install Docker
--------------

* Linux kernel 3.8 or above
* AUFS
* LXC
* 64 Bit
* (Ubuntu 13.04)
* Vagrant
* Docker APT repo

Vagrant
-------

* Clone and vagrant up

Binary Install
--------------

* Manage upgrades yourself
* Need to install system startup script.
* 5 easy steps for Digital ocean

Digital Ocean Install
---------------------

* Docker install in one step for Digital Ocean (Official docker image)
* 10$ free credit DJANGOCON2013 tinyurl.com/docker10

Use Cases
---------

* Local Dev environment
* Deployment
* Unit Testing
* Parallelize tests
* one DB per test


Unit Testing
------------

* Containers to isolate tests
* No more worrying about tests not cleaning up
* Parallelize the tests across multiple machines

System Tests
------------

* Easily create all the diff system configs to test against
* No need to worry about breaking or rebuilding a test server
* Test fabric scripts
* Agileq.com/blog/

Continuous Integration
----------------------

* run tests after each commit
* StriderCD.com open source CI server
* Travis CI also playing with Docker

Deployment
----------

* Dokku
* flynn.io
* deis.io
* chef, puppet, salt, ansible, etc.

Dokku
-----

* Open source
* Docker powered mini-heroku
* less than 100 lines of bash
* Heroku build packs
* git push deployment

Flynn.io

* Open source PASS written in Go

Deis.io
-------

* Python
* Git push
* Docker images, chef recipes
* Scaling


Other Projects
--------------

* Chef-docker
* chef-cookbook
* Salt stack
* Ansible

Local Dev
---------

* VMS heavy, containers not so much
* RUn 100s of containers on laptop
* Easy to duplicate prod environment if you have a complex setup


Projects using Docker
---------------------

* Node.js module testing
* Plone/jiffylab - web based enviroment for instruction
* Kitchen-docker - Run unit tests in isolated environment
* npmt.abru.pt - Auto testing all NPM modules, one container per module and destroyed when finished.
* memcached SAAS - Memcached SASS built on Docker
* Try out Rethink DB, containers killed in 24 hrs.  1000s of containers on one host
* Open-stack-docker, deploy to linux containers instead of VMs


Use Docker
----------

* Container: linux container
* Image: snapshot
* index: public docker image directory
* Dockerfile: auotmated script used to create an image
* push/pull : commands to get images and push them
* Run: start a docker image to run
* Docker run (start image with commands)

DockerFile
----------

* Simple scripting language
* Automate creation of images
* built in cache
* Add them to any project repo to dockerize the project
* Online tut - docker.io/learn/dockerfile

Docker Index
------------

* Similar to Pypi but for docker images
* Written in Django
* Public directory to store and download re-useable images
* Docker image meta data
* Account required to publish images
* index.docker.io

Docker Registry
---------------

* Open source python flask app
* Manages the storages of the images
* Install private registry for private images

Docker API
 ---------
 
* rest API
* Docker CLI uses the same API
* Clients for most languages
* Docker clients (docker-py)
* Docker UI (Shipyard) Docker UI (angular.js) Dockland Ruby

Demo (https://github.com/kencochrane/django-docker)


