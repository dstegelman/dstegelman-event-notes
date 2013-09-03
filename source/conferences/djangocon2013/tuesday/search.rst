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
** Whitespace/N-grams/word delimters
* Filters
** ASCII/Stemming/Lowercase/stop words/synonyms
* Language specific filters.
* Querying (Data Out)
* Match tokens against tokens
* Faceting - Characteristics of a set.  
* Spell checking
* Geospatial search
* Autocomplete

Django
------





