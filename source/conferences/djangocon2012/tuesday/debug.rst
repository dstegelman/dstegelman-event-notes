======================================
Debugging Live Python Web Applications
======================================

**Presenter:** Amjith Ramanujam

**Track:** II

**Description:**

    Monitoring tools record the result of what happened to your web application when a problem arises, but for some classes of problems, monitoring systems are only a starting point. Sometimes it is necessary to take more intrusive steps to plan for the unexpected by embedding mechanisms that will allow you to interact with a live deployed web application and extract even more detailed information.


Why Debug?
----------


* Obvious - Python exceptions
* Subtle - Memory leaks
* Performance - Slowness
* Heisen - Only shows up in production.
* Devops - Says no to debugging in production

Things to Avoid
---------------

* Do not do more damage
** Crashing the site
** Loss of customer data

Manage Risk
-----------

* Use software that restricts what you can do.
* Script changes
* Test what you are going to do first
* Develop contingency plans

Monitoring
==========

Passive
--------

* Collection of log info
* Collection of Python exceptions
* Collection of performance data from hosts
* Logstash
* graylog2
* Sentry and New Relic

Server Monitoring
-----------------

* Monit
* Munin
* Cacti
* Nagios
* New Relic

Application Performance Monitoring
----------------------------------

* New Relic

Web Page Performance
--------------------

* YSlow
* GooglePageSpeed
* WebPageTest
* Firebug


