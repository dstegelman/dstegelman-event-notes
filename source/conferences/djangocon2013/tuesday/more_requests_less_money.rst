========================
More Requests Less Money
========================

**Presenter:** Nick Catalano

**Track:** I

**Description:**

	Hear how in under 2 weeks Ain't it Cool News, a movie news and review website with over 15 years of raw HTML content and hundreds of thousands of daily visits, was moved from an expensive custom Ruby on Rails App on an EC2 cluster to a dedicated server running Django. All with zero downtime.


More Requests Less Money
------------------------

History
=======

* Old, Old, HTML
* Perl, Drupal, Rails 

Problem
=======

* Ads were gradually going down.
* AWS bills were growing
* Active scaling horizontally
* Had to pay licensing fees for using software

Realizations
============

* Can't offer commenting as well as Disqus
* OK if articles dont' appear right way for entire world as long as it eventually shows up
* A little down time is manageable

Solution
========

* Managed dedicated server behind Amazon cloudfront
* Use disqus

Arch
====

* Old arch, multiple high=cpu medium instances, extra large RDS instance
* Over 3000/month

New Arch
========

* Dedicated server, 16gb RAM, mysql, SSD, Apache Modwsgi
* Cloud instances for forums and domains redirects
* Disqus
* Additional cloud instances
* Managed operations services
* 1325/month

Migrating Content
=================

* 60000 raw html articles
* 4.5 million non spam comments
* SQL dump and public facing templates only way to get content

Inspect DB
==========

* Based on SQL dump
* set production DB as secondary DB
* Rebuilt the site using view source files and simple django views

Migration
=========

* Left talkbacks alone 
* Built a management command to migrate articles from secondary database first
* Get or create runs without duplicate data on both machines
* Management command also stripped out html to generate meta tags
* Find and replace for image URLs and handling weird unicode in DB
* Simple cleanup with beautiful soup

Cloud Front
===========

* HTTP POST is not supported
* Do pay for requests
* Bring your own analytics
* No full site purge
* Do not assume every cloudfront request will have a cloudfront user agent.
* Cloudfront will not continue to serve your site indefinitely if your origin goes down.

Scaling Up
==========

* Scaled from 10,000 visits/hour to 90,000 visits/hour.  No downtime


http://bit.ly/aicndjangocon

