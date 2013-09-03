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
           c. Main issue is bottle-neck entering data to DB
           d. Need an easy way to generate load ... JMeter
           e. Record yourself testing a complex process
           f. HTTP Cookie Manager built into JMeter
           g. pgfouine --> log postgres performance
    2. Scaling Phase 1: Chicago Public Schools
    3. Scaling Phase 2: The State of Illinois
    4. Optimizing your PostgresSQL

