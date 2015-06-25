================
REST for an Hour
================

Testing
-------

- Can test in the browser using POSTMAN
- Fiddler

Designing
---------

- Understand Purpose
- For use with a particular client/front end app
- For Javascript
- Building a FINE api, servce needs of the app only.
- Lots of calls but its fairly useful to make someting else and re-use.
- Dont let front end change how you design and develop it in the API.
- Be consistent
- Highly recommended to build a FINE api that meets the needs of the app.
- Ask for use cases
- Deprecation is important.

The Purest and Pragmatic
------------------------

- HATEOAS
- Hypermedia APIs
- Most APIs are not truly RESTful
- Hypermedia may not be the most important part of it.
- Lot of work for little pay off

Versioning
----------

- Versioning directly in the URI
- Highly recommend that no version specified means V1.
- More correc to put versions in the header during content negotiation.

Considerations
--------------

- Scalability
- Performance
- Security
- Logging with multithreaded servers
- Documentation  (RAML)
- Usage/Metrics Auditing

Best Practices
--------------

- Consistency
- Status codes matter!!
- Provide HEAD calls for large entities
- Special attention to date and times.  Always represent in UTC
- TDD
- System integration tests.

Anti patterns
-------------

- Imporper response status codes.
- Verbs in the URI
- Misued query parameters (id=?)
- Method confusion
- Conusion between POST, PUT, and PATCH
- 401/403
- 500 for everyhing
- 400 for everything is worse
- 200 for everything
- Race concurrency issues
- No automated tests
