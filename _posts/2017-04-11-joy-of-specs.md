---
layout: single
title: "The Joy of Specs"
date: 2017-04-11 12:21:29 +0000
tags: Design Management
---
_Apr 2017: Specifications that is, not spectacles. You see after a heated pub debate (really) about the need for “a spec” in the 
face of almost universal Agile adoption, I felt drawn to defend this pillar of proper software engineering._

In a Perfect Agile Environment with responsive, always-available customers, and subject matter experts falling from 
the rafters, specs may not be needed. But I suspect relatively few enterprises operate in such idyllic states. So, 
thought #1 – in an imperfect operating environment, a spec can help nail what’s really to be done.

Many enterprise projects take place in regulated context: financial, health and medical, control of heavy machinery. 
None of those are environments where a mixup between microseconds and minutes is going to form the basis of a gentle 
anecdote, and regulators aren’t in the jobs they’re in for the entertainment opportunities. Thought #2 – specs provide 
clarity up front, and also in retrospect.

The slow and ongoing demise of the Waterfall project method means that very few of us have to deal with ring binders 
of printed and versioned Requirements, Design, Functional and Nonfunctional Specifications. That is, mostly, A Good 
Thing. But with the undoubted benefits Agile brings, along with it comes the implication that we no longer need specs. 
Let’s take a rough view of what happens:

1 – define a User Story, or a Smallish Work Item of some sort that can be done in a Sprint  
2 – sort out what needs to be done, and how  
3 – do it  
4 – release it, evaluate it, measure it

And repeat: if it’s not perfect, fix it in the next Sprint.

Step 2 is to me the contentious bit. For anything except the glaringly obvious, the so-obvious-it’s-purely-strawman-to-discuss-it, 
we should have a spec. Usually, Step 2 means talk to customers, colleagues, bosses; send a few emails, have a few 
conference calls. And that’s all great, it’s standard “requirements gathering and elicitation”. Even build a simple 
prototype with PowerPoint, Excel, or your kids’ crayons. All fine, all helpful, all important steps. But write the 
final details down in a spec.

Seventeen whole years ago, Joel Spolsky write about specs, and the endemic resistance we engineers have to them, 
and the small group of articles still reads well today:

[Painless Functional Specs](http://global.joelonsoftware.com/English/Articles/PainlessFunctionalSpecifi-2.html)

I believe the crux of this whole issue – the dearth of beltingly good specs – is that we engineers continue to see 
specs as extra, pointless, bureaucratic distractions. And we utterly miss the truth, that specs are our best friends 
in the world in terms of driving successful delivery – or surviving the blamestorming when things go wrong.

In an Agile team specs need not, and should not, be onerous leaden tomes. 2 or 3 pages will suffice most times. 
Developers shouldn’t consider specs as 50 page “templates” with sections and subsections for every imaginable facet 
of possibility. There’s no need for “17.11.4 – Steps To Take If User Is Named Albert (DELETE IF N/A)”. Some guideline 
bullet points for topics to cover are:

- what’s the project/story objective?
- why are we doing it?
- what’s the scope, i.e. which systems, components, applications, modules, files and databases are affected?
- what, fundamentally, do we plan to do?
- how do we intend to do it?
- what “tricky” areas are there which aren’t well understood right now, or are known to be difficult or novel?
- have we any outstanding questions?
- what is notably excluded from the task at hand?

Now, we can dress these up as much or as little as we like depending on the culture at hand – Spec by Stealth is an 
intriguing option – but this is all information which surely only serves to improve our chances of getting things 
right with our subsequent build work. This simple format can work for a 5 day project but can also serve a 5 week 
project reasonably well. Even a 5 month project could conceivably get by with enough elaboration in appropriate areas.

Getting this in writing serves to ease further communications, e.g. with one’s boss’s boss who has a meeting with 
his budget allocation team and needs to know right now what the project’s all about.

And of course – when the time comes for evaluation later, and did we actually achieve what we wanted, nobody is 
going to deliver a perfect recall of the 17 conference calls that produced that consensus on what’s really going 
on (and which wasn’t really even a consensus but we all pretended it was, 5 hours in, just to get away). But a 
spec does.

The corollary to the importance of specs: nobody reads them. People hate reading them just as much as they hate 
writing them. Unless you have supervisory or other personal leverage over someone, or their neck’s even more on the 
line for the project than yours, never rely on a simple email: “here’s the spec”. Nobody will read it, nobody has 
time, deep down nobody cares because it’s not “their” task.

The best and only way to get people’s attention remains getting them together in a meeting room – or failing that a 
conference call with a screen share – and going through the spec. Don’t just read it word for word, of course, 
paraphrase and summarise. But do go through it in some level of detail, so that all the people involved who are 
Not You and hence experiencing their first ever encounter with this marvellous document, have many opportunities 
to realise that “hang on, no, that won’t work”. Ask people explicitly: Fred does that seem OK? You will almost 
always find these sessions produce changes, concerns, objections, queries, clarifications and suggestions. And they 
will always improve your overall outcomes.

So please, do consider making the humble spec part of your flow. I’ll agree sometimes changes genuinely are so simple 
they need zero clarification; let’s not be dogmatic. No-one needs a spec to fix the “Addrsse” typo in the order form. 
But for the rest, why not consider a simple spec and see how it works out?

I have a final point for folks joining new teams where specs are not the modus operandi: here it’s even more vital 
you use them. Don’t call it a spec if that’s going to cause friction: call it a doc with some ideas/plans in it that 
you’d like to get feedback on. And if it contains an entirely correct and complete set of changes needed in the 
WidgetFarm, but your team mates realise with horror that you’ve utterly overlooked the whole of the ThingyTransfer 
deployment, and without that the half-understood task will ruin the company, then your spec has done its job.
