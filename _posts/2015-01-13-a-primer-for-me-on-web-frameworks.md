---
layout: post
title:  "A Primer (For Me) On Web Frameworks"
date:   2015-01-11
categories: programming, recurse center, web frameworks, python
---

(Hacker School: Week 2, Day 1)

Yesterday - day 1 of week 2 of HS<sup>1</sup> - I learned about [web frameworks](http://en.wikipedia.org/wiki/Web_application_framework). Like a lot of other things in programming - object-orientedness, version control, package managers, variables, the Internet, Y2K - "web framework" is a term I've heard a lot, but to which I'd attached little meaning. "Yeah, Django's a web framework, it like makes websites more dynamic and scalable and has these views and is the best" is probably a quote I said to myself at some point in the (not too distant) past, with little understanding of what Django actually does (and if you think Django is [this](http://www.imdb.com/title/tt1853728/), [this](http://www.imdb.com/title/tt0060315/), or [this](http://en.wikipedia.org/wiki/Django_Reinhardt), or none of those, that's cool too).

So, yesterday, I set out to change that. And thanks to this [terrific, simple, insightful post](http://www.jeffknupp.com/blog/2014/03/03/what-is-a-web-framework/) by Jeff Knupp - I think I did OK. (Much of this will be summarizing his points - and so are mostly just notes for myself to digest them.)

(I'll try to be as clear as I can to people who know all of this and people who don't in most posts - I think it helps me to communicate what these complex concepts are in a concise, easy-to-understand fashion. Most people aren't programmers.)

It really starts with "How does the Internet work?" Let's assume we're just talking about me trying to go to amazon.com on my laptop through Google Chrome.<sup>2</sup> My browser - Chrome (or Firefox, or Internet Explorer, or whatever) - is the _client_. Most simply, anytime I go to a website, the browser/client is _requesting_ data from the website's _server__. _So I type in www.amazon.com and hit Enter - that's the request. The server then _responds_ with data. That data is always, when it gets back to the browser/client, in the form of HTML (and CSS and JavaScript, [but that's not important right now](https://www.youtube.com/watch?v=VOmD-xqK2Es)). The browser/client then _renders_ that HTML (and CSS and JS) - takes all of that data and turns it into the page (amazon.com) you're used to seeing. Anytime you click on a link, or go to a new site, it goes through that process again.

So if the process is that simple - a browser/client sends a request, as a URL/web address, to the server, the server sends back some HTML, and the browser/client renders the HTML - why would it need to be complicated by a bunch of stuff in the middle<sup>3</sup>? Well some<sup>4</sup> would argue you don't need to<sup>5 </sup>- but whether or not it's a good idea to use web frameworks, it's good to understand what they are and do, how to use them effectively if at all, and how you'd do what they do without them.

As simply as possible, web frameworks are there to allow you as a programmer to write as little code as possible, primarily for web-specific tasks that are done over and over again. For example, every page on Amazon has the same exact (or extremely similar) header toolbar (where you search for stuff or pick a category). They could write all of the HTML for that bar and copy it for every single page they have - millions, probably - or they could use some kind of template for that header, and attach the stuff under it (all the product info) automatically. Amazon may not use a standard, freely-available web framework, but many frameworks allow you to do similar templating.

Yesterday, I learned [Flask](http://flask.pocoo.org/docs/0.10/)<sup>6</sup>. Flask is one of those web frameworks<sup>7</sup> - this one's Python-based. It's a good one to learn, though, because it does as little as possible and it's easy to follow how the creators actually went about writing the code to make it work<sup>8</sup>. It has the aforementioned templating (implemented using a library/package/whatever-you-want-to-call-it called [Jinja2](http://jinja.pocoo.org/docs/dev/)), and takes care of all of the magic that happens when the client requests something from the server<sup>9</sup>. It also helps with URL routing - using the same example, if you type in anything after amazon.com (like amazon.com/books), the "/books" part is used to determine which data to send back to you. It can get more complex and interesting but that, [in a nutshell](https://www.youtube.com/watch?v=jKMK3XGO27k), is URL routing.

So what can I actually do with it? Yesterday, I got it to show me some pages in HTML, and even connect to a database. But the project I was attempting takes a ton of data, so I'd like to step back today and do something simpler - create a very small but usable web app where I can track my to-do list. Once I'm convinced I know the ins and outs of using Flask - and what it's actually doing for me - I'll move onto something bigger.

Hope that was helpful, future Jim.

* * *

<sup>1 I like giving some context, for when I inevitably come back here to re-read all of my thoughts like a weirdo.</sup>

<sup>2 I'm leaving a ton of possibilities out - and also a lot of the evolution of the Internet - but this is the most straightforward example.</sup>

<sup>3 Web frameworks could be pretty effectively summarized as "a bunch of stuff in the middle."</sup>

<sup>4 Including last night's HS speaker - [r0ml](https://twitter.com/r0ml) (his preferred moniker)</sup>

<sup>5 If I was a weaker man, his talk would've effectively invalidated all of my learning for the day.</sup>

<sup>6 Probably an overstatement. I learned the basics and have an OK grasp of what's going on.</sup>

<sup>7 Other examples (that I know anything about): Django, Rails, Bottle, Sinatra. Here's a [Wikipedia list of all frameworks](http://en.wikipedia.org/wiki/Comparison_of_web_application_frameworks) - there are a lot.</sup>

<sup>8 Also it has great, straightforward, step-by-step documentation - not always assumed for any kind of software/package/&lt;/sup&gt;etc.</sup>

<sup>9 It involves HTTP - basically the standard set of rules for making those requests - and WSGI - Python's standard set of rules for using Python to interact with the data - both of which are blog posts on their own.</sup>