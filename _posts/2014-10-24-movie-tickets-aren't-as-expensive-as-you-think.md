---
layout: post
title:  "Movie Tickets Aren't As Expensive as You Think"
date:   2014-10-24
categories: movies data tickets
---

(I've finally got the [companion
website](http://onethirtyseven.herokuapp.com/) working. It has cool
interactive charts! Some of which I use in this post. But you can also [search
for any movie](http://onethirtyseven.herokuapp.com/interactive/movie_page/)
and get its daily box office, or [compare two movies at the same
time](http://onethirtyseven.herokuapp.com/interactive/multiple_movie_page/).
I'm working on improving those and adding more stuff - would love
suggestions.)  
  
The Dissolve had an [interesting article](http://thedissolve.com/news/3723
-charts-graphs-average-movie-ticket-prices-in-the-u/) this morning about
average movie ticket prices over time. I wanted to give some more depth to
that and visualize how the average movie ticket price has really changed over
time, and how that compares to the number of tickets actually sold each year.  
  
(I also covered this [at the end of 2013](http://137to1.blogspot.com/2014/02
/nothing-will-ever-beat-et.html).)  
  
A few disclaimers for the data:  
1\. To include 2014, I scaled the Tickets Sold number using the percentage of
the year we've gone through so far (so if the exact trend were to continue
through the rest of 2014). Imperfect, but it's just for comparison's sake.  
2\. I didn't include data before 1989. According to the NATO (National
Association of Theater Owners) [website](http://natoonline.org/data/ticket-
price/), prior to 1989, they're just using CPI.  
3\. To inflation adjust ticket prices, I used the [CPI
index](http://www.usinflationcalculator.com/inflation/consumer-price-index-
and-annual-percent-changes-from-1913-to-2008/) and scaled to 2014 dollars.
(Thanks to The Dissolve commenter who mentioned using inflation-adjusted
numbers.)  
  
Here's what I found -  
  
[Ticket prices have increased in most
years.](http://onethirtyseven.herokuapp.com/interactive/movie_tickets_page/#movie_tickets_graph)
(Blue line on that graph.) Not a huge surprise - that's the general consensus.
Not only are regular tickets more expensive, so the thought goes, but now we
have premium (3D, IMAX, RPX, similar scams) tickets too.  
  
[But, adjusted for inflation, ticket prices have barely
increased.](http://onethirtyseven.herokuapp.com/interactive/movie_tickets_page/#movie_tickets_graph)
(Same graph, red line.) Adjusted for inflation, the average ticket price in
1989 was $7.59. In 2014, it's $8.12. That's a 7% increase - as in, not a huge
change at all. The problem with this dataset is obviously the lack of
granularity - New York City tickets are probably increasing more dramatically,
likely due to rent increases well above inflation - but this gives you an idea
for across the US.  
  
[Year over year, the change in price is slowing
down.](http://onethirtyseven.herokuapp.com/interactive/movie_tickets_page/#movie_tickets_change_graph)
Year-over-year change in prices peaked in 1999. The 2013-2014 change in price
was the lowest since 1993 (adjusted for inflation, 2011 was lower - but both
were negative). This could be a result of the shift toward streaming, VOD,
etc. - but it's still very slight.  
  
[But people are going to the movies
less.](http://onethirtyseven.herokuapp.com/interactive/movie_tickets_page/#movie_tickets_sold_graph)
Number of tickets sold peaked in
[2002](http://www.boxofficemojo.com/yearly/chart/?yr=2002&p=.htm) ( _Spider-
Man, Lord of The Rings, Star Wars, Harry Potter_ , and _My Big Fat Greek
Wedding_ were the top five movies that year - all five of which, if adjusted
for ticket price increase, would've been the top movie of 2014). The
assumption that the end of 2014 will keep pace with the rest of the year isn't
fair - _The Hunger Games_ , _Interstellar_ , and _The Hobbit_ (among others)
will likely be big enough hits. But the trend is pretty clear - steady
increase from 1991 to 2002, steady decrease since then.  
  
The picture isn't as bad as I was led to believe - tickets aren't really that
much more expensive. But it's not great, either - people are just going to the
movies less. There's more to say on this; would love to hear anyone's
thoughts.

