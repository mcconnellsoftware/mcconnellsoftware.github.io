---
layout: single
title:  "Colourblind in a Software Driven World"
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

Most importantly: _the colour blind world is not black and white._ It's colourful, vivid, bright - as you'd expect, 
really, when the grass may as well be orange and the sky a light purple. Some might consider it quite psychedelic. It's 
our "normal", but it happens to be very, very different to what normal folk see.

Secondly: it's not a binary thing, colourblind or not. Some people have a very minor deficiency that manifests only in 
slightly-off home decor. And there are different types of deficiency, which boil down to basically which bits of your 
eyes are dodgy. 

There are a few "colour blind simulators" out there which purport to show you what colour blind people see - some work, 
some don't. I know this because a simulator should be showing me personally a "normal view" and "colour deficient view" 
which look identical - and some _don't_, even for the types of deficiency I know I have. 

That said, this perhaps serves only to reinforce the fact that there's such a wide range of ways our eyes fail to work 
properly that any one given simulator can only represent a small proportion of what we "The Afflicted" actually perceive,
so I won't name names or judge harshly.

[This site](http://www.colourblindawareness.org) for example works brilliantly for me - the homepage has a lovely big 
vivid image of some colouring pencils. And assuming it's not some subtle and cruel joke, the "sample images" 1, 2 and 3 
look _100% identical_ to me.

The 4th image though - wow. That's crazy. Those "tritanopes", wow, that's some world they go through, no? Whoah!

I'm only half kidding there, by the way. Image 4 really looks extreme to me, but - again assuming images 2 and 3 do also
look pretty nuts to most people, and the website's not a weird mock-the-colourblind effort, it bears repeating: 2 and 3 
are 100% normal to me - they look great! Warm, vivid, colourful images! But 4 is _properly bizarre_, and I'm forced to 
the conclusion that 2 and 3 look just as extreme to normal folk!

I've had conversations along the lines of "well, yellow does look pretty much the same as lime green doesn't it?" 
Apparently not. And yes I have got actual lemons and limes mixed up before.

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
  cannot risk inadvertently turning faces green and exposing myself to ridicule on Facebook
  
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

Secondly: everything you ever do from this point on has to be black and white. "It's the only way to be sure" - Aliens (1986).

Just kidding. Colour's great, let's keep it!

The single most important piece of real advice I can give: **don't rely on an ability to distinguish colours _alone_ as a 
signal** - use supplementary indicators: 

- stick with a RAG rating for projects by all means, but use the letters R, A and G inside the Excel cells (a little 
  nudge can be all we need!)

- use bold or italics for emphasis, or some other formatting device, _in addition to_ a jump to red text

- line charts can use dotted, dashed, bold, solid lines creatively - and still in colour; more than 4 or 5 lines is 
getting quite "busy" anyway...

A useful rule of thumb: if you can print it or view it in monochrome, and it still "works", it's fine: if the dark grey 
equates to on-track projects and the light grey to the more "sad-face emoji" type projects, that's perfectly OK, who cares if 
they were puce and fuchsia to start with!

Avoid certain combinations, mainly red/green which are the most commonly mis-perceived colours. Thankfully the wider 
visual design community has apparently got together and decided that red text on green background (or vice versa) isn't 
something they want to take any further.

If you're designing a UI that's going to see widespread use you could explore a "colourblind suitability review", but 
really you should consider an accessibility review generally: there are far more serious visual impairments out there 
and you'll do untold good to a bunch of appreciative users.

"Ticks and crosses" is a safer visual metaphor for health/problems or pass/failure across the board than "green or 
red" - even use 'O' and 'X' characters if your MS Paint skills aren't up to the challenge.

Tooltips for colour selection are great: hovering over a lime-green option and getting a "Lime green" tooltip is not 
the blatant redundancy you may think!

Phone a friend - remember colour blindness is a really common condition, with nearly 1 in 12 males affected to some 
extent, so it's always worth asking around for feedback if you have any questions.

And a slight caveat to the above - I'm guilty of this myself, I assume if it's fine for me, it's fine, period - 
remember there are different types of colour blindness, and where I struggle with red/green, others struggle with 
blue/yellow. Be wary of building a whole colour scheme based on a nod from Dave from Billing and Accounts, Dave 
doesn't speak for all of us!

## Is There a Cure?

Not yet. There are some borderline scammy glasses which can help accentuate differences between colours in artificial 
and arguably completely pointless ways, but they're not much different to wearing tinted sunglasses. At the end of the 
day, if you can't see red properly, _you can't see red properly_, and making reds EVEN MORE RED won't help. 

But who knows - one day we might find a fix, even if it's total nanobot eyeball reconstruction! Who wouldn't jump at that?
