---
layout: post
title:  "Learning a New Programming Language"
date:   2020-11-10
categories: recurse center, go, python, scraping
---

## Back to RC

This week, I took a week off from work to attend a mini batch at the [Recurse Center](https://www.recurse.com/). I've been wanting to go back for a while, and now seemed like the perfect time to do something different for a week, even if I'm still at home.

My goal for the week is ambitious, but simple: learn a new language. In my first batch, I learned Python (and some JavaScript), and in the last 5+ years at YipitData, when I've coded, it's always been in Python or JavaScript. 

So I picked [Go](https://golang.org/), since it's pretty different from Python & JS: it's statically typed, compiled, and known to be great for concurrency. I'd especially like to learn why it's good for concurrency, as I have very little experience in concurrent programming, and know that Python is considered not-so-good for concurrency.

On day 1, I met a lot of folks at RC, and was impressed (and intimidated) by their ambitions and project ideas.

I spent the rest of the day trying to learn the basics of Go, and felt like a beginner and an imposter.

## Tips for Learning a New Programming Language

In reflecting on my frustration, I realized that there were a few key ideas I should've focused on when approaching a new language, especially with a short amount of time. Here's what helped me:

### Run code often
When working in Python, if I'm taking a shortcut and not using TDD, I tend to run code snippets in a REPL (`ipython`), or as a script and use a debugger (`ipdb`). It encourages me to have a short feedback loop between code changes and running my code.

I don't want to focus on TDD with Go this week, even if it would have compounding benefits — I really want to focus on getting my code working as fast as possible.

There are two aspects of Go that are new to me: it's statically typed (tldr: you must have types), and it's compiled (tldr: code must be compiled before being run). Because it's compiled, I assumed that using a REPL or running the code would naturally have a longer feedback loop. But it doesn't have to!

I structured my first program like (simplified):
```
myproject/
    /main.go
    /scraper/
        /scraper.go
```

`main.go` is my program's _entrypoint_, and it imports `"myproject/scraper"`. Though Go is compiled, it helpfully has a command to build _and_ run your program from its entrypoint:
```
go run .
```

This was exciting, I could run my code with every change! But even with this smoother workflow, I tend to make a few changes at a time, and had unexpected compilation issues almost every time. With such a short time to learn a new language, I wanted a way to make the feedback loop even faster, so I learned I should...

### Get a good IDE!

During my first batch at RC, I used SublimeText — a great text editor, but not a full-fledged IDE. This was really effective for my first language: I spent a lot of time actually _writing_ code, which forced me to _think_ in code. I've found that this time was crucial for working as a programmer, and that thinking in code has become like riding a bike.

Now, when I work, I use a full-featured IDE (PyCharm), and it's made my coding significantly faster: it auto-completes, highlights errors, runs tests, auto-formats. I don't need to spend the time writing code.

In my first day in Go, I assumed I needed the same practice time to start to think in Go. But I can already think in code! What I really want is to map that framework to a new language, and to do that, I don't need to painstakingly write out every single line of code. So I finally realized I should download a good IDE to complement my thinking, and luckily, JetBrains (who make PyCharm) have a Go IDE ([Goland](https://www.jetbrains.com/go/)) with all of the features I'm used to. 

Already it's made my coding significantly faster and less frustrating.

### Build a small project I've built in another language

I picked a small web scraping project I'd already worked on in Python: scraping https://letterboxd.com/ to find how expensive it is to stream a playlist of movies (e.g., a director's filmography). At RC and at YipitData, I've spent a lot of time web scraping in Python, *so I can focus on the language, rather than the domain.*

This project has been surprisingly difficult — Go's ability to work with web scraping and JSON is not nearly as simple as Python — but I've mostly finished. 

I've found that starting with a small, familiar project is effective because it *gives me boundaries*, and I'm much more likely to finish and feel like I learned something. With larger and more unbounded projects, I feel like I've learned less if I didn't finish the project.

Here's my v1: https://github.com/jimjshields/letterboxd_scraper

I did add a bit of Go-native concurrency, just to learn how it works. It's very expressive and cool, btu hard to totally wrap my head around.

Here's how to run (it's not very useful yet, just prints out a lot of streaming sites for a directors' movies):
```
git clone git@github.com:jimjshields/letterboxd_scraper.git
go run . 'Bong Joon Ho'
```

Now I'll work on making it useful and fun!
