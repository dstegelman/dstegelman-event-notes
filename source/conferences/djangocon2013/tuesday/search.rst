=====================================
Finding The Needle: Search and Django
=====================================

**Presenter:** Ben Lopatin/Wellfire Interactive

**Track:** II

**Description:**

	Most websites share at least two things in common: content and users who want to find content. This talk will cover the basics of site search using search engines (the kind you run, not Google), setting up a Django project with Haystack, highlight some of the gotchas you might encounter, and touch on some more advanced functionality.
	

Overview
--------

* Understand Search
* role of search engine
* Nifty search features
* Adding search with Haystack
* Implementation Strategies
* Limitations and Options

Search Problem
--------------

* Trying to search text content
* Distinction between searching for and looking for.
* Trying to find information

Search Engines
--------------

* Stop words (remove common words)
* Indexing tokens
* Document data store based on filtered tokens.
* ElasticSearch/Solr/Whoosh/Xapian/Sphinx
* What about SQL full-text indexing? - Can do it, won't get as many features as a search engine.

Data in/Data out
----------------

* Analyzers - Tokenizer + Filters
* Tokenizers
	* Whitespace/N-grams/word delimters
* Filters
	* ASCII/Stemming/Lowercase/stop words/synonyms
* Language specific filters.
* Querying (Data Out)
* Match tokens against tokens
* Faceting - Characteristics of a set.  
* Spell checking
* Geospatial search
* Autocomplete

Django/Haystack
---------------

* Haystack is a pythonic abstraction
* ORM Oriented
* SearchQuerySet
* SearchForm
* Search View

Index Strategies
----------------

* One Time
* Real Time
* Real time-ish (queued)
* Periodic

Building Search
---------------

* Model attribute
* Templates
* Field method (Method that refers to a field)
* Queryset to define a search index (Specify what gets added to the index)

Help Users
----------

* Improve quality of search
* Adjust relevance
* Boot fields, documents, terms
* Log searches, results, and their success
* Use search engine as cache

Doing More with Search
----------------------

* ElasticSearch can configure index analysis.
* Can configure tokenizers and filters
* Write a custom backend/New Default analyzer/Update search mapping

Some Gotchas
------------

* Don't index fields used for sorting
* Debug search issues (Is this plugged in, is anything indexed?)
* Haystack debug pannel for django debug toolbar

SearchIndex = data mapping
