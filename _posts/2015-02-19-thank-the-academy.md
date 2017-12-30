---
layout: post
title:  "Thank the Academy"
date:   2015-02-19
categories: programming, recurse center, oscars
---

Hacker School: Week 7, Day 4

Big gap between writing. 

I've made pretty steady progress on two projects - one the web framework I've been writing, and one a web app ([try it out!](http://thanktheacademy.herokuapp.com/)). I'm not really finished either - one of the major problems I've noticed in programming is the eternal question I have, "is it finished?" - but the web app is simpler to understand, more fun, and super relevant for the Oscars! (or irrelevant if you don't like the Oscars). 

Last week, I found [this](http://aaspeechesdb.oscars.org/), a database for Academy Award acceptance speeches. I decided I had to use it. So I first got all of the data together - using Python to gather the data (I'll leave out the details, but they involve regular expression matching, parsing HTML, and, depressingly, copying and pasting - the site is not the best). And then I built a web app - one with questionable styling, but which does two different, real things!!! - on top of the data! And you can use it!
![image](https://78.media.tumblr.com/6bc231220a924fa509aa6dd1bd64cf08/tumblr_inline_nk1eav6wrK1t8beow.png)

First, it [randomly generates an Oscar thank you speech](http://thanktheacademy.herokuapp.com/) (like above) based on all speeches ever given. It does this through a concept called a [Markov chain](http://en.wikipedia.org/wiki/Markov_chain) - the basic idea is that you take a body of text (here, all speeches) and break it down into sequences of words of a specific number (here, 3 words - but that's arbitrary) called an **[n-gram](http://en.wikipedia.org/wiki/N-gram)**. So a 3-word n-gram could be "Thank you to" or "cast and crew" or "Tommy Lee Jones." An algorithm (that [another Hacker Schooler wrote](https://github.com/amandapickering/markovgenerator) - thanks again!!) then collects every unique n-gram in all of the text, and matches/maps each one to a list of all of the words that follow it. So "Thank you to" would be mapped to "the", "God", "my", and anything else that followed that n-gram in the text. Once that's done, you can generate a seemingly random block of text - except it's only random in that it randomly chooses the words based on that previous mapping. So "Thank you to" might be followed by "the", "God", or "my" - but never by something it wasn't mapped to. It's much more complex than that, and I'm glossing over specifics, but [see it for yourself](http://thanktheacademy.herokuapp.com/) - it'll "randomly" generate a thank you speech for you, one that looks almost real because of the Markov chain being used, and you'll almost definitely never see the same one twice.

![image](https://78.media.tumblr.com/e39857b6600132fb84b39e5d8d063bbd/tumblr_inline_nk1ebeMr521t8beow.png)

Second, I did a [bit of analysis](http://thanktheacademy.herokuapp.com/analysis) on the length of the speeches. There are two interactive visualizations - one for the length of every single speech since 1966 (data before that is a bit spotty) and one for the average per year. You can see (above) that, on average, speeches are definitely getting longer, at least by number of words - especially when you include Honorary speeches (those are getting exactly as long as you think - aka REALLY LONG - calm down, D.A. Pennebaker). 
![image](https://78.media.tumblr.com/d179c3f86665a12fd7f06c46befa2a98/tumblr_inline_nk1eezhymt1t8beow.png)

You can also see how long individual speeches are, and filter for particular categories. The one above is Best Picture - if you hover over any of the bars you'll get all of the associated info - for Titanic. (Shock, they went super long too.) You can even click on "Speech (click to show)" at the bottom to actually see the speech, or be taken directly to the Oscar website entry for that speech (if you're tryna watch that D.A. Pennebaker speech - hint: it's so long they don't even have the full video). 

Overall, this has been a really fun project - but also somewhat frustrating/against what I know is best for my learning. I spent too much time on styling, on data cleaning, on interactivity, and ultimately feel like I could've learned more by diving into one particular thing. What's more, I know this hasn't been great in that I worked alone on it - Hacker School is especially good as I am surrounded by other programmers, and they're all willing to work together on really cool projects. I somehow keep finding myself drifting back to working on my own. Ultimately, it makes for projects I want to work on - usually movie-related, clearly - but also leads to me getting lost in my own head, going down rabbit holes, and not focusing on what would be best for learning. I'd like to make a concerted effort in these last few weeks to work with others on projects - even if they're not exactly what I want to work on.

Until then, happy Oscars!!!! (if you don't celebrate, enjoy the weekend, I suppose)