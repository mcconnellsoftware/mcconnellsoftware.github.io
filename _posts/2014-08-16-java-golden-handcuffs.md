---
layout: single
title: "Java's Golden Handcuffs"
date: 2014-08-16 12:21:29 +0000
tags: Tech
---
Is Java dead? Ask Google that question via the Chrome bar, and you get the feeling that this is an oft asked question, 
with auto-suggest offering the following:

`is java dead 2014`  
`is java dead 2013`  
`is java dead 2012`

I don’t think Java is dead, far from it. Certainly not in the enterprise where I spend most of my own hands-on 
development time. And I don’t see that changing any time soon.

Unwinnable arguments about is-it-or-isn’t-it dead aside, it’s interesting to look at why Java is still so pervasive. 
Many in the industry who’ve enjoyed great success with Java are looking at other options with real interest – i.e. 
they’re seriously considering using something new. Vaunted languages like Scala seem to have made relatively little 
impact, albeit there are enterprises dipping toes in the water.

My take on it: Java’s longevity has little to do with its basic syntax, which is often clunky and wasteful 
(Map<String, Map<String, List<Customer>>> anyone?), and its APIs (Date, cough) can leave a lot to be desired.

No. The reason for Java’s ongoing favour is entirely down to its ecosystem.

Java is so well supported it’s ridiculous. When you think about the huge range of organisations, both commercial and 
FOSS, that provide tooling and services for Java, the conversation about what to use instead moves – to my mind – 
completely away from the core language over to all the ancillary bits and pieces.

Let’s take a look at some of these. My aim is not to suggest that nothing else can match what’s on offer here, but 
that when a developer or architect wants to try something new, he or she has far more to lose than just the repetitive 
strain injuries that typing in Java all day invites…

### Application Servers

Java’s success is mainly on the server side; there are exceptions, granted, Android being the biggest one so far. But 
having tried-and-tested application servers – Tomcat and Jboss seem to have outlasted the vast majority – with known 
configuration, deployment and monitoring characteristics is an amazing “given” for any project, one that I am certain 
gets taken for granted 99% of the time.

### 3rd Party APIs

Apache Commons. Joda Time. Google Guava. Don’t like Java’s own APIs? Build your own. If it’s any good, people will 
come. Happily these days you don’t really need to, the big gaps have been plugged.

### Profiling and Tuning

One of the more subtle aspects of the ecosystem: you don’t even need to use profiling tools until – well, until you 
do need to use them. And thankfully there are a wealth of options, with the JDK coming with a great selection built 
in: Jstat and JVisualVM. Commercial options like JProfiler and YourKit add a whole extra level of capabilities.

### Frameworks

Having stumbled badly with J2EE (remember Entity Beans, Session Beans, and more supporting XML and Interfaces than 
even made sense? Thank God for XDoclet) Java was arguably rescued by a couple of particular frameworks: Struts and 
Spring.

In 2014, a full 10 years after Spring 1.0 was released, Spring continues to expand its offerings, and is the de facto 
standard for a huge number of organisations. Its importance in providing a consistent mechanism for wiring together 
applications, databases, message queues, remote services, testing technologies, object caches, etc., cannot be 
overstated.

### Core Tools

IntelliJ or Eclipse? Doesn’t matter. There’s a modern, first-class IDE there to be used whichever one you prefer. 
One which will integrate with standard testing tools (Junit, TestNG), build systems (Ant, Maven, Gradle), databases, 
and a ton of other projects and intiatives that come together to form this rich ecosystem

### Talent

Starting a new project using Java, Spring and SQL? You probably won’t have to work too hard to find someone that can 
help you out.

### No Surprises

Java simply brings with it the accumulation of 5, 10, maybe 15 years (or more!) of experience. In an industry blighted 
by high profile overruns and failures (“NHS IT Project Cancelled” isn’t even news in the UK any more), “playing it 
safe” on the tech front is maybe common sense.

### So. What Next?

Java will I’m sure fall out of favour at some point, particularly when alternatives start to bring things to the 
table that Java just cannot. I must admit though I fully expect Chrome to continue its suggestions for some time to 
come...

`is java dead 2018`  
`is java dead 2017`  
`is java dead 2016`
