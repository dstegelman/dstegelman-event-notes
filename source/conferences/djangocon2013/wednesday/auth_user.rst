================
Django Auth User
================

**Presenter:** Russell Keith MaGee

**Track:** I

**Description:**

	An exploration of one of the banner features of Django 1.5 -- Custom User models. Includes worked examples, a discussion of design decisions that must be made, and a look at the internal architecture that makes it all possible.
	
	
Auth User Model
---------------	

Why Should We Care?
===================

* Login with email address
* Associating profile data with the user model
* Not clearly understood

Whats in a name?
================

* Names are different (not just first and last)
* Non western names
* Some last names do not have family names
* Some do not have last names at all.
* Django assumes that you have a distinct first and last name, is wrong.

Names are Hard
==============

* Do you need separate fields
* Just use a Full name?
* If you need to seperate them, use "Family name" and "Other/given name"
* Ask "How would you like to be addressed"?

Tips
====

* Don't assume a single letter is an initial
* Be wary of name-part algorigthms
* Spaces, Apostrpohes, and Hypens are all level characters in names
* Don't require a "Family Name"
* "previous name", not "maiden name"
* Honorifics are even more complex.  Can't just add "mr" in front of a name

On the subject of "do you need to ask"?
=======================================

* Why do you ask for certain things? (Gender?)
* Kuzdu and the California Marriage amendment

When it comes to identity you need to think:
============================================

* Do I need to ask at all?

I. Define User Model
====================

* 2 possible base classes (Abstract base user, abstract user)
* Define username field
* Define requried-fields
* Define get_full_name and get_short_name




