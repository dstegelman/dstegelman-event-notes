===================================
Scaling your write-heavy django app
===================================

**Presenter:** Tobias McNulty 

**Track:** 2

**Description:**

    Content management systems and other read-heavy Django apps are 
    relatively easy to scale. Scaling write-heavy apps is another 
    matter. In this talk I’ll walk through our experience scaling the 
    University of Chicago’s custom school survey application to handle 
    over 75,000 requests per minute and upwards of 9,500 PostgreSQL 
    transactions per second.

**Notes:**

    1. Project Overview

           a. 5Essential survey module for UChicago
           b. Not about making app fast but scalable, i.e. multiple users at once

    2. Scaling Phase 1: Chicago Public Schools

           a. Main issue is bottle-neck entering data to DB
           b. Need an easy way to generate load ... JMeter
           c. Record yourself testing a complex process
           d. HTTP Cookie Manager built into JMeter
           e. pgfouine --> log postgres performance
           f. django-cache-machine for specific caching
           g. Choose what you cache via 'cached =' property on a model
           h. use read database to avoid load on write DB
           i. Streaming replication hit PG in 9.1 -- try django-balancer

    3. Scaling Phase 2: The State of Illinois

           a. gevent worker terrible for CPU-bound applications
           b. NewRelic makes I/O looks expensive, but each worker is processing too many reqs at once
           c. Use a sync worker in gevent and it will open up the CPU bottleneck
           d. Database was the bottleneck, still overloaded
           e. Increased size of EC2 instance, still slow
           f. Figuring out max_connections: not web server count ... **Machine resources**
           g. **Use pgbouncer to share a small number of presistent connections**
           h. Run pgbouncer on your web servers using supervisord
           i. Don't need max_conn to be so low, but know what you're changing when you change that

    4. Slides: http://cakt.us/djangocon-scaling
