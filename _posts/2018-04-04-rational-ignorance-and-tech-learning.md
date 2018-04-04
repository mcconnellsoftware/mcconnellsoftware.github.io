---
layout: single
title:  "Rational Ignorance and Technology Learning Challenges"
date:   2018-04-04 12:21:29 +0000
tags: Misc
---
"Rational ignorance" is where the cost of arriving at a suitably informed, educated position outweighs the benefit of 
doing so. In other words, it's better to not bother.

For example, say you're torn between buying one digital alarm clock at £10 and another at £12. They seem pretty similar
but it's likely you'd spent 2 hours researching their features to make sure you definitely get the best one for your 
particular slumber-spoiler needs. If you value your time at perhaps £11 per hour, then £22 of research cost for a 
product difference of £2 seems excessive. You could even buy both for that amount.

So the concept should be pretty clear: for some things in life it's truly _just not worth_ becoming an expert - not a 
proper expert anyway. This doesn't mean you must stumble blindly from crisis to crisis: there's clearly a difference 
between spending a few days learning about mortgages and financial terms when thinking of buying a house, and getting a 
degree in economics and a doctorate in mathematical risk modelling just to make sure that £299 product fee on your 2 
year tracker mortgage doesn't ruin your life.

There's a balance, basically. Learning in moderation. And if you get it right, you'll probably end up making some good 
choices in life - splendid!

Incidentally it's not always naturally-occurring, or accidental: here in the UK energy companies love to bewilder 
consumers with tariffs designed, when taken as part of a wider "who should I switch to?" evaluation, to make it so hard
to pick the right provider that people either abandon their endeavour, or just pick one to get the whole exercise over 
and done with.

[Why are energy bills so complicated](http://www.thisismoney.co.uk/money/bills/article-1715782/Why-are-energy-bills-so-complicated.html)

What I've been contemplating lately is Rational Ignorance in the technology realm: specifically, new technologies and 
languages.

## Change in Software Engineering

Software engineering, software development, programming, coding, technology, "digital" (ick) - call it what you want,
it's notorious for its rapid pace of change. That change is not always evolutionary: one doesn't _always_ simply move 
from Java 7 to Java 8 and thence Java 9, etc. Sometimes new languages emerge, new paradigms, new architectures. 

Some of them catch on, some don't. Some simply put a shiny Web 2.0 on something that's trendier - _but worse_ - than 
its predecessor. Some are technically brilliant, but die in tragic acqui-hires. Some are flawed and badly executed and 
ought to be taken out and shot, but plentiful investment and strong marketing get them - eventually - over the quality 
hurdle to the point they become genuine contenders. 

All of that presents a challenge to the professional practitioner, because to keep abreast of everything that emerges 
in this field - to the point where one can make an informed choice about which are the "winners" - does seem to be one
where our Rational Ignorance premise applies, at least a little. Bluntly, the cost of spending huge swathes of one's 
time in exploring the never-ending stream of New Stuff to the point where one can actually reach an informed viewpoint
seems to significantly outweigh the benefit one gains, certainly in any serious software development role where 
significant projects can last several years.

In other words, why spend one's evenings learning the latest and greatest JavaScript frameworks when the day job 
involves working - happily and productively - on a monolithic Java application for collating insurance statistics? 

Look at this list of NoSQL databases, for example, on Wikipedia:

[Types and examples of NoSQL databases](https://en.wikipedia.org/wiki/NoSQL#Types_and_examples_of_NoSQL_databases)

Seriously who can possibly work through all that and decide: right, ZopeDB is the one for me! Better to just stick with 
SQL, perhaps.

## Rational Ignorance vs Always Learning

Learning new things - it's great! It's often fun, it's probably good for you long term (brain plasticity and all that). 
And plainly no software developer with hopes of any kind of career hits the age of 25 and then shuts off the New 
Information Intake pipe. 

So we have something of a conflict: there's too much out there to possibly learn, but we have to keep learning lest we 
become unemployably behind the times. 

This is something I must admit I struggle with a bit. In my time I've learned Basic, Pascal, C, C++, Visual Basic, 
Visual C++, Perl, Java, J2EE, Servlets/JSP, HTML, CSS, Spring, Struts, Groovy/Grails, Hibernate, Ibatis, MySQL, Sybase, 
Oracle, MongoDB, XML/XSLT, Splunk - not to mention half a dozen source control systems (and written one!), and as many 
separate IDEs. And all the other supporting stuff of course - build tools, O/S scripting, automated testing tools, proprietary 
enterprise ecosystems.

There's a fair amount there, and it's all stuff I've enjoyed working with (even EJBs, although we had the sense to stick 
with session beans to avoid the utter insanity of entity beans...). But it pales in comparison to the list of 
technologies _not_ listed! And I don't mean even the crazy tech nobody really uses.  

So can we resolve this conflict? How can _I personally_ resolve it?

## Strategies for Sustainable Learning

Perhaps key concepts here are balance, moderation, sustainability - and bit of good judgment. Without wanting to present
a _fait accompli_, perhaps it's valuable to just identify some techniques that combined might help to start tackling 
this area that probably affects a lot of developers, including experienced professionals with expertise so ingrained 
that risks becoming a rut:

- try to stay even just a little bit on top of trends: sites like [Hacker News](http://news.ycombinator.com/) are good
for including in a "morning news catchup"; don't overthink any particular visit, don't treat every language or 
technology article as a Must Learn About one, but rather treat it as a long term background-attention thing - browse HN 
a few times a week for 6 months and you'll probably end up having a pretty good sense of what's really going on in the 
industry, what's flash-in-the-pan versus what people are consistently talking about

- while avoiding an over-ambitious learning programme, do try to adopt some form of regular deep-dive learning activity;
that might involve signing up to a site like PluralSight and making time to watch some of their huge selection of video 
training courses, or adopting a quarterly tech book buying (and reading!) regime

- think strategically: you've spent time on HN and other online tech hubs, you've most likely been in some form of 
workplace, you've kept yourself in touch with the local job market - what technologies seem to be gaining traction? 
Which ones do job adverts ask for? Which ones can you actually practice at home - open source is a fantastic phenomenon 
for the democratisation of technology! This is actually an important one: don't scatter your learning energies anywhere 
and everywhere, be judicious and invest your time like the scarce resource it truly is

- if you're an employee rather than a freelancer or a company founder yourself, there's a good chance your manager can
help give you some direction, and perhaps even match it with course-based training allowances - covering both time and 
budget

- hands-on practice time is invaluable - if you're keen to learn a new language (rather than a tool), consider writing
a simple app which:
    - reads JSON or XML content from a filesystem file, e.g. a list of groceries, or bank account transactions
    - iterates over all the entries: filter some out, transform some of them, sort them
    - stores output data in a different format - converts JSON input to XML output for example
    - connects to a database, SQL or NoSQL, and performs both reads and writes using that database
    - uses (however "forced" it seems!) list, map, set data structures, helping you get a feel for how that language handles 
    them: cleanly, or with great fuss?
    - handles errors properly - exceptions, exit codes, whatever
    - lets you try out debugging and logging capabilities
    - uses multithreading

- (re)discover the pleasure of simply watching and learning - not every new technology needs to be completely absorbed 
and mastered - it's fine to simply "skim" articles, books, or videos

- stay away from front-end web development - that field changes its favoured frameworks on a daily basis and you will 
never, ever stay current no matter how hard you try (only half joking...)

- don't be intimidated by know-it-all colleagues - some people do have a genuine love of learning and applying new 
things, some just like to make everyone else think they know everything in the world (and often those latter 
types _can't actually deliver anything_)

- it's good to have a "learning phase" where you're actively brushing up your skills, and sometimes instead a 
"mastering" phase - or at least an "applying in real life" phase - there's nothing wrong with staying in our comfort 
zones sometimes! 

- look out for vacancies in teams using technologies you're interested in - often teams will be happy to have a keen 
learner if they can't find a ready-made expert, especially in more modern technologies; a little background reading 
and practice can't hurt of course

- don't ever try to learn _everything_; look at your sector, draw up a list of technologies and tools 
you think are honestly - and realistically - a minimum "need to know", and work towards acquiring those skills

## Ignorance - Not Bliss After All

In the light of a few pretty obvious strategies and techniques, it really shouldn't be too hard to keep one's 
skillset relatively current. Worst case any periods of neglect can realistically and systematically be tackled via a 
concerted programme of targeted active learning based on some specific "inputs" - what's in demand, what can be learned 
in one's own time, what's actually interesting, what seems to be "on the up" in the short to medium term?
