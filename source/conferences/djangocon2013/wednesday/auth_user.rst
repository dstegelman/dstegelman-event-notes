================
Django Auth User
================

**Presenter:** Russell Keith-MaGee

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
* Define required-fields
* Define get_full_name and get_short_name

II. Define Manager
==================

* Need to describe how to create users.
* Describe how to create superusers.

III. Define Forms
=================

* usercreationform
* userchangeform
* passwordresetform

VI. Register with Admin
=======================

* Only need to do this if your using the admin
* subclass contrib.admin.UserAdmin

V. Register the model
=====================

* AUTH_USER_MODEL = 'myapp.MyUser'

IV.  Update Foreign Keys
========================

* NOT ForeignKey(User)
* ForeignKey(settings.AUTH_USER_MODEL)
* USERNAME_FIELD must be unique and not in REQUIRED_FIELDS

Signal Registration
===================

* Register signals with the actual model that is being used, not hte setting.

What Isn't in the Docs
======================

* Reverse lookup naming.
* The "User Contract" - You must be explicit about what a user object has.

Email Based Login
=================

* Define a user model with email
* Username_field = 'email'
* Define forms, admin.

Don't reinvent the wheel
========================

* Ticket: #20824
* API-based login
* Kerberos single sign-on
* Authentication backends, can have multiple auth backends.
* roguelynn.com/words/

Profile Data
============

* Option 1, put everything in the user model
* Option 2, keep user separate, link to it with a foreignkey
* In option 2, you can provide your own profile model to hook in to the user model.
* Which should you use?

It Depends
==========

* Profiles are better architecture. Makes no assumptions about user model
* Long term user objects.
* Cost of getting a foreign key
* Where do draw the line.

One More Thing
==============

* How does it all work.
* No references to auth.User
* Meta property: Swappable = 'auth_user_model'
* Inspected at run time for the real model class
* The rest is validation
* No new features in ForeignKey() or M2M
* Validation that ForeignKey doesn't point at a swapped models.
* You can make your own models swappable.

https://speakerdeck.com/freakboy3742/red-user-blue-user-myuser-auth-dot-user