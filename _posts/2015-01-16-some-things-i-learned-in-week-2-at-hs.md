---
layout: post
title:  "Some Things I Learned in Week 2 at Hacker School"
date:   2015-01-16
categories: programming, recurse center, learning, make it stick
---

(Hacker School: Week 2, Day 4)

Out of laziness/inability to put together a coherent and thoughtful summation of my week, I'll stick to the random list format. (h/t [randomlists.com](http://www.buzzfeed.com/))

1.  What a web framework does. Using Flask as a proxy for understanding the larger point of web frameworks was a good choice - I'd recommend it to anyone looking to start learning web development. It takes a bit of effort to connect the underlying concepts to what Flask does specifically, but it is a good starting point. I'd like to elaborate more in a (more coherent and thoughtful) post on what exactly it does, how to use it to make something simple, and what's difficult about using it for someone unfamiliar with programming or web frameworks.
2.  How to work with a database in the simplest possible way. I had a decent grasp of how to write SQL queries - basically, what you write to get, add, or update data in a database - but had very little understanding of how to set one up, make it work with a web app, or even what one really is. Again, a later, better post.
3.  What actually happens when you visit a website on your browser.<sup>1</sup>
4.  It's not a good idea to install whatever you want at any time. This is probably good advice in general - but especially for a programmer. In Python, it's considered bad practice to install all but very few packages globally<sup>2</sup>. Instead, you should create - and consistently use - [virtual environments](https://virtualenv.pypa.io/en/latest/). This is something that always gave me some confusion/fear - the name "virtual environment" in and of itself is not super helpful in understanding what it does - but they basically allow you to install sets of packages specific to a particular project, without having them conflict across projects. Again, a whole blog post.
5.  User authentication is still confusing; I'll return to it later.<sup>3</sup>
6.  It's a good idea to stick to the specifications (aka specs, a good fancy tech word) you set out for yourself when building a program - no matter how small. You can return to and refine those specs at any time, but without a map, you can easily get lost. Don't be me when coming out of a subway station - orient yourself before just walking in the direction that seems kinda-sorta-yeah-it-must-be-north, and then walk south for like ten minutes, especially in an unfamiliar setting.<sup>4</sup>
7.  Regular expressions! They are scary and potentially confusing and I'd avoided them for a while. But they are also super cool - and there's a great step-by-step, interactive tutorial for them [here](http://regexone.com/).<sup>5</sup>
8.  How to learn, and how to reflect on how I learn. Already plugged this book, but [Make It Stick](http://www.amazon.com/Make-It-Stick-Successful-Learning/dp/0674729013) is really insightful on this topic - though I'm surprised by how common-sensical the author's arguments seem. For example - it's a good idea to weave (or their word, interleave) different topics together over the course of learning a larger topic - rather than the typical chunks of information (like a math textbook, where you learn one topic completely, then move onto the next and forget about the last one). It makes so much sense! I definitely don't learn this way, so I'd like to refine my learning habits to be more in line with what they recommend during my time here.

I'm sure I learned a million other things, but these have stuck with me this week. Looking forward to learning more, and more deeply, next week.<sup>6</sup>

* * *

<sup>1 You type in a URL - that's a request - the website's server sends back data that's been formatted in HTML - that's the response - and the browser renders it/makes it look like a website. Or you don't - that's your prerogative.</sup>

<sup>2 Packages - basically programs written for use with Python (and other programming languages; in some other languages they're called something different). Installing globally - installing in your main/root directory so that you can access those programs at any time with any program you write.</sup>

<sup>3 Is this a cheating one? Kind of, but I learned that it is still confusing, so that's something!</sup>

<sup>4 And especially especially outside of the confines of the Manhattan-above-Union-Square grid (or your city's/town's equivalent).</sup>

<sup>5 If you don't know what a regular expression is - it's essentially a way to search for patterns in text, [used in computer science but also in formal language theory](http://en.wikipedia.org/wiki/Regular_expression) (not my words). For example, you want to find all words that have three a's - no more, no less - you can use the regular expression _a{3}_ (I think, would be embarrassing if I have that wrong).</sup>

<sup>6 ...on Serial.</sup>