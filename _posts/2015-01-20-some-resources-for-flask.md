---
layout: post
title:  "Some Resources for Flask"
date:   2015-01-20
categories: programming, recurse center, flask, python
---

(Hacker School: Week 3, Day 1)

Wasn't technically at HS yesterday, but I wanted to give a little more detail on how I learned Flask last week. This is really only interesting if you want to work with Flask, so I guess you've been warned.

Here are my major takeaways from learning Flask:

*   It's a web framework written in and for Python.<sup>1</sup>
*   It's relatively easy to learn - but that's relative to larger frameworks like Django (for Python) or Rails (for Ruby). If you're truly new to web development, there's still a good amount of assumed knowledge/understanding. 
*   It's easy to learn because it does only a few, specific things, and those things don't take too long or too much pre-requisite knowledge to understand.

Here are some great resources for getting started, though they do require a minimal amount of assumed knowledge of intermediate topics in Python, the underlying concepts of web applications (routing, templating, HTTP requests, etc.), and working with databases:

*   [Official Flask documentation](http://flask.pocoo.org/docs/0.10/): Great if you have some experience in other frameworks/have developed web apps on your own before.
*   [Quickstart](http://flask.pocoo.org/docs/0.10/quickstart/) (also part of the official Flask docs): Perfect if you just want to get something working, even if you're just starting out. Does assume you've installed it already, which is outlined by them [here](http://flask.pocoo.org/docs/0.10/installation/).
*   [Tutorial](http://flask.pocoo.org/docs/0.10/tutorial/) (again, official): A little more advanced - they take you step-by-step through building a web app using a database and some templates. More assumed knowledge here, so a bit more confusing if you're just starting out.
*   [The Flask Mega-Tutorial](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world): Written by Miguel Grinberg, who wrote the [O'Reilly book on Flask](http://flaskbook.com/)<sup>2</sup>, a more in-depth tutorial that spends more time getting you oriented, even if you're just getting started. If you have some more time and patience to get into the details and possibilities of using Flask, this is a thorough but straightforward intro. 
*   [Jinja2 documentation](http://jinja.pocoo.org/docs/dev/): One of the two<sup>3</sup> pre-installed libraries for Flask is called Jinja2. It allows you to use templating to build dynamic HTML templates that will render using data derived from databases and manipulated using Python. Once you have an understanding of how it works, it's powerful - but until then it can be a little confusing. [Here's a simple example.](http://jinja.pocoo.org/docs/dev/intro/#basic-api-usage)
*   [Using SQLite3 with Flask](http://flask.pocoo.org/docs/0.10/patterns/sqlite3/#sqlite3) (again, part of the offish docs): assumes that you know basic SQL and how to work with databases. If you're not familiar, it's worth struggling through this part on your own - and especially trying to understand what each piece of code does. Hopefully I'll write a more detailed post soon that walks through that; it's just a broad and potentially complex topic.
*   [My Flask Tutorial](https://github.com/bev-a-tron/MyFlaskTutorial): A former HSer (bev-a-tron on GitHub) wrote what looks to be (and recommended by multiple HSers as) an excellent intro to Flask for people who don't have all of the knowledge the above tutorials tend to assume. I haven't worked through it yet but even the intro makes it clear that the tutorial is truly a tutorial - for people with no web development experience (just some Python experience).

I'm sure there are other good resources - I'll try to add them here if I encounter them - but these are great for just getting started in Flask. A lot of the concepts introduced in Flask also translate easily to other web frameworks - and it's worth knowing what the framework actually does for you, in case you can't rely on it for some reason (e.g., it doesn't do what you want it to).

* * *

<sup>1. Obvious, yes. But if you don't know what that means, you probably won't be interested in the rest of this. But if you are interested, and you don't know what that means, you just have to learn a bit more - and that's ok too! Or you might just want to struggle through learning this - it'll make it stick, so to speak.</sup>

<sup>2. [O'Reilly](http://www.oreilly.com/) is a terrific - and pretty much the definitive - resource for books on programming. I've read a few, and they tend to be easy to read, step-by-step, and comprehensive. (Also, many are free online!)</sup>

<sup>3. There's another - [Werkzeug](http://werkzeug.pocoo.org/docs/0.9/) - that takes care of WSGI/HTTP stuff for Flask. I haven't learned much of it yet - I just know that it allows you not to deal with the lower-level details necessary for building a web app in Python. They also have [a tutorial](http://werkzeug.pocoo.org/docs/0.9/tutorial/) - I haven't worked through it but it seems detailed and actually kinda fun.</sup>