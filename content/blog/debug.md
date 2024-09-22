+++
title = "have a debug checklist"
date = 2024-09-22
draft = true
+++

> [Avoid debugging by gut feel or trial and error](https://selectstarsql.com/beazley.html)

### have a checklist

snippet
* env: 
* dir: 
* cmd: 
* out:
* question: 

https://blog.ionelmc.ro/2016/02/18/notes-on-debugging/

https://thoughtbot.com/blog/it-works-on-my-machine-why

https://jvns.ca/blog/2022/12/08/a-debugging-manifesto/ https://jvns.ca/blog/2022/08/30/a-way-to-categorize-debugging-skills/

Atul Gawade's [The Checklist Manifesto](https://www.amazon.com/Checklist-Manifesto-How-Things-Right/dp/0312430000) teaches us: 

* checklists are incredibly useful
* the hardest part of a checklist is actually sticking to the checklist

The first step to addressing both of those points is to actually have a checklist. For whatever reason, I've never seen anyone debug according to an explicit checklist, but I think it might be worthwhile. Here's why.

### why have a checklist?

Having a checklist is better for your coworkers and yourself.

* If you need to enroll the help of a coworker or collaborator, you've got a list of things you've attempted and the results of those attempts. Plus, you've proof that you put effort and consideration into solving the problem on your own and therefore respect their time.
* As you document what you've tried, you'll regain some flow. Almost like TDD, make small assertions and record what happens. This mental hack wards off negativity, especially when the bug is above your current skill level.

### my checklist

Here's my attempt at a personal checklist:

* read the error message, read the code
* if stuck, check out Duck Duck Go and Stack Overflow
* if still stuck, get back to the previous working state by:
    - rebuilding the code
    - checking out the develop branch or a previous working commit
    - recloning the repo
* some things to double check:
    - are there any environment variables that need to be set? any env var incorrectly set?
    - are the logs masking anything?
    - anything left in environment from a previous branch (db migration, dependencies)?
    - dependencies: anything been bumped lately?
    - version interop: does the server require a certain client version (or vice versa)?

### other advice

If things get really dire, I take a walk and think about something else and then, when I'm back at my desk, ask myself [what do I *actually* know?](https://jvns.ca/blog/2018/09/01/learning-skills-you-can-practice/)

p.s. Julia Evans has a bunch of [other debugging advice](https://jvns.ca/blog/2019/06/23/a-few-debugging-resources/) that you should check out. ++ https://codewithoutrules.com/2020/08/17/search-engine-programmers/
