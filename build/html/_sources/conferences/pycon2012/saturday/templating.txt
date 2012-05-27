========================================
Django Templating: More Than Just Blocks
========================================


**Presenter:** Christine Cheung

**Track:** V

**Description:**

    Django's template language is designed to strike a balance between power and ease of use; learn how to use this balance to create awesome looking websites. This talk will cover the basics and best practices of Django templating, from custom tag and filter creation, to the finer points of template rendering and loading, and even to replacing the default templating engine itself. 

    https://us.pycon.org/2012/schedule/presentation/80/
    
    http://www.xtine.net
    @plaidxtine
    
    
Intro
=====

* Front End Developer
* PyLadies!
* Introduction to Templating
* Effective use of Built In Tags
* Extending Templates
* Template Loading
* Extending Current Django Templating

Basics
======

* This is the end user experience
* Balance between power and ease
* By Design it is seperated so that backend/front end can be developed seperately
* Start with a base template, and have pages inherit from it.


Tools
-----

* Syntax highlighting, autocompletion
* django-debug-toolbar
* Print out tag/filter reference guide.

Structure
---------

* Root template folder, argues against seperate apps/templats

Standards
=========

* Consistent Spacing
* Put all loads at the top
* Use {% comment %} instead of <!-- Comment -->

Common Blocks
=============

* Title
* Meta tags
* Extra_head
* Content
* Extra_JS
    
    
Block Best Practices
--------------------

* End {% block title %} with {% endblock title %}
* Blocks cannot be repeated 
* DOn't over block, only write one if you need one.
* Use include {% include "snippet.html" %}
* Do not over use includes

Variables
---------

* Modify objects with filters {{ var|filter }}
* loop through them useing tags


Security
--------

* Make sure you sanitize data if you are using {% autoescape %}

General Best Practices
======================

* Name URLs
* Do not hard code static
* Django-floppyforms (html5)
* django-crispy-forms - More semantic forms
* {% include form.html %}
* Use {{ form.as_ul }}
* Firstof tag, removing un-necssary if statements
* Custom tags live in application module
* Write simple, basic filters

Example Custom Tag
==================

::

    from django import template
    register = template.Library()
    
    @register.filter(name="remove")
    
    def cut(value, argument):
        return value.replace(argument, '')
        
Other Types of Tags
-------------------        

::

    @register.simple_tag
    
    @register.tag(name="current_time")


* django-templatag-sugar 
* django-classy-tags - Class based template tags

Do Not
------

* Application logic
* Dangerous, Difficult to support
* Do not replicate python logic in the templates

Loading and Changing Templates/Loaders
======================================

* Template Loaders

Replacing the Template Engine
-----------------------------

* Jinga2, Mako, Cheetah
* Django is a bit slower
* Different logic control and handling
* Lots of risk switching becuase you are separting django from its template engine.

Jinja
-----

* Functions callable from templates
* Loop controls
* Multiple filter arguments
* Performace Increase
* More dependencies
* Lose built-in support
* Too much logic in your templates
* Speed increase is minimal

Speeding Up Templates
---------------------

* Cache -Django-template-preprocessor
* django-pancake - Flatten template files
* Remember other bottlenecks (Cache, load balancing) 

New in 1.4
==========

* Custom project and App templates
* Startapp/start project
* Combine with your favorite boilerplate
* {% elif %}







