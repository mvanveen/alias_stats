Title: 	 Alias Stats
Authors: Michael Van Veen
Time: 	 1328688775


**Note:** This is a work-in-progress.

Alias Stats
===========

A Markdown and Javascript notebook for [GitHub][github] UNIX alias stats.

Abstract
--------

The UNIX alias is an indispensable asset for the efficient, happy hacker.  Repeating the same keystrokes over and over and remembering the various incantations we produce at the prompt is a tedious nightmare we've thankfully automated away for a while now.  


Unfortunately, these gems of productivity have traditionally been locked away within each user's own home directory.  The maintenance and sharing of one's aliases and has always been somewhat of a hassle…until now.

The advent of distributed revision control such as `git`, as well as the emergence of social coding platforms  like [GitHub][github] have incredibly aided the fluidity of aliases.

People finally have a simple way to share and distribute their spells with one another!  This innovation has opened up an opportunity for exploration.

Our goal is to investigate the space of unix aliases and determine what patterns and dynamics are at play within this space.

### Topics of Interest

Here are a list of questions we're hoping to answer/are curious about:

1. Why do some people prefer a particular alias over another one?
2. Which alias is the "best" for a particular command, and why?
3. How do a developer's environmental/language/editor habits affect their alias choice?

Method
------

### Data Aggregation

We crawl github's public search results in order to grab out any Shell code
with the search query `alias`.  The results are aggregated, fetched, and parsed using 
the pipeline designed in [this repo][alias-scrape].

The result is a simple [sqlite] database which drives our front-end.

### Front-End

A home-brewed mix of Markdown, Python, and Javascript.  More to come later.

Terminology
-----------

* **alias key**: The prefix that someone aliases a string to.  The shortcut that you'd type at the prompt.
* **alias value**: The string that someone is aliasing to.  The shortcut that you'd type at the prompt.
* **command**: see alias value.

Results
-------

### Pie Charts

**Alias Keys**

{{pie_alias_keys}}

**Alias Values**

{{pie_alias_values}}

Helpful Links
--------------

* [Scrapy](http://readthedocs.org/docs/scrapy/en/latest/): The world's best web scrupling platform
* [SQLAlchemy](http://www.sqlalchemy.org/): The ORM I'm thinking of using.
* [RaphaelJS](http://g.raphaeljs.com/): Awesome javascript chart library


[alias-scrape]: http://www.github.com/mvanveen/alias-scrape
[github]: http://www.github.com
[sqlite]: http://www.sqlite.org/
