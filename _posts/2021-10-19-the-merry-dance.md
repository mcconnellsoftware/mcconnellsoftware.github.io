---
layout: single
title: "The Merry Dance We Do"
date:  2021-10-19 14:53:00 +0100
tags: Misc
---

I figured it's been a while - let's update the blog. How hard can it be to crank up the old motor?

And then the trouble started.

Quick jump to "github pages", oh dear some vuln reports. Best fix those. Happily some 
magical "Dependabot" thingy has raised a couple of Pull Requests. Merge. Done.

1 vuln remaining. Dependabot can't just make it go away, hmm let's look closer.

OK - not too bad, another version bump in whatever Gemfile.lock is. Delete delete type type - done.

Commit - push - auth failed. Retry - same. 401.

Stack Overflow time!

"Try the Use credential helper" setting.  OK sounds kind of relevant let's do that.

No such setting. IDE version is pretty old by now, let's update that.

(Few hundred Mb later...)

Some shiny new buttons, lovely. Oh wait - Git version not supported.

"git update-git-for-windows"?

Nope *way* too ancient for that!

Add & remove programs -> uninstall -> off to the interwebs for another download.

(More Mb downloads later)

(Wow git has a lot of options when you install it doesn't it?)

Right - install done, new Git version accepted and recognised.

And this time... 403 error!  Woo!

OK keep calm, this is not a biggie, I am not unfamiliar with HTTP error codes. Let's try looking again post-update 
for that "Use credential helper" spell from the Stack Overflow wizards.

It's there now! *Tick the box*

Retry. Grant the IDE some special GitHub access? OK why not. Done.

Another one? OK. Done. Go nuts, IDE.

Another attempt: push rejected?  Well I don't have any JIRA hooks, this project's pure FUN, so let's try a pull and retry.

Success! Sort of! Some new files appeared!

But the one I was working on has gone. Vanished.

Pause. Sip of delicious fruity juice.

Right I know. "Local history -> Show history..." - and what do we have here? Our missing file. Lovely. "Revert" please!

It's back. Quick tweak. Save.

Commit/push...

Success! Of the unqualified, Properly Good Again variety!

We're back in business - and I enjoyed every purely-technical, no-politics-or-consensus-building minute of it.
