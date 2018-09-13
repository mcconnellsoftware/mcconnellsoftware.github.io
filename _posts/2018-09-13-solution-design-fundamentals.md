---
layout: single
title:  "Sep-2018 - Solution Design Fundamentals"
date:   2018-09-13 12:21:29 +0000
tags:   Design
---
**Coming up with a solution design fit for use in large organisations can be a big ask - but breaking it down and 
spending time planning your approach systematically can help you design software which will succeed at enterprise 
scale.**

It's natural, when asked to start work on a new project, to focus on one particular area: _how to solve the main problem_.  

But a Senior Developer or Solution Designer should be contemplating far more than this for any project of reasonable 
scale.

All of the areas discussed here really need to be handled - but some of them, in some organisations, will be a "given",
with no project-specific thought needed whatsoever. If _Thou Shalt Use Git and GitHub_, great, one less thing to worry
about. But still be mindful of this as a topic for consideration, and one which - this time - has a super-easy answer. 
In the future that may not be so.

Don't worry about having to nail all of this 100% up-front, or about executing/solving all of it on your own - if you're 
working on an enterprise project, part of working effectively means delegating and distributing tasks, ideally to people
with a keen interest in that task. You don't need to write a 300 page "Solution Design Spec" either - your documentation
approach is your own to choose, but much of what we discuss here could be covered on a Wiki page if it even needs that.

Some areas can be deferred - making decisions may not be possible up-front, for technical or local-expert-availability 
reasons, or various others.

To reiterate: working all of this out can - _should_ - be part of the project if it's anything other than immediately 
clear. It's not "work this out _then_ start the project firing pistol...".

A general approach worth considering here is one from the famous
[7 Habits of Highly Effective People](https://www.amazon.co.uk/Habits-Highly-Effective-People-Powerful-ebook/dp/B00GOZV3TM) - "Begin 
With The End In Mind". Simply put it means establishing early on a clear picture of what your eventual outcome looks like. 
For tech solution design, breaking that down into some manageable constituent parts is a really good idea. 
Can I really picture the Backup solution? The DR solution? As in, can I sit at my desk, close my eyes, and imagine _in 
detail_ what the shape of that will be? If so, great - you've probably got that covered. If not though, don't worry, and
be pleased that you've identified a part of your solution that you can tackle early on and assure good assimilation with
everything - not a bolt on a the end when it's too late for an elegant option.    

I highly recommend Stephen Covey's book, by the way; its style may be a little dated and idiosyncratic now but the core ideas, the seven 
"habits", have a lot to commend them.   

So - let's start to consider the key solution design areas we need to account for.


# Solving the Core Problem

I've stated earlier that this isn't the only thing to focus on - but obviously it's a pretty important one to include, 
so let's get it out of the way!

Whether it's a fairly pure computation with a known set of inputs, or whether it's about connecting existing systems, 
set a task to drill into this.

I don't mean you need to spend 6 months on a Detailed Design, specifying every last flow - just that you need a coherent
vision of what you're trying to do, and a reasonable grasp of how you're going to do it. Once you get to a point you're
comfortable with overall feasibility, or at least a plan for getting there, proceed.

Consider an elevator pitch: if you can explain it to an educated colleague and they don't look at you funny or ask if 
you've really thought about it, you're probably OK.    


# Project Life Span

"This project's going to last 4 years and 3 months" said no stakeholder, ever. But you do need to think about how long,
roughly speaking, you're building your solution to last: 6 months? A one-off data migration in a year's time?

Consider "T shirt sizing": 2 weeks, 6 months, 2 years, 5 years, 10 years+ are probably useful starting points: Extra 
Small to XXL sort of thing.

Why's this relevant? Simply put if you know you're being asked to design something that has to last and grow for 5 years
or more, you can justify spending more of your team's time and budget on certain early tasks: prototyping untested 
technologies, validating load and scale assumptions, evaluating 3rd party product options.

Similarly you can justify pushing back against certain constraints - not least deadlines.

This kind of conversation, by the way, can be a good way to raise topics which might not even have occurred to senior 
management: they might know they want a new Strategic Widget Management Solution and they want it within the next 6 
months and let's have no arguments about that - but raising the lifespan topic might be one way to register the possible 
false economy of rushing through mission critical software projects without enough time or budget to do them "properly", 
potentially even with some practice runs.

It's also the sort of conversation which, if _you_ don't raise it, may not ever happen. And that's a missed opportunity
all round.


# Key Risks

All projects have risks - some major, some minor. Some tech related, some people related, some timing related. It's a 
good idea to brainstorm your risks early on and classify them by impact (low, medium, high) and likelihood (again, low, 
medium, high is a good starting point).

Usual brainstorming rules apply - think of as many as you can: some will be thrown out, some mocked mercilessly, some 
will stick, that's fine!

Clearly _high impact, high likelihood_ risks are worth factoring fully into your project - can they be mitigated? Because 
they're _probably going to hurt you_.

For technology-risk and difficult logic/computation problems consider prototypes and proof-of-concept (POC) work. Nailing
your big concerns early allows you to confront the hard challenges - and if necessary adjust course before you're too 
committed (see: Fallacy of Sunk Costs).


# Version control, CI and Building

In enterprise environments much of this will often be pre-determined; architecture and standards groups may have already 
made your decisions. 

This can be a blessing or a curse depending on what those choices are. Hopefully it's more of a blessing and takes a 
reasonably unexciting set of decisions out of the picture - and brings a pre-existing set of dependency management 
standards and tools to the table too.

_Hopefully..._

Of course even in an organisation with such things already decided, actually _getting things working_ end-to-end can be a 
significant challenge: don't underestimate the complexity here. Getting a "Hello World!" using a few token 3rd party 
libraries fully "built" - and deployed somewhere - can be a significant milestone.  This can be frustrating: the thought
of taking 6 weeks to get a new "hello world" into production seems ripe for a bit of mockery. But for a truly large 
scale project expecting to carry 10, 20, 50+ person-years of effort, it's not really too unreasonable.

Things to consider:

- which version control system to use
- which build/CI system to use
- extracting your source code and compiling it
- pulling in dependencies, whether from external or internal sources
- how you'll update your dependency versions - and you should absolutely prefer _frequent, slightly-painful_ updates 
to _occasional and brutal_ ones!
- running automated tests
- scheduling builds on commit, and more formal "we're ready to build the official February Release" 
- automatic deployments to an environment - or environments, plural


# Development Tools and Standards

IDEs, text editors, coding standards - no project is really underway until the team's had a really good fight about 
this kind of stuff! Eclipse vs VIM, tabs vs spaces, where to put one's { and } and all that. Marvellous fun. And 
Windows/Mac/Linux developer OS of course...

Again corporate decisions may reign supreme, but if not then please consider truly how important a "one size fits all" 
tooling ecosystem really is. If blessing the use of anything-goes as long as the build - and test suites - remain in 
their happy places avoids religious tooling wars, great. Perhaps define a "preferred" tool set and anyone wishing to 
diverge is responsible for their own problems but otherwise welcome to do so.


# Logging, Traceability and Analytics

The benefits of well implemented logging are tremendous. Not only having the forensic capability to work out what went 
wrong with Customer 12345's order ID 56789 across 12 different microservices and the inherent detective work therein, 
but being able to use products like Splunk - which is _truly brilliant_ - to query logs methodically and easily, and 
produce reports, dashboards, charts of behaviours etc in more or less real time is quite a game-changing capability - 
and worth an article in its own right!

As with other areas there is no one-size-fits-all to recommend here: but do think about this carefully, not as an 
afterthought.


# Solution Sizing

This can be difficult, but it's vital to have a feel for solution sizing. What sort of traffic do you expect? How many 
users/customers? What data storage do you expect, e.g. per day, week, month? How long must you keep it? What data is 
disposable in the medium to long term, and what must be archived - and for how long? Can you establish time-targets, 
e.g. in 6 months the aim is XXX, 12 months it's YYY then 24 months ZZZ? 

In some ways it's not so critical to get these 100% accurate, per se, but to get buy-in for your projections. 

And err on the side of caution - in this area, success beyond projections can be a real problem. If you've planned for 
growth doubling after 12 months and you hit that milestone after just 2 you could be in serious difficulty. So always
build in contingency, by a factor of _at least_ 2 - 100% difference, not 10%.

And have a concrete plan for growth - more compute power? More storage? If you're starting with a product catalog of 
1,000 items marketed in one country alone but you know you plan to roll out _globally_ with a catalog of 1,000,000 items 
you need a plan beyond just buying more RAM and a bigger SSD.  


# Error Handling

You might think this an odd one to consider at a solution design level: what to do with exception is usually an 
interview question about checked-or-unchecked. But it can be a significant architectural question: if your system 
is 4th in a chain of systems all contributing to "Organisation Event XXX Is Happening" and you are the one whose 
database chooses to go pear-shaped, what should happen?

Maybe you are a purely UI operation in which case a user-friendly - but security-aware - error message may be 
acceptable. 

If you're a pure REST API responder, apt error codes is probably a clear answer, albeit you should certainly be thinking 
about transactionality and rollbacks.

You may, when push comes to shove, be tempted to ignore this, certainly in the short term if you're feeling a bit 
overburdened by other challenges, but the sooner you confront it the better - and the easier it will be in the long run. 


# Environments

It can be natural to just consider "production" - how will everything work in production? And sure, that's the ultimate 
target environment, so why not. But it's also most likely the last environment you'll get to: you'll need to go through
dev, test, maybe others, first.

What environments do you want to have - and what will budgets cover?

- Dev, Test, Prod?
- Dev, QA, UAT, Prod?
- Dev, QA, UAT, Pre-prod, Prod?
- Dev, QA, UAT, Pre-prod, Prod-minus-1-day, Prod?
- Dev, Test1, Test2, Test3, .. , Prod?

Can you design something with "on demand" environments or must they be procured months in advance so start work on the 
4 year environment plan right this moment?

What level of prod-like should each environment be in terms of size and resources?

Will production data be available to "prod refresh" when needed? Must it be obfuscated for security or privacy reasons?

Will your team be DevOps for all this, or will a dedicated team assist? The more environments and moving parts the 
larger the task.

There are a lot of questions here to consider. Once again, think carefully about what the best thing will be for 
your team.


# Testing Strategy

A good testing strategy will have a number of layers: unit testing, integration testing (i.e. testing with real message 
queues, databases, whatever), local-run testing, end user testing, testing-in-prodlike-ecosystem testing (i.e. testing 
alongside other - real - solutions in your ecosystem, if apt).

All of these are distinct testing techniques: decide which ones do, or should, apply; ideally as many as possible. Each
has value and although as you work left to right they go from "fast and cheap" to "complicated and expensive", there 
are things you can can in full-ecosystem testing that more left-hand methods simply cannot account for.

Consider whether you need a test team, or whether your area has an existing team of test specialists you can leverage; 
automated testing is only ever a part of an integrated test programme. Often test teams are overlooked - "we'll just get
the developers to test it" - but this is often a serious miscalculation and a truly false economy: for one thing, 
developers you're asking to do testing are spending time Not Developing Software, and for another it's often something 
they've little interest in, and little real talent for - it's simply a task to get through..  


# Security

Security cannot be an afterthought in this day and age. Security needs will vary depending on your environment and 
whether your project is internal-only or outward-facing but the need for rigorous security practice and "Defence in 
Depth" security planning has never been greater.

Things to consider, meaning satisfy yourself that some area in your organisation is actively dealing with, include:

- network security
- static code analysis for any mistakes you're making in your code
- dependency scanning for any known vulnerabilities in 3rd party libraries (side note - get off Apache Struts NOW if 
you haven't already done so!)
- protection of sensitive data both in transit and at rest, paying particular attention to key areas like personally 
identifiable information and payment card information - and watch your logs, don't feed anything sensitive to _log.info()_!
- credentials management: access to passwords, regularly changing passwords, system identities vs human identities, etc
- common attack vectors such as XSS, SQL Injection, abuse of inputs (Google _Little Bobby Tables_ if you're not familiar with these)
- ensuring your customers never see stack traces or server error messages which may reveal more about the innards of 
your solution than is wise

Different organisations will hopefully have their own programmes here, you're unlikely to have to invent your own from 
scratch - but you do need to take responsibility for adopting and embracing security practices. 


# Executing Releases

This is a really worthwhile one to think about early on - because if you don't make clear plans up-front you risk 
losing your weekends, evenings, or ultra-early mornings to release activity.

To put it another way, consider this the "How We'll Release Without Losing Friends and Family" step. This is your chance
to design a release process which will specifically allow you to do releases in working hours, Monday to Friday - take 
it! 

Now - I don't what that process will be. It's your project. I simply urge you: make that plan _now_! With a bit of luck, 
again, corporate wisdom will have mandated something that fits the bill nicely, but that's certainly not always the 
case - and it might even be the opposite. 

Things to consider:

- how you get from version control/dependency-list via your build/CI server into actual production environments
- how will you update database schema, if there are any?
- how will you do rollbacks when needed?
- can you deploy bad releases and then do those rollbacks without anyone, or anything, being affected?
- how will you do post-release validations?
- what is your user/customer profile - can they reasonably be expected to handle outages, or would that be a showstopper?
- are you responding to requests, or triggering your own scheduled workloads?
- do you have multiple regional deployments or a single global service?
- can you do something with [blue/green deployments](https://www.martinfowler.com/bliki/BlueGreenDeployment.html)?
- can you handle varying versions e.g. patch the Europe servers to 3.12.15 while everything else is stable on 3.12.14 
while you work through them in a sequence?
- are your release/uptime obligations actually _negotiable_, i.e. if you make a strong enough case - and there are many 
good arguments! - for midweek vs weekend releases you might _win_?


# Backups, Site Reliability and Disaster Recovery

Truly madly deeply unexciting to most developers, but crucially important in a solution design. Don't give the task of 
designing this stuff to the coder on the team with the short attention span and a predilection for trying JS Framework 
Darling of the Week.

Consider:

- data backups have to be taken, maybe daily/hourly, maybe always-backing-up is part of your database
- test your restore strategy
- spend time designing around "what if this bit fails" scenarios: components fail, hardware and software, and some 
failures can be well tolerated with some forethought
- Disaster Recovery - it does happen, data centres do suffer outages; a solution spanning at least a couple of regional 
data centres is fairly easily achievable these days - and again, _test_ your DR: a plan that can't be tested a couple 
of times a year is not a great plan to be blunt


# Tech stack and Physical Deployment Architecture

In the olden days, you would have fairly orthogonal choices:

- what would you like to use, Java/Linux or DotNet/SQLServer?
- how will you host it - on-prem? 3rd party datacentre?

Now though there are a frankly bewildering array of tech stack choices, and some - such as AWS - combine to a fair 
extent stack choices with hosting.

The aim of this article is not to offer suggestions on hosting or stack choices, but to raise the considerations which 
may apply and which a solution designer must consider:

- what do you see your end geographical architecture being - deployments in US, EMEA and APAC? Perhaps multiple 
deployments in one or more of those regional hubs?

- what do you need from your database with regard to deployments - global replication, or distinct sharding with highly
independent nodes?

- how will this work with your growth strategy? Can you go from 1 x EMEA to 2, to 3, to 10, as needed?

- is all of the above way beyond your wildest needs and you just need a reasonably well specc-ed web server and a 50Gb 
database but all the cool kids are talking Kubernetes so you don't want to look, y'know, _lame_?

- stackwise do you want to stick with languages and components you know - no-one got fired for Java/Spring/Oracle! - or 
try something more "avant-garde"? If the latter, is your project really one you want to take that risk with - or is 
there a smaller, safer, less-mission-critical one that might be more suitable?

- do you need a Big Data solution? Really? You're sure your data can't fit on a decent mobile phone with an SD card 
and give you all the results you need with a cheeky properly-indexed SELECT...? Well, if you say so!

Some notes of caution:

- don't get carried away with a what-can-we-include mindset. Prefer what-can-we-leave-out. Keep things as simple as 
possible while it all still works. Every component that's a block with arrows coming in and going out in a beautiful 
masterpiece of a system diagram is a component in a real life production system (and dev, test, etc) with bugs, setup 
and maintenance costs, communication overheads, release overheads, etc

- the network is still _by orders of magnitude_ the slowest part of your solution compared to processor cost, memory 
access cost, and local storage cost: micro-services are very much in vogue at this point in mid-2018 but the cost of 
parcelling objects into JSON bundles and chucking them over the network for "processing" is HUGE compared to in-process
handling - consider any network transits a terribly poor relation, to be avoided except when overwhelmingly justifiable

- how will you handle profiling and monitoring, often the last thing you think about when starting out with, in 
particular, an unfamiliar tech stack - and which only becomes a pressing need when production problems arise 

- how will your choices impact your team in terms of training and hiring? Will a rapid re-skilling exercise be needed, 
and is there time and budget? Are there candidates in your area with these skills or are you plumping for bleeding edge 
tech and you'll opt to build skills rather than buy them? 

- building to an unfamiliar tech stack is a significant risk, and you must actively address this


# Local Run Capability

The ability to run applications and components locally is a massive boost to productivity: try to design your solutions 
to support this. _Some choices will preclude it._ Debugging in a decent IDE still offers insights that cannot be 
matched with black-box running-in-QA processes, although remote-debug is a close second. The benefits of letting 
developers explore and experiment with impunity cannot be over-stated. This applies to both "build" and "maintenance" 
stages of a project's lifecycle.


# Enterprise Architecture and Policy

Your organisation may have stringent policies and directives regarding technology choices, tooling, dependency 
management, security, identity and access management, hosting, resiliency, backups and DR, outward-facing websites - 
and others. 

If so it's incumbent upon you as a solution designer to comply with these. Some will help you, some may feel like a 
hindrance - and that's the nature of the game, for better or worse. 


# Weighing It All Up

You might read all this and think: wow - how does anyone ever actually implement anything? And it can seem a little 
overwhelming. 