---
layout: single
title:  "Colourblind in Software Land"
date:   2018-05-14 12:21:29 +0000
tags: Misc
---

Being colourblind isn't a terrible disability. It's not a daily struggle, and while it does preclude certain career 
choices (electricians playing "eeny meeny miny moe" with cabling don't exactly thrive) its overall impact for most is 
mainly "shrug". 

Sometimes though, it can be a bit of a problem, purely because the way colourblind people see the world really is very 
different to the way others do.

So let's look at (1) what is being colourblind actually like, and (2) what can people in the workplace and in software 
design do to help?

By the way around 8% of males have some form of colour deficiency, and only around 1 in 200 females. Among other things 
this means I rarely get to pick the kids' clothes - and when I do it's a while before I get another go at it...

In the context of this article I use "normal" to mean "people with little or no colour deficiency". I don't level this 
term lightly, so please do not take offense: I'm just being lazy, I'm sure you're far from normal in many special ways 
of your own.

## What I See != What You See

Most importanly: _the colour blind world is not black and white._ It's colourful, vivid, bright - as you'd expect, really, when 
the grass may as well be orange and the sky a light purple. Some might consider it quite psychedelic. It's our "normal", 
but it happens to be very, very different to what normal folk see.

Secondly: it's not a binary thing. Many people have a minor deficiency that manifests only in slightly-off home decor. 
And there are various different types of deficiency, which boil down to basically which bits of your eyes are dodgy.   

There are a few "colour blind simulators" out there which purport to show you what colour blind people see - some work, 
some don't. I know this because a simulator should be showing me personally a "normal view" and "colour deficient view" 
which look identical - and some _don't_, even for the types of deficiency I know I have. That said, this perhaps serves 
only to reinforce the fact that there is such a wide range of ways our eyes fail to work properly that any one given 
simulator can only represent a proportion of The Afflicted actually perceive, so I won't name names or judge harshly.

This site for example works brilliantly for me: [colourblindawareness.org](http://www.colourblindawareness.org) - the 
homepage has a lovely big vivid image of some pencils. And assuming it's not some subtle and cruel joke, the "sample 
images" 1, 2 and 3 look _100% identical_ to me.

The 4th image though - wow. That's crazy. Those "tritanopes", wow, that's some world they go through, no? Whooo!

That's a joke by the way. But, again assuming images 2 and 3 do look pretty nuts to most people, and the website's not a 
wind-up, it bears repeating: 2 and 3 are normal to me. They look great! Warm, vivid, colourful images! But 4 does look 
_properly bizarre_, and I'm forced to the conclusion that 2 and 3 look just as extreme to normal folk!

## Grumble Grumble

As I've said, most of the time it's not a big deal. For me that muted - or psychedelic? - alternative is my normal. 
Sometimes though it's a bit of a pain:

- graphs and charts: 17 differently coloured trend lines with a legend way down at the bottom might as well be a bunch 
  of dry spaghetti dropped on a flat sheet of A4; database and monitoring dashboards are bad for this, I've found

- black text with some occasional red text for emphasis? yeah I won't see it: waste of time (fluorescent yellow 
  background highlight does the trick for me nicely, FWIW...) - this one actually caused me some difficulty as one 
  past project's "priority tasks" were those in the red text

- RAG rating: these are just about as impenetrable as you'd expect, writing as someone for whom - let me repeat - _grass 
  looks orange_; in fairness all the RAG rating calls I go to seem to agree that our catastrophically failing projects 
  are variations of "green minus" or "soft green" anyway
   
- photography post-processing: if it's more than converting to B&W or mucking about with brightness or contrast I just 
  cannot risk turning face green and exposing myself to ridicule on Facebook
  
- code syntax highlighting: it's quite _pretty_, I suppose, but no practical use whatsoever; genuine kudos to Jetbrains 
  for adding a "colourblind friendly" option to IntelliJ, it didn't help me though and made things less pretty so I 
  switched back

- Call of Duty: team games are just a no-no - trying to carefully distinguish "light beige" from "medium beige" when 
  your enemy has the reflexes of a pre-teen juiced on chicken danglers and litres of Cherry Coke is not my idea of fun

- ATMs: "press the green button to confirm your transaction" - OK then, 33% chance I'll win this one, I've faced worse odds...

## Benefits of Colour Deficiency

None. It's rubbish, but mainly only mildly so. Next!

## How to Help Your Colourblind Colleagues and Customers

Firstly: thanks for trying, and for thinking about us!

Secondly: everything you ever do from this point on has to be black and white. "It's the only way to be sure" - Aliens, 
1986. Just kidding. Colour's great, let's keep it!

The single most important piece of advice I can think of: **don't rely on an ability to distingush colours _alone_ as a 
signal** - use supplementary indicators: 

- stick with a RAG rating for projects by all means, but use the letters R, A and G inside the Excel cells (a little 
  nudge can be all we need!)

- use bold or italics for emphasis, or some other formatting device, _in addition to_ a jump to red text

- line charts can use dotted, dashed, bold, solid lines creatively - and still using colour; more than 4 or 5 lines is 
getting quite "busy" anyway...

A useful rule of thumb: if you can print it or view it in monochrome, and it still "works", it's fine: if the dark grey 
equates to on-track and the light grey to the more "sad-face emoji" type projects, that's perfectly OK, who cares if 
they were puce and fuchsia to start with!

Avoid certain combinations, mainly red/green which are the most commonly mis-perceived colours. Thankfully the wider 
visual design community has apparently got together and decided that red text on green background (or vice versa) isn't 
something they want to take any further.

If you're designing a UI that's going to see widespread use you could explore a "colourblind suitability review", but 
really you should consider an accessibility review generally: there are far more serious visual impairments out there.

"Ticks and crosses" is a safer visual metaphor for health/problems or pass/failure across the board than "green or 
red" - even use O and X if your MS Paint skills aren't up to the challenge.

Tooltips for colour selection are great: hovering over a lime-green option and getting a "Lime green" tooltip is not 
the blatant redundancy you may think!

Phone a friend - remember colour blindness is a really common condition, with nearly 1 in 12 males affected to some 
extent, so it's always worth asking around for feedback if you have any questions.
