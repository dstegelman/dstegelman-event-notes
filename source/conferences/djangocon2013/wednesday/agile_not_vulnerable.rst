====================
Agile Not Vulnerable
====================

**Presenter:** Jacob Kaplan-Moss

**Track:** I

**Description:**

	Startups like to "move fast and break things"… but how do you ensure that what breaks isn't security? How do you strike a balance and make sure you're able to ship quickly while still ensuring that what goes out the door doesn't have vulnerabilities? The answer begins by recognizing that security is a process, not a feature, and this has ramifications throughout the organization. It means that security engineering needs to be everyone's responsibility (instead of a select few), and it means that when security vulnerabilities crop up — and they will — the organization needs to be prepared and aligned to act quickly.
	

Security
--------


Shipping Often With Security/Agile

* Ability to ship is incredibly valuable but also dangerous.

Overview
========

* Security is a process not a product.
* Security is a part of everything you do, every day.
* Similar to testing, documentation, daily activity.
* Heroku has two man security team.
* Security is everyone's responsibility.
* Every developer should have some understanding of what can go wrong


The OWASP Top 10 (Paste in later)

Example
=======

* Building a REST API
* Should you support all major (common) formats?
* Does this decision have security ramifications?

Ex 2:
=====

* You need to store data.  One format is common, one is less common, harder to read and write and isn't used as often
* Which do you choose?
* Does this decision have security ramifications?

A security vulnerability has been created.

2013 Ruby/Rails YAML Vulnerabilities
====================================

* Real world security issues are multifaceted.
* This can happen to anyone.  Django/Python is not exempt.

More on Security
================

* Secure by default matters.  Defaults matter!!
* YAML "load" and "load_safe"	
* You can't really prove that software is secure.  You can only prove that it's insecure.
* Unknown Unknowns
* If an issue of this magnitude was discovered in your stack would you be prepared to respond?
* Need to define terminology to refer to severity of security issues

A good security policy
======================

* Lays out standard terminology used when talking about security issues
* Explains the expectations and commitments around vulnerability handling.
* Creates a transparent repeatable assessment mechanism.

Terminology
===========

* Advisory
* Low
* Medium
* High
* Critical

Advisory
========

* Issues that the security team wishes to communicate but carry no specific required action.  
* May contain recommended actions, but no specific response is required.

Low
===

* Issues that are expected to be resolved, but have low risk, or low consequences.  Should not interrupt
day to day operations.

Medium
======

* Carry some risk, but have low impact.  May have someone work on.

High
====

* Carry substantial risk, publicly disclosed issues.  Will probably interrupt several developers from multiple teams.

Critical
========

* Threaten the integrity of the company.  Great financial risk or otherwise "sky is falling" level issues.
* "All hands on deck"

Assessment
==========

* Start with OWASP for risk rating
* Risk = Likelihood x Impact
* How likely is that this issue will be discovered and exploited?

Examples of Vulnerabilities
===========================

* http://bit.ly/13ds9X0 (PostgreSQL)
* Likelyhood: threat agent
* Calculate Threat
* Calculate your impact
* Matrix of likelyhood and impact
* This case came out to High level.