===================================
Custom User Model/Django Auth Tools
===================================

**Presenter:** Aaron Merriam, Rocky Meza


**Description:**

Django Auth Tools

FusionBox

Custom User Models
------------------

* Supported in Django 1.5
* MOst apps don't use a username (use Email instead)
* Not the correct pattern
* More control
* Adding custom methods and properties

Adding A Custom User Model
--------------------------

* Must implement methods and custom manager
* Custom user admin won't work
* Lots of custom code needs to be written
* Lots of boilerplate
* Custom login logic
* Custom password reset logic


Django Auth Tools
-----------------

Custom user app
===============

* Add to installed apps.
* Already implemented the required methods
* AbstractBaseClass
* Class based views so methods can be drop in replaced.
* Password reset confirm and login in one view.
* Generic forms 
* Generic model admin classes.
* Email as username, but others..

Migrating
=========

* Take over the table.  Migrations still needed.
* Django's email field on user does not enforce a unique constraint
* 3rd party applications aren't all ready.

Storing Additional Information for a User
=========================================

* Don't store user information in the new user model.
* Mixes profile code with authorization and authentication.

User Profiles
=============

* Just make a relationship between the profile and the user object.
* Profiles for users in each app/project.
* Idea is to package user profile info into an app so it can be re-used.

Dos Don'ts
==========

* use get_user_model instead of django.contrib.auth.models.user
* Don't point them directly at the user model
* models.ForeignKey(settings.AUTH_USER_MODEL)














