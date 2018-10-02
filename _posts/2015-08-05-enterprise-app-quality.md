---
layout: single
title: "Enterprise Application Quality"
date: 2015-08-05 12:21:29 +0000
tags: Management
toc: true
---
_Aug 2015: One widely known benchmarks of “software team quality” is The Joel Test, and nitpicks aside it’s still an 
entirely sane bunch of questions 15 years after its debut. 12 “yes” answers – or 12 x “nope!” – gives a pretty 
quick insight into an organisation._

Reading about The Joel Test again recently got me thinking about this, largely because many of the questions 
don’t really hit close to the heart of what makes large enterprise development satisfying and effective – or not. 
Hallway usability testing? For a JSON parser? Or a Customer Database Service Interface? That I would like to see!

Here then are 10 questions which I think get more to crux of the matter: an Enterprise Application Quality Test. 
Catchy.

These aren’t lofty fads, they’re basics. More than a few negative answers could well indicate a team that needs to 
take a step back and look at how it’s working. Usual caveats apply: lots of “no” doesn’t guarantee disaster, and 
lots of “yes indeedy” doesn’t automatically mandate a gold star and wild applause.

### (1) Do you have unit tests – and keep them passing?

My definition of unit tests: “pure” code tests that test classes’ and methods’ execution under different conditions. 
Unit tests should test logic, boundary issues, happy-path and rainy-day routes. They should run nearly instantly, 
with no additional configuration. They should be small, concise, “point” tests, not end-to-end.

### (2) Do you have integration tests – and keep them passing?

I see integration tests as being more of an end-to-end testing approach. Ideally they’ll store data in a real 
database (in-memory, or personal test DB -  all count); fetch or retrieve from a real FTP server (again, local-install 
is more than fine); write files to a real directory. Etc.

Unit tests that show: “yes we passed our Transfer Objects to our DAOs” are one thing, but there’s just no substitute 
for putting data physically into a proper database – and then querying to get it back out again.

Some configuration effort up-front is acceptable here; ideally, as much as possible should be automated.

### (3) Do you use Continuous Integration to manage builds and deployment?

Nightly builds. Continuous builds. Continuous deploys. Continuous unit and integration test execution. Continuous 
deployment of fully-compiling builds, which then pass all tests, to QA, restarting every bit of the infrastructure, 
mailing the team with “Job done!”, and then popping on some toast.

Thank you Jenkins et al.

### (4) Can developers run the application locally?

It’s critically important to be able to start your team’s applications locally, whether inside the IDE, inside a local 
app server, or even on the command line. Ideally, situation-testing against real databases, real FTP servers, real data 
consumers and providers will be supported. If that’s not as simple as “start your local Mongo and change 
connect.properties” and needs some up-front investment – maybe to build a Data Provider Simulator – then do it.

This capability makes it much easier to develop new features, find and fix bugs (yay, debuggers!), train new 
colleagues, respond to change, and keep “real” QA environments free from turbulence (“QA is down again – Neville’s 
adding a new feature to the Widget Streamer and it still doesn’t work…”).

### (5) Can the application be readily run in different environments?

Running out of resources on server ‘BlueSteel449’? ‘LeTigre221’ creaking with all the “big data” sales demos being 
done? Let’s grab ‘Magnum35’ and fire that puppy up.

Can’t do that without a fortnight from the environment team and a sacrifice to the angry gods of the purchasing dept? 
Oh…

### (6) Is there a clear and effective branching strategy, aligned with the release process?

It’s now mid-August: does every single person in the team know that we’re working on the Sept2015 branch for the 
September 30 release, still fixing last (June) release’s bugs in June2015, and merging those fixes into Sept2015? And 
that Nov2015 branch is up and running for that slightly-further-out release? Yes? Good.

And is anyone obliviously still committing to the April2015 branch, and feeling increasingly nervous about why their 
changes aren’t showing up in QA? You are, Arnold? OK. Let’s chat.

### (7) Is there clear production release documentation and process, ideally much of it automated?

Sometimes software development would be a whole lot more enjoyable without having “releases” – ruining everyone’s 
weekend, and riling up users with tricky new things to learn.

Releases being a vital part of keeping the fees/salary/doughnuts coming in though, we need to grin and bear it. Make 
this simpler by:

- automating the release process as much possible  
- documenting it really, really well  
- making sure everyone knows what’s actually involved under the covers of any scripting or tooling – if not everyone, 
enough folk at least that no-one is more than 20 feet away from Someone With Answers  
- always, without fail, having a rollback / “undo” plan for a release, be it code or data  

Releases should be controlled, well communicated events. They should never require heroics, improvisation, calls to 
the emergency services or floods of tears.

### (8) Is there effective dependency management?

There are 3rd party libraries: database drivers, XML parsers, FTP interaction libraries. Loads of them. These are 
quite easy to manage, they don’t change that much.

Then there are your in-house libraries, those produced by sibling teams (the Customer Profile folks, or the Product 
Inventory empire), and those produced by the ever-overworked Central Engineering Brigade.

And there’s your very own smorgasbord of interacting components: the object model, the service layer, the mass 
distribution engine – and heaven forbid you pair v3.2 of the distribution engine with v3.1 of the object model: nasty, 
nasty, nasty.

Happily there are plenty of ways to manage all of this: Maven, Ivy, Gradle, to name but a few in the Java space. 
Please: do use one of them.

(Bonus points if you keep all your dependencies pretty much current and have nothing more than 3 years past “end of 
life”! Even if your firm forces this upon you don't worry - the bonus points are still yours!)

### (9) Are there well defined system inputs and outputs – and timelines?

It should be really, really clear to all in the team that we get this bunch of data from this team between 8am and 
11am UK time, via MQ, and we deliver the results of “having a right good tinker with it” to that other team, via SFTP, 
no later than 1pm – again UK time. 1.15pm is sort of acceptable at a push, but any later than 1.30pm and really, 
management are going to get the big sticks out, the ones with the bent nails protruding. Or “missed SLA consequence 
time” as they call it.

### (10) Are there clear logs/metrics and audits of inputs and outputs?

What we want to see in logs: a clear narrative, with all relevant times and details for the inevitable “what went 
wrong and why?”. Multiple threads and distributed components can make this harder to do effectively – but still: do 
it. Your future self, the L3 support self, will thank you.

{% highlight text %}
9:12:01 - req 23498, consumer X requested Thing345  
9:12:03 - req 23498, request valid, storing: /my/infile/request_23498.xml    
9:12:04 - req 23498, getting Thing345 from database – starting  
9:12:06 - req 23498, getting Thing345 from database – completed in 2000ms  
9:12:07 - req 23498, response valid, storing: /my/outfile/response_23498.xml  
9:12:08 - req 23498, returning response, all processing completed in 7000ms  
{% endhighlight %}

Accusations of an ignored request? Logs say no!
Accusations of a 5 minute response? Logs say no!
Accusations of response content with some sweary words? Audit files say no!

You get the gist…! Good logging is an art, and deserves an article in its own right, but this little aperitif serves 
our purpose here.
