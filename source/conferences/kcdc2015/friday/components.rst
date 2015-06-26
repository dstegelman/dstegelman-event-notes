===========================
Components as Microservices
===========================

* Open Table developer
* Restraunt reservations, free, instant confirmation
* 32k restraunts worldwide


Dismantling the Monolith
------------------------

Negatives
~~~~~~~~~

- Deployments every 15 days
- Not very resilient (new hires had issues bootstrapping and learning)
- Not very robust (single code base)

Good Things
~~~~~~~~~~~

- Had code consistency, one single language
- Dedicated team for infrastructure
- Dedicated team for testing

Few Years Later
---------------

- Start splitting up applications
- Reorganized teams
- Flow changed
- All teams changed
- Multiple code bases

Microsites
----------

- Want to push changes quickly into production
- Reorganize the teams on the front end.
- Break up large apps into smaller parts
- Approach issues in different ways
- Idea is to have small focused sites that do one simple thing
- Homepage microsites, search microsite, etc.
- Quick deployments
- More focused and effective testing
- More robust
- Diversity on technical stacks
- Decoupling

Negatives
~~~~~~~~~

- Static resource duplication
- Markup, JS, and CSS duplication
- Inconsistencies
- Including massive amounts of JS/CSS in all sites.

Common Parts
------------

- Fetching html components through an API
- HTML included in the JSON response.
- Headers and params to get different variants
- Asking a central location for common parts
- For headers/footers/nav etc.
- Pull in shared CSS/JS components

What about..
------------

- Client site rendering
- iFrames?
- Asset complilation during build time.
- WebComponents

Microsites + Shared Components
------------------------------

- Consistency
- Coordination
- Optimal front-end loading
- Easy to spin up new microsites

Negatives
~~~~~~~~~

- New hard dependency for all the front end
- Not possible to create or edit components

Open Components
---------------

- A framework for developing and deploying HTML components
- Enables peopel to create new components and publish them
- Granular ownership
- Performances
- Client side rendering as a failover strategy
- Robust

Conclusions
-----------

- Independent deployments
- SOA is not just about code
- Cultural changes
- Reorganization
