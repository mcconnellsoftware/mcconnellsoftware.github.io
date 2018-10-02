---
layout: single
title: "The Struggle for a Design Balance"
date: 2016-06-24 12:21:29 +0000
tags: Design
---
_Jun 2016: It’s surprisingly hard, producing software in teams, to get a consensus on “detailed design”. And by that I mean 
the fine-grained, nitty-gritty, actual classes and interfaces._

Let’s take the simplest example I can think of for now: a component to store a Product in a database. Inside 
a “storage component” in a larger application.

Assuming we’re using an enterprise ecosystem (Spring, Java, SQL database, version control, CI server, etc), even 
the choices we might make to fit in with that can form a tremendous number of permutations. Some might implement 
simply `IProductDAO`, `ProductDAO` and `Product`. 

Some might add a `ProductBuilder`, or a `DAOFactory`. Others might model generic database fields for use in that 
ProductDAO and all other future DAOs, for any database, SQL or otherwise: “Description”, well it’s textual, it’s 
mandatory, let’s design some classes to model all that: `DescriptionField` extends `Field`. Nice.

I won’t overstretch this trivial example: most of us can probably relate by now.

The question is: what’s the right amount of design? We’re all vulnerable to subjective criticism: whether we 
over-engineer or under-engineer seems entirely in the eye of the beholder.

Mantras abound: Keep It Simple Stupid. You Aren’t Going To Need It. Don’t Repeat Yourself. But then: patterns. 
Factories. Builders. All that proven Best Practice good stuff, just waiting to be woven in!

I prefer simplicity: what’s the simplest thing that works, without clear shortcomings? We can all appreciate a 
sound, elegant design that grows larger gracefully, absorbing new features month by month, year by year. But how 
do we measure that? How can we prune the frippery and leave just a good, solid, extensible core?

Perhaps the database design world has some good approaches: I am thinking normalisation. Start properly simple, the 
simplest thing that feels like it might work, and make improvements until the solution is “good enough”: first 
normal form, second normal form and then onto third normal form, by which point you’re probably in decent shape. 
Perhaps code design should start with The Basics and factor in “design” only until no obvious flaws remain – build 
it up in terms of complexity, based on actual shortcomings, rather than starting by default with factories and 
facades galore.

Fundamentally it perhaps comes down to opinion, context and personal philosophy. But still, correct behaviour and 
“accurate in what it tries to model” are, on their own, absolutely not sole success criteria: a given 
`GenericPersisterBuilderFactory` might be utterly and incontrovertibly correct in its implementation – with JUnit 
proof, no less! – but might yet become an albatross round the neck of the team supporting it for the next 5 years.

And that’s where software engineering ultimately remains an art, a craft, as much as science and engineering, for now.
