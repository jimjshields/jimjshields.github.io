---
layout: post
title:  "Cats (2019), Feedback Loops, and Programming"
date:   2020-05-26
categories: Cats, movies, programming, devops
---

## Intro

I gave a version of this talk a few weeks before coronavirus, and meant to adapt it into a blog post well before now, but I probably would’ve procrastinated on it in the best of times so I think this is a pretty good turnaround!

Fair warning, this is one of those posts where the author stretches a metaphor to its breaking point. 

I think there’s a lot to learn about programming, specifically in establishing feedback loops, from the constraints on movie production. _Cats_ (2019) is a recent and obvious example of this (also seriously considered _Sonic the Hedgehog_ (2020)).

DISCLAIMER: I haven’t seen the movie _Cats_, the musical _Cats_, read the collection of poems _Old Possum’s Book of Practical Cats_, and have no personal stake in the multi-billion-dollar _Cats_ empire. I’ll really try to stay objective about the quality of all _Cats_ media.

## A Brief History of _Cats_

_Cats_ was a movie released in 2019 to widespread confusion. It didn’t spring from nowhere; it has an 80-year history. First was T.S. Eliot’s _Old Possum’s Book of Practical Cats_ (1939), a collection of fanciful, cat-related poems he wrote for his godchildren. 

<p style="text-align:center">
    <img src="https://pictures.abebooks.com/isbn/9780156685689-us.jpg" alt="Good Old Possum" height="400px"/>
</p>

Then there was _Cats_ (1981), Andrew Lloyd Webber’s stage musical based on the poems, which was an enormous hit — Broadway’s longest-running show of all time until the mid-2000s, grossing $3.5 BILLION worldwide (one source has it as the highest-grossing show of all time; I couldn’t confirm it but it gives a sense of scale).

<p style="text-align:center">
    <img src="https://bsp-static.playbill.com/dims4/default/ea8f643/2147483647/resize/x250%3C/quality/90/?url=http%3A%2F%2Fpb-asset-replication.s3.amazonaws.com%2Fe6%2Fb4%2F827726c645b9a817ab0e4bdea8a1%2Fcats-playbill-2016-07-14-web.jpg" alt="I chose the logo on purpose; you can look up pictures of the production, they're kind of scary" height="400px"/>
</p>

In the mid-90s, after the huge success of the musical, [Steven Spielberg’s animation company wanted to adapt _Cats_ into a movie](https://www.forbes.com/sites/marchershberg/2019/12/20/how-a-dog-film-killed-an-animated-version-of-cats/#43f788a8beb8), but the writers struggled to adapt the story (essentially a series of introductions to different whimsically-named cats) into a traditional 3-act movie structure. They failed; the animation company folded; the rights for _Cats_ went to Universal and lay dormant until 2013, when the movie adaptation of Les Miserables was a huge international hit and made musical movies bankable again. Universal decided to start up the old _Cats_ train again, and hired Tom Hooper, the director of Les Mis, in 2016. He adapted the screenplay and started production in 2018, hired a bunch of very famous (Taylor Swift) and reputable (Jennifer Hudson, Idris Elba, Judi Dench, Ian McKellen) actors, and they shot the movie. 

## Feedback Loops in the Production of _Cats_ (and All Movies)

During the production of a movie until the theatrical release, there are a few critical feedback loops: [*dailies*](https://en.wikipedia.org/wiki/Dailies), *trailer releases*, and [*test screenings*](https://en.wikipedia.org/wiki/Test_screening). Importantly, though, there’s only one place feedback actually matters: the *theatrical release*, where people either pay to see the movie or they don’t. Once it’s released (though _Cats_ is a special exception here), there’s no longer a feedback loop — the movie is locked.

Dailies are the “raw, unedited footage” shot during movie production, and usually viewed by the director (and maybe some cast and crew) the next day. _Cats_ was heavy on visual effects, which were added after production (in post-production), so its dailies likely weren’t reflective of Tom Hooper’s full vision. I also can only speculate how this feedback loop worked for _Cats_. But they are the first important loop, where the director can make adjustments to performances, production design, cinematography, etc. based on how the footage looks.

Trailer releases are usually the first public feedback loop: the ultimate audience is reacting to (heavily edited, but usually fully produced) footage of the movie. On July 18, 2019, the world changed when [the _Cats_ trailer](https://www.youtube.com/watch?v=FtSd844cI7U) was released. It “received overwhelmingly negative reactions from viewers,” mainly due to the mix of live action and CGI, which hovered around the [uncanny valley](https://www.youtube.com/watch?v=FtSd844cI7U). Not all trailer releases are a full feedback loop; often the movie is mostly locked prior to the trailer. But for _Cats_, the reaction was so strong that they had to rework much of the VFX.[^1]

Test screenings are typically the last feedback loop for movies, and can be valuable in responding to audience feedback by cutting out scenes that don’t work or even changing plot points that test poorly. I couldn’t find any evidence of test screenings for _Cats_, likely because of the rushed schedule.

On December 16, _Cats_ had its world premiere — Hooper said he’d finished the film "at 8am the previous day after 36 hours in a row" (not normal!). On December 19, it’s released to critics, who aren’t kind (currently at 21% on Rotten Tomatoes). It finally had its theatrical release on December 20, and was expected to make $15 million its opening weekend (abnormally low for a movie this “big” released on the weekend before Christmas). It made $6.5 million, good for 21st worst wide opening of all time.

On the Sunday of its opening weekend, Universal did something “unheard of” for an already-released: it sent a “patch” of _Cats_ to all theaters! _Cats_, in effect, created a new feedback loop for movies by releasing a new version after the public reaction. The patch was to address some VFX mistakes like this gem, where you can see Judi Dench’s real hand:

<p style="text-align:center">
    <img src="https://www.nydailynews.com/resizer/nxSaCm1DMoC4OnKUyATuMhm5ERg=/800x657/top/arc-anglerfish-arc2-prod-tronc.s3.amazonaws.com/public/S2QFGAKIKNDKTOAHR4JYRSSH2U.jpg" width="500px" alt="A terrible merge conflict"/>
</p>

By the time its run ended, it made $27 million in the US, and $73 million worldwide, against a $95 million production budget and rumored $100 million marketing budget. It was supposed to be a major Oscar contender; after its failed release, it was pulled from contention and garnered zero nominations. It was an unqualified disaster.

## Feedback Loops in Programming

Movies try to build in feedback loops, but they’re deprived of the most important one: the feedback from a *paying audience*. _Cats_ is the only example I know of with a second version released in the original theatrical run.

Because of this constraint on movies, I think they’re a perfect counterexample to programming projects: you’re (probably) not making a movie, so you should strive to build in the feedback loop from your “paying audience” (your day-to-day users) as quickly and as often as possible.

Programming also has other feedback loops that correspond nicely to those in movies:

*Writing tests* for your code is a lot like viewing the dailies: it usually doesn’t tell you that the whole project is working, but gives you quick and critical feedback on an isolated piece. 

*Giving a demo* of your project is a lot like releasing a trailer: it’s a great chance to market the best parts of your project, hide the non-working details, and get feedback on your approach. 

And *releasing your code to staging or QA* is a lot like doing test screenings: you get real feedback on the whole project, though not from a paying audience (test screening audiences are usually self-selected and don’t pay, just like staging / QA users are likely not 100% representative of your paying audience).

But there’s no feedback loop as important as *releasing your code to production* to your paying audience. Releasing often is a critical practice and goal of the [DevOps movement](https://en.wikipedia.org/wiki/DevOps), supported by the annual [State of DevOps surveys](https://services.google.com/fh/files/misc/state-of-devops-2019.pdf) (and the companion book, [Accelerate](https://itrevolution.com/book/accelerate/)), and is shown to be a strong predictor of engineering team performance.

So build in this feedback loop as early and often as you can (if you can), because you’re extremely lucky not to be working on a movie, where you won’t know for months or years whether it’s truly any good.

## Epilogue

By January, _Cats_ had [already found a second life through midnight screenings](https://www.wbur.org/artery/2020/01/23/tom-hooper-cats-midnight-screenings). It didn't make back Universal's $100 million loss, but bodes well for its future as a cult classic, like [_The Room_](https://en.wikipedia.org/wiki/The_Room). I don't think your programming project could someday become a cult classic... but you never know!

[^1]: This kind of VFX usually takes a year or more, and the studio gave them 8 months so they could release it in time for Christmas — the VFX team was put in an absolutely admirable effort through a horribly rushed schedule and were [mocked at the Oscars](https://www.indiewire.com/2020/02/academy-awards-visual-effects-cats-rebel-wilson-james-corden-1202210749/) for their work. In a disturbingly similar story last year, the Sonic the Hedgehog team somehow [responded to the trailer backlash by turning the movie into a huge success](https://www.vulture.com/2020/02/the-sonic-the-hedgehog-controversy-and-redesign-explained.html), but were also put through a dreadful work schedule and were [ultimately shut down](https://screenrant.com/vfx-studio-mpc-vancouver-shut-down-closed/).