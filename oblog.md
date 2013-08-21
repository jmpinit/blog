---
wip: true
date: 2013-07-31 10:19:30
desc: jekyll-like static blog but faster
---

Jekyll-like Static Blog Generator
=================================

![oblog]({{site.url}}/images/oblog/oblog.png)

Frustrated with long site generation times using Jekyll, I set out to create a similar but much simpler system that I could optimize for my needs:

* speed - see rendered changes as soon as possible
* minimalism - few dependencies and code that is easy to follow
* connectivity - publish from any of my devices

## Tech

* [Liquid Templating](http://liquidmarkup.org/)
* [Kramdown](http://kramdown.rubyforge.org/) (markdown superset)
* Dropbox (for accessing posts anywhere)

## Flow

1. Write post as markdown file in Dropbox.
2. Upload any pictures for the post to the server.
3. Execute "publish".
4. New post and index.html are generated.
5. New post and index are uploaded.

Ideas
-----

* use [git API](https://github.com/schacon/ruby-git) to generate ncftp commands for pushing updates to server

Source Code
-----------

TODO - link to code

_(It's called oblog because my name is Owen.)_
