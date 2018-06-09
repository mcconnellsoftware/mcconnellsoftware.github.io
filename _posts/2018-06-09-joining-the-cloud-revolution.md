---
layout: single
title:  "Joining the Cloud Revolution"
date:   2018-06-09 12:21:29 +0000
tags: Misc
---

Disclaimer - it's mid-2018, and "Cloud" started a long time ago. Many years ago. I know this; I'm a relative latecomer 
to the party. Here, then, I don't pretend to champion something new and bleeding edge - I'm just presenting my own thoughts
as I gaze from the near-bottom of the learning curve and strap my climbing gear on!


# Setting the Scene

Right now AWS is very much an established player, but Kubernetes - [Greek, from which "Governor" and "Cybernetic" both stem, apparently, which is apt](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/#what-does-kubernetes-mean-k8s) - is 
increasingly being lauded as the "winner" in the containers arena, and quite plausibly. 

My take: AWS offers a rich - overwhelming to the newcomer? - set of out-of-the-box services, true to the longstanding 
vision of technology being comprised of "building blocks" which one combines to form overall "solutions", or systems. 
AWS is doing very well, it's widely used, widely respected, and is building up traction in one key area: the job market, 
where ads in my part of the world often indicate its use.

Much of the industry buzz however seems to be around _containers_, with Docker, Kubernetes and 
the [Cloud Native Computing Foundation](https://www.cncf.io/) being well at the forefront. Indeed AWS and other providers 
more "Platform as a Service" than "Infrastructure as a Service" are all also making sure they support Docker and containers.

The upshot is, no matter which provider you're working with, containers are pretty hot right now.


# Containers...?

"Containers" is a new thing to me; I've been working with physical servers and VMs for the past 20 years, and I'll 
freely admit that term pretty much crept up on me. And looking online for "Explain Like I'm 5" explanations yields a lot
of stuff from people that have plainly _never_ spoken to a 5 year old. 

I'm really not up on the finer points but like much in the world of technology a rough abstraction/concept perhaps 
suffices for now: I think of them as ultra-lightweight alternatives to VMs - but they are still "virtual instances". 
A container though doesn't have the full weight of say a Windows or Linux OS inside it, rather it stands apart and builds 
on the parent OS.

For example - and bear with me, consider all this a rough sketch begging for correction - one could imagine deploying 
a system with apps running on 5 x 1Gb RAM VMs, 100Mb for "app" and 900Mb for "OS/kernel/etc", total footprint being 5Gb. 
But imagine instead deploying 5 x 100Mb "app" containers on a host/parent with 900Mb: total footprint becomes just 1.4Gb. 

This as far as I'm concerned is the big win: really small units of deployment where scaling up to 5, 10 or 50 container 
instances remains hugely efficient.

And that's where the famous "Container Orchestration" phrase comes in: if one is to quickly, elegantly, safely ramp up 
and down large numbers of containers, one needs a bloody good set of usable and simple tools to handle that or one is 
going to make a right mess. Considering Kubernetes "The Guv'nor" makes a lot of sense in that regard.


# Supporting Factors

Let's say we have a super simple app that calculates a square root of a random number in an infinite loop. It's easy to 
imagine that running in a little virtual world somewhere. It's also easy to imagine we might want to run more of those 
neat little _SqrtCalcer_ apps ("why" is another matter of course...). So, great, ramp the instances from 1 to 20. Easy. 

But of course very few real world applications live in quite such a pure computation bubble: components need input, they 
produce output, they record changes, and they interact with their little component friends and even the wider world. 
And much of what "real world applications" pre-cloud and pre-container take for granted brings with it a set of 
challenges, not least durable file systems: when you can't even write your log files to /var/tmp with any guarantee 
they'll survive the night you need to find alternatives. If the promise of containers is super-simple create, destroy 
and scale-up/scale-down, it becomes clear that one mustn't rely on any one running container to be anything more than 
some transient borrowed processing power. 

Same for database access: sure you can run a database server on a larger-sized container, but you need to park your data 
somewhere, and that somewhere needs to be reliable, available, durable, etc.

Networking and security considerations come into play: how do containers talk to one another? What manages them and 
how? How is data from and back out to the wider network handled? How are communications secured, in terms of both 
authentication and authorisation?

I won't go into too much depth in this brief piece, but it should be clear that additional support is needed here: 
to gather and make available output logs; to coordinate lifecycle events (start, stop, etc) for containers; to provide
the durable storage we need in so many areas. And that extra support pretty much directly implies extra complexity, 
really it can't _not_ mean extra complexity. 


# Systems Engineers vs Application Developers

DevOps, Full Stack Developer: trends that I think ride roughshod over the fact that - very often - people 
enjoy working on one part of technology rather than others, and their strengths develop accordingly. I've often worked 
in groups where the demarcation between application developers, system engineers, and DBAs is very clear, and I've 
found it has worked well. 

Sure, "specialisation is for insects", but every single one of those engineering disciplines is potentially large and 
complicated enough for one person to immerse themselves in and devote an entire career to mastering. One does not, 
contrary to the book publishing world's view, master C++ development in 24 hours.

Some talented people seem able to execute well in all those areas, and well done to them but expecting most software 
developers - to whom writing a bug-free implementation of FizzBuzz remains a challenge, remember - to cover all those 
disciplines with any _significant_ level of competence seems ill-judged, I would argue. 

What's my point? Simply that given the new complexities and challenges that running a multi-containered application 
involve are going to need a pretty special set of skills to get right. And I'm not sure it's a set of skills that 
application developers necessarily have, or - once the lustre of the shiny and deeply fashionable new technology 
fades - actually really _want_.

What do I mean by that? Simply that for many application developers, job satisfaction comes from being immersed in 
a codebase; designing elegant, cleanly-coded classes or functions; choosing good processing algorithms or data 
structures; implementing complicated calculations with a deft simplicity; protecting data from accidental abuse; 
tracking down bugs with techniques honed from years of practice; choosing where to place logging outputs to allow 
maximum clarity of forensics and monitoring. The list goes on, and of course I don't speak for anyone other than myself, 
but I hope it's clear that _Things Developers Find Rewarding_ and _Things System Engineers Find Rewarding_ don't 
necessarily overlap.  

Application developers do of course need to design and build appropriately to their architecture: coding away, 
oblivious to a generally distributed architecture, isn't really on.
 

# Those Who Forget History...

...are famously condemned to repeat it. A lot of the container solution buzz right now reminds me of the J2EE, EJB 
situation nearly 20 years ago. The Entity/Session bean implementation of early 2000s was heavily flawed - ain't hindsight 
great - but much vaunted by the industry at the time, and human nature being what it is, everyone in the Java ecosystem 
soon became convinced that EJBs on fully fledged J2EE app servers was the only way to go. Servlets? Pah. All in for EJBs!

So we all duly learned about EJBs. Chapter 1 of the Sun Microsystems guide pretty much warned us what was coming by 
talking about all the roles involved: developers, deployers, configurers. More or less: get your team of 60 together 
now folks, we've an application to build! And my God: they had the boilerplate XML to need it!

Long story short: over-complicated technology that most teams didn't fully understand or handle well, leading to even 
simple CRUD apps being deployed in vastly over-architected distributed balls of mud that then ran like _utter 
sludge_ (so everyone moved to Tomcat and Spring instead, and lived happily ever after; the end.)

Containers are not EJBs; the comparison only works so far. But some of the risks apply: people focus on using Docker 
and containers for their own sake, perhaps as a form of Resume Driven Development but more likely because we as a group
just really do enjoy _playing_ with new technology and we'll often jump at the opportunity to do so - often losing sight
though of the big picture: process efficiency, and ease of handling large scale and great swings in demand.    


# A Cambrian Explosion

We're at a VHS vs Betamax point in time. Companies are fighting it out to see who will survive in this billion-dollar 
marketplace. Docker and Kubernetes and containers seem good technologies to bet on, but our industry tends to 
consolidate around a small number of big players, and right now there are a lot of parties involved in trying to end up
being one of them.

At the end of the day cloud and container technology is there to help us efficiently solve real-world application and 
business problems. And for every discussion on Hacker News about the great gains realised, there's one complaining about 
the time spent nursing a complicated deployment instead of building actual applications - and 20 more people then 
berating them for not using Cabbage or RatBagger or OoberScoober Container Magic or whatever other of the 10 OSS "supporting 
tools" has emerged this week (anyone else remember XDoclet? If you need tools to manage your tools, you're just possibly 
doing it wrong...).

Some predict, and I happen to agree, that whatever ends up "winning" is likely to be based on Kubernetes but wrapping it
in a way that makes it _truly simple and accessible_ to the legions of time-pressured application developers to whom 
"secure-ftp helloworld.war to /home/produser/webapps on prod-server-emea-01" is the benchmark (and why not) for 
acceptable deployment complexity and overhead.

There is of course a tension there: the more proprietary one company makes its "wrapper", the less "standard" it 
becomes, and lock-in, non-standard offerings may struggle to compete for that reason. Frankly, I'm quite glad it's not 
my problem..!


# Finishing Up

This cloud business is evolving very quickly, but learning Docker, Kubernetes and general container concepts is a 
pretty good bet.

Be mindful that "system engineer" can be quite a different path to "application developer". Don't feel bad if you find 
you'd rather be coding and debugging large codebases or building elegant Web UIs than working with small scripts and 
connecting components - there's a definite argument to be made that Kubernetes and related technologies are for the 
system engineers.

Watch carefully for signs any project you're working on is veering towards an over-engineered EJB style mess; warning 
signs are:

- it runs far more slowly than you all know, deep down, it really ought to

- getting everything even up and running OK, and correctly communicating from one component to another, is _difficult_

- making simple but nevertheless "across the whole application" level changes are inordinately expensive, e.g a new 
field on a core class or entity

- no-one can work out what's going on in terms of Request 123 making its way through the various components because 
the logging and tracing just isn't there

Projects don't _finish_ on go-live day; in many ways that's just the beginning. Make sure you are building something 
which can grow and change elegantly over 2, 5 or even 10 years.

Don't be fooled into thinking that just because many teams are choosing certain technologies there aren't 
better - sometimes simpler - alternatives!

I think the "summary of my summary" is really: look after yourself in this brave new world, enjoy the genuinely 
exciting new technologies, but watch out for the pitfalls!
