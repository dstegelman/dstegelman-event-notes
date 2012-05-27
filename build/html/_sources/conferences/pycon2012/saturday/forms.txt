================================
Django Form Processing Deep Dive 
================================


**Presenter:** Nathan Yergler

**Track:** V

**Description:**

    Django Form processing often takes a back seat to flashier, more visible parts of the framework. But Django forms, fully leveraged, can help developers be more productive and write more cohesive code. This talk will dive deep into the stock Django forms package, as well as discuss a strategy for abstracting validation for forms, and the use of unit and integration tests with forms.

    https://us.pycon.org/2012/schedule/presentation/420/
    
    http://yergler.net/2012/pycon-forms
    
Basics
======
    
Forms in Context
----------------

VIews - Convert request to response
forms = Conert input to python objects
models - Data and business logic    

Forms
-----

* Forms are composed of fields, which have a widget
* Ubound forms dont have data associated with them but can be rendered

::
    
    form= ContactForm()
    
* bound forms have specifid data assoicated which can be validated, can be any dict of data

::

    form = ContactForm(request.POST)
    
Two ways to access fields

::
    
    form.fields['name']
    #Field Object

::
    
    form['name']
    # outputs html widget
    
Forms can be given initial data

Validation
==========

* Only bound forms can be valided
* Fields are validated, then the form itself
* Validation, then cleaning
* Validation Error

Field Cleaning
--------------

* To PYthon, Validation, Cleaning
* .clean_fieldname() method is called after validators
* already converted to python
* methods ``must`` return a clean value


::

    def clean_email(self):
        if (self.cleaned)data.get('email', '').endswith('hotmail.com'))::
            raise ValidationError()
            
        return self.cleaned_data.get('email', '')
        
* Using get is safer if not a required field.

Form Validation
---------------

* .clean
* Called even if errors raised by fields
* Must return the cleaned data dictionary
* Initial data != default data
* Defaults for non-required fields should be specified when accessing the dict.

Changes
-------

* form.has_changed()
* form.changed_fields

Testing
=======

* Remember whats forms are for
* Testing intial states, field validation, final state of cleaned data

::

    class FormTests(TestCase):
        def test_validation(self):
            form_data = {
            'name': 'x" * 300,
            }
            
            form = ContactForm(data=form_data)
            self.assertFalse(form.is_valid())
            
* Rebar, open source. Couldn't find the link.

::

    from rebar import flatten_to_dict

    form_data = flatten_to_dict(ContactForm())
    form_data.update({
        'name': 'x' * 300,
        })
        
Rendering Forms
===============

* Class based views with forms is excellent

Form Output
-----------

* as_p()
* as_ul()
* as_table()
* field.label
* field.label_tag
* field.html_id
* field.help_text
* field.errors 
* required_css_class
* error_css_class

::

    name = forms.CharField(error_messages={'required': 'something'})

Error Class
-----------

* Error list is used as <ul>
* Specify the error_class kwarg

::

    from django.forms.util import ErrorList

    form = ContactForm(data, error_class=ErrorListClass)

* Avoid name collisions with prefix

::

    contact_form = ContactForm(prefix="contact")


Other Notes
===========

* Model forms have an additional method, ``_post_clean()``
* FormSets to put many of the same form on the same page
* Same validation structure
* http://yergler.net/2012/pycon-forms






