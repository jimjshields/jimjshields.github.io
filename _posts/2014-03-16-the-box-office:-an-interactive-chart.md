---
layout: post
title:  "The Box Office: An Interactive Chart"
date:   2014-03-16
categories: movies, data, movie tickets
---

In the spirit of never making anyone look at an ugly, boring Excel graph about
movies again, I've learned the (very basic) basics of [D3](http://d3js.org/)1
\- effectively, I can make interactive graphics. The hope is that I can use
this to make these posts more engaging, while also including significantly
more information than I could otherwise.  
  
Blogspot/Blogger, while great (and free), doesn't allow for Javascript - which
these use - so I am hosting all of this at my very own website -
[1.37:1](http://interactive.137to1.com/).  
  
After practicing a bit, the first thing I made was an area chart of the
domestic box office over the last few months. It's really a follow-up to my
last post - it takes the gross of all movies on a given day as a percentage of
the total gross in that day. But now you can actually see what makes up the
chart - and see, for example, how _The Hobbit_  made up about half of the
money spent on its opening weekend, but faded fast, while _Frozen's_ run has
lasted for months.  
  
The second thing I added was several ways to look at the data: by Movie (like
above), by Studio, by MPAA Rating, by Genre, and by Month of Release. You can
click any of those titles to change the chart to that classification. This
data is all taken directly from Box Office Mojo - again, they do a great job
with storing all of this data (though their genres need a little work).  
  
For example - here I'm looking at how much of the domestic box office revenue
was accounted for by PG-13 movies (after clicking MPAA Rating):  
  
  

[![](http://2.bp.blogspot.com/-TjsJRgmUF0c/UyYz9TZkWhI/AAAAAAAAAJ0/qMhim5YdqdQ/s1600/rating.png)](http://2.bp.blogspot.com/-TjsJRgmUF0c/UyYz9TZkWhI/AAAAAAAAAJ0/qMhim5YdqdQ/s1600/rating.png)

  
Month of Release is the one I wanted to highlight - it shows the gross
accounted for by movies released in a particular month.  
  
  

[![](http://1.bp.blogspot.com/-pi-
iLumrU6Y/UyY1_LsRw8I/AAAAAAAAAKA/I3YOUe6VmrY/s1600/releasemonth.png)](http://1.bp.blogspot.com
/-pi-iLumrU6Y/UyY1_LsRw8I/AAAAAAAAAKA/I3YOUe6VmrY/s1600/releasemonth.png)

  
All of these would be much more interesting over a much longer period of time,
but this one would be more than anything. It's really showing two things: how
well movies released in one month do in the subsequent months, and how poorly
movies do in their month of release. In the chart above, the dark green is
December movies, and the light green is January movies. Not a shock to anyone
- movies released in January are generally expected to perform terribly (and
are usually, with some exceptions, terribly received), and movies released in
December are generally either pushed for the Oscars or expected to be
blockbusters. But, it's another thing to have the numbers verify that.  
  
Again, this is a short timeframe and has very little to say in the way of real
trends across time. There are only around 50-100 movies regularly tracked in
the domestic box office - a relatively small sample size - and the list only
incrementally changes. Moreover, the makeup of the box office changes
drastically from month to month and from season to season; January looks very
different from March, and spring very different from summer. That makes it
harder to intuit real changes - you'd need to look at multiple seasons and
years for true trends to take hold. But that, in short, is one of the major
points I'm attempting to investigate.  
  
________________________________________________________________________  
Data source: [Box Office Mojo](http://www.boxofficemojo.com/)  
  
1Not [this](http://www.imdb.com/title/tt0116000/) D3.

