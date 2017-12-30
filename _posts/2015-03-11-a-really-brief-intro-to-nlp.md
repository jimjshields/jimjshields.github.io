---
layout: post
title:  "A (Really Brief) Intro to Natural Language Processing"
date:   2015-03-11
categories: programming, recurse center, nlp
---

Hacker School: Week 10, Day 2

It's been far too long since the last post. I promised my check-in group — our daily time for talking about what we're doing here — every day last week that I would write a blog post. I didn't. But here it is, in all its glory.

**What is Natural Language Processing?**

My brief sojourn into working with words — specifically, the Academy Award speeches — sparked an interest in all of the possibilities of combining programming and language. Everything I read and heard about this idea led me back to natural language processing. So, as is my custom, I went straight to [good old Wikipedia](http://en.wikipedia.org/wiki/Natural_language_processing).

"**Natural language processing** (**NLP**) is a field of [computer science](http://en.wikipedia.org/wiki/Computer_science "Computer science"), [artificial intelligence](http://en.wikipedia.org/wiki/Artificial_intelligence "Artificial intelligence"), and [linguistics](http://en.wikipedia.org/wiki/Linguistics "Linguistics") concerned with the interactions between [computers](http://en.wikipedia.org/wiki/Computers "Computers") and [human (natural) languages](http://en.wikipedia.org/wiki/Natural_language "Natural language")."

So NLP combines a few things — CS, AI, linguistics — but ultimately concerns how computers work with natural languages (aka our human languages). Don't worry, it doesn't take a background in CS, AI, or linguistics to get the basics. 

**Why Do I Care?**

I care because NLP has a huge number of potential applications — many of which are challenging, fascinating, and (eventually) world-changing (if computers could actually understand anything — anything — we ask them). But more immediately, I care because NLP is actually tangible and accessible, even for beginners. Much of what I've learned in programming is conceptual, or mathematical, or involves a large number of moving pieces. NLP (at its most basic) is taking organized text — a thing I already understand and _can see — _and manipulating and analyzing it in a way that I could talk about with anyone who has read or written text.

For this (again, really brief) intro, I'm going to use a Python library called [Natural Language Toolkit](http://www.nltk.org/) (NLTK). I'll try to assume as little knowledge as possible, but a basic understanding of how to write Python and interact with the terminal will definitely be helpful. I'm essentially following along with the start of [this book](http://www.nltk.org/book_1ed/) (or [this version](http://www.nltk.org/book/) if you like Python 3). Just the first section of the [Preface](http://www.nltk.org/book_1ed/ch00.html) gave me a much better understanding of why NLP is important and uniquely challenging. It's written by the creators of NLTK, and gives a much more thorough and understandable intro to using the NLTK library than I ever could. I'll use two of their intro examples to show what you could do right away.

**Getting Set Up**

I'll assume you already have Python and some kind of interactive terminal (if you have a Mac, both should already be there). If you're completely new to Python, but are interested in learning about NLP in Python (or in general), the [book I referenced before](http://www.nltk.org/book_1ed/ch01.html) does a much better job than I ever could easing a newcomer into both Python and NLP/NLTK.

In fact, I'll just point you to [this section](http://www.nltk.org/book_1ed/ch01.html#getting-started-with-nltk) for getting set up with NLTK (just those few paragraphs up to 'Searching Text.') If you have some experience with _pip_** **and/or virtual environments, it can make installing NLTK easier (it's what I used).

Once you have your terminal open, here's what you'll type:

_$ python_

This should open the Python interactive interpreter (or [REPL](http://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop)). You can type in Python code and the results of the code will appear immediately. I find it's a great way to try out my own code, or try using a new library, package, or API, to actually see the results of particular code. I also just love typing some code in and getting immediate feedback. If you have NLTK installed, try  (any text following "&gt;&gt;&gt;" is Python code you can enter):

_&gt;&gt;&gt; from nltk.book import *_

This'll import a bunch of books! NLTK has a number of text sources — books, news stories, chat logs (anonymized, don't worry) — to analyze/use in your code. You should see the name of each print as they load. Should look something like this:

![image](https://78.media.tumblr.com/f9775e12be5531d3e0047e15b97ca968/tumblr_inline_nl1wxuyFjR1t8beow.png)

Now you can use them!

**What Can I Even Do?**

Try this:
![image](https://78.media.tumblr.com/99432a0edfd859651589fe79287c0bfc/tumblr_inline_nl1wztqZXg1t8beow.png)

_text1 — _the full text of _Moby Dick — _is what you just loaded from NLTK above, and is now accessible/usable by Python. More specifically, it is an object of type 'Text' — this is specific to NLTK and allows you to perform a bunch of cool operations on it. In fact, try this:

_&gt;&gt;&gt; dir(text1)_

It should look like this:

![image](https://78.media.tumblr.com/c3ebf04cb55151980a105519d99be3b1/tumblr_inline_nl1z6aN85R1t8beow.png)

_dir()_ is a really helpful Python command — it effectively shows all of the attributes associated with the object you put in the parentheses (important to note that everything in Python is an object, so you can use _dir() _with everything — [even _dir()_ itself](http://i.kinja-img.com/gawker-media/image/upload/s--QAu_RHov--/18k2ozi2bcff3jpg.jpg)). Put more simply, it's everything you can do or access for a given object. It might seem overwhelming, but for now I'll ignore everything with trailing and/or leading underscores (these are for the most part standard Python operators) and focus on the other stuff, specific to Text objects in NLTK (like 'collocations', 'plot', and the one we're about to use).

**Searching Text**

Promised we would, so let's search the text!

_&gt;&gt;&gt; text1.concordance('whale')_

![image](https://78.media.tumblr.com/b932d3035d2e0fe72d5beb697980f612/tumblr_inline_nl1xm3hQLI1t8beow.png)

_concordance _is one of the actions (aka methods) of Text objects (it's just to. So you have a text object — _text1 — _call a method on it — _.concordance()_ — and put some argument in the parentheses — _'whale'_. The argument is a string you want to search for in the text. The result of this method is what you see above — all of the places in the text with the word 'whale' along with its context (all of the words surrounding it). It's limited to displaying the top 25 (of 1226 — unsurprisingly, lots of whale talk in _Moby Dick_). This is kind of amazing! It's probably one of the simplest features of NLTK, but I can imagine a ton of applications — not the least of which is it just looks cool: you could make a web app just to do this and show the context for any word in some text!

Sidenote: 'Concordance’ comes from publishing, and refers to exactly what we did above (list words in a text with their contexts). [Its Wikipedia entry](http://en.wikipedia.org/wiki/Concordance_%28publishing%29) highlights what makes NLTK, and computing in general, so amazing: ‘Because of the time, difficulty, and expense involved in creating a concordance in the pre-computer era, only works of special importance, such as the Vedas, Bible, Qur'an or the works of Shakespeare or classical Latin and Greek authors, had concordances prepared for them.’ Now we can do it with one command! That’s just the best.

**Finding Similar Words**

Let's try another cool method — _similar_:

_&gt;&gt;&gt; text1.similar('whale')_

![image](https://78.media.tumblr.com/313e0eaf48226eb015a6f44a62d53545/tumblr_inline_nl1zecmrNa1t8beow.png)

According to the NLTK book, _similar _finds 'other words [that] appear in a similar range of contexts' as the given word. So 'ship' is found in more contexts with 'whale' than any other word — because of this I can reasonably conclude that the two words are similar in _Moby Dick_. Already I can see how I'd apply this elsewhere — e.g., I could find words similar to a particular topic, which could form the basis for more complex [sentiment analysis](http://en.wikipedia.org/wiki/Sentiment_analysis). Or, again, I could just make a fun web app that allows you to type in a word and get similar words in a body of text. 

This obviously barely scratches the surface of natural language processing and the Natural Language Toolkit, but hopefully gets you a little interested. I'd love to write more about some of the other features/possibilities, and maybe even walk through a project I'll create with it (though I have to do it first). I'm sure I'll have more to say soon.

* * *

Resources:

[NLTK book](http://www.nltk.org/book_1ed/): The better-written basis for this post. Go try it out!

[NLTK](http://www.nltk.org/): The home for the Natural Language Toolkit. Has some simple/cool examples and additional resources.