---
layout: single
title:  "Make it Fast: The Underrated Rewards of Performance Tuning"
date:   2018-07-04 12:21:29 +0000
tags: Misc
---
**Optimising software needn't be a chore or a drudge - consider it an opportunity for some rewarding detective work!**

Many will be familiar with "Make it work; make it right; make it fast", generally attributed to Kent Beck. The "fast" 
bit trails like something of an afterthought; unlike its siblings it feels kind of _optional_, in practice anyway if not 
in the perfect world in which such advice lives.

Let's face it: for those of us in the commercial world time to market is often crucial, and "Add feature 2" tends to
beat "Improve feature 1" in prioritisation decisions.

But right now I'm not looking to consider pragmatism vs purism, or gold-plating vs turd-polishing (!) - we all know the 
trade-offs that happen in real life: decisions are made; stuff gets done in way too much hurry; junior devs don't get 
the support they need; new and unproven tech stacks are inflicted - how hard can it be eh...?

I'm writing today instead to celebrate the sheer unalloyed glory of a successful performance deep-dive and fix - to 
revel in the purity of such a task, and exult in the unqualified satisfaction that comes from cutting tens, hundreds 
or even thousands of milliseconds off an operation! What triumph! I've been doing quite a bit of this in recent client 
engagements and as well as having the stubbornness and tenacity to be pretty damn good at it I've found it rather an 
enjoyable way to "add business value".

So what's so good about it, exactly?

First some caveats: 

Caveat 1 - any boss type, pointy-haired or otherwise, wandering over at 11am and demanding a fix by 4pm isn't 
conducive to an enjoyable session; this kind of pressure takes all the fun out of what is clearly an artistic and 
creative process. Avoid such people. 

Caveat 2 - try to fix problems in code which other people wrote. We're not looking to blame-storm, but if _your_ work's 
all in Component X while _all the issues_ are in Component Y, there's zero downside: you are not at risk of uncovering 
your own dirty little secrets. And if you don't really find anything, well, that's sort of OK, it wasn't your fault in 
the first place... (ahem).

So, groundwork done: you have unlimited time to find someone else's mistake. Happy days. Let's proceed.

Main reasons this kind of task can be deeply rewarding, then:

- it's a great chance to make your team's product unambiguously - and measurably - _better_, most likely in a area 
of enough importance to justify its priority being higher than adding new features or fixing other known bugs 

- there's no politics or negotiation to consider (if there is, your organisation may be a bit broken) - or if there is
it's the net positive of announcing the "wins" (be wary of announcing the non-wins!) to the wider team

- it's an easy sort of task to become deeply immersed in; hours can pass while you sit sifting logs, correlating 
timings and frequencies against code, trying to build a narrative of _what's really happening_; this sort of state is 
known as [Flow](https://en.wikipedia.org/wiki/Flow_(psychology)) and well worth reading about - jobs and tasks where 
you achieve this state tend to be ones you enjoy more 

- it's a very pure challenge: you have one goal to work towards, and you can channel all your skills towards it - and 
build new ones too if you're lucky!

- by definition if you're investigating an area then it's not well understood (by you, anyway - yet) so you'll 
inevitably end up learning a lot more about that area - and that's no bad thing

- you probably know when you're done; getting an operation down from 1,500ms to 30ms may or may not be carved in stone 
as "the requirement" but once you're there you know you've nailed it


# Where Should We Look?

Experience suggests the following candidates, in severity order:

1 - the database 

There we go; done. Look in your database and/or how your application or services are using it. That's where your 
problem is. You're welcome.


# The Tools for the Job

There are sophisticated tools in the monitoring world but honestly the basics are all you need:

- access to complete log files and the ability to add new log entries

- the codebase and the ability to make diagnostics changes - a cheeky `log.info("Got here 123!")` can work wonders in 
the right place! (always remove it afterwards though; we're not savages...)

- the ability to conduct runs and experiments - either locally with zero friction, or even by deploying - safely - to 
production to get extra log instrumentation into play 

With the above you have all you need to conduct your experiments: add logging till you know exactly what is happening, 
write scripts to extract meaningful patterns if your volumes prohibit intuition alone from gleaning the key facts, and 
really just keep iterating until you know what's taking place.


# Macro vs Micro Issues

Sometimes your issue is a tiny bad SQL query running in a component. Sometimes it's a perfectly good SQL query but 
it's being run by 40 threads in 15 parallel application instances. Be mindful of this difference.

(Like I said, it's still always the database...)


# Low-hanging Fruit - A Case Study

Don't make the mistake of assuming any issue is going to take weeks of micro-analysis: sometimes there are huge wins 
just waiting to be found. "Packs of watermelons hanging off the leaves" levels of low hanging fruits. Don't count on 
this of course but do yourself a favour and look out for them before you look for the harder gains.

Here's an example.

15 years or so ago, the firm I worked with was basically "gifted" a government client from another development shop. 
The original developers had built a form of contact management system for a small number of high value contacts: 
it _worked_, it was _correct_, but sweet chocolate teapots was it _slow_ - it barely functioned _at all_. 

One page - "view contacts" - showing names and email addresses, for example, would take 10 minutes to load. There were 
a couple of thousand contacts: it probably worked great for the 5 "test" entries, maybe the next 50 real contacts. But 
very quickly (ha) it then went wrong. 

And the original developers couldn't fix it. They tried, they couldn't find the problem, and to their credit they 
helped their client find someone else who could.

Long story short: yeah it was the database. A dumb ORM interaction with the database to be precise. Each Contact had 
one or more Company objects, and those had Location objects - and the ORM was doing what dumb ORMs do unless you advise
them otherwise and fetching the child objects _one by one by ID_. We quickly measured something like:

1 query to find the 2000 Contact entries
2000 queries to find the Company entries one by one 
2000 queries to find the Location entries one by one

The irony was the page didn't even use the results from those other 4000 queries: the code loaded the entire object 
graph, ignored most of it, and spent many minutes doing so. We replaced it with a simple hand-crafted SQL query and a 
simple result handler and the "view contacts" page loaded pretty much instantaneously. 

The moral of the story here isn't about ORMs (but, wow, therein lies a topic) or even Knowing One's Tools - it's about
looking for the simple stuff first because sometimes even in the incredibly sophisticated world of software, 
optimisation isn't always about squeezing the last few ounces of horsepower from the red-lining engine, it's just about
_releasing the handbrake before putting your foot down_! 


# Some Further Reading

It's not really super relevant but _Zen and the Art of Motorcycle Maintenance_ has some interesting parallels to 
performance tuning and debugging in general: the focus one finds in trying to determine root causes, the need to know 
one's tools and develop a wider understanding of the overall system/engine. It's a classic - not the easiest read but 
not the hardest - and well worth a read for anyone with a slightly philosophical bent!
