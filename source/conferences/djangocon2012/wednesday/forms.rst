============================
Django Forms in an API World
============================

**Presenter:**  TAREQUE HOSSAIN

**Track:** I

**Description:**

    In a world of django powered web APIs and arbitrary consumers, traditional methods of rendering & validating django forms are ineffective. We discuss how to uphold the API provider/ consumer separation, yet utilize provider's django form subsystem to power forms in a pure JS consumer. We achieve this by serializing form configurations, rendering metadata, error handlers & exposing them over API.
    
    


Whats wrong with Forms
----------------------

New Way
-------

* Django forms live on API server
* Validates/saves API
* Trying to match frontend to the API


API Clients
-----------

* Website no longer lives on the same server
* Forms exist on phones/web sites/other devices
