---
layout: post
title:  "Pull Request vs Continuous Integration"
date:   2015-01-28 00:01:15
categories: Continuous-Integration Pull-Request agile XP
---

I am a major supporter of [Continuous integration](http://martinfowler.com/articles/continuousIntegration.html).
I've seen many companies attempting to replicate the success of open source projects by using a pull request with feature
branch model for proprietary code. Unfortunately this tends to break Continuous integration, and team communication.

**Pull Request Problems**

A CI practitioner would have a developer integrating code with the mainline, very frequently, every hour or so.
This has many benefits:

* When a developer is about to start taking the design of the system is one direction, an excellent
communication tool is to start making the changes for everyone to see. These small communicative commits go missing in the 
pull request model, as the integration time is put off for days.

* When a developer makes a major overhaul and another developer submits a PR in slightly different direction.
  Merge Hell will happen, and most likely most of one of those developer's work will be laid to waste. 

The above issues could be dealt with, via other communication channels, standup and simply talking to one another.
Also If developer A knew that developer B was working on a similar area of code, they could do some "Promiscuous Integration",
in DVCS and pull and push to each other branches. I have never really seen "Promiscuous Integration" in practice. What
I seen is that when a developer learns that another developer is working on the same code, they will drop it, back off, and
do something else, probably something with less priority.

**Continuous integration Problems**

The main reason I've heard for pull requests over CI is for code review.
The obvious solution is to use [pair programming](http://en.wikipedia.org/wiki/Pair_programming). Also In practice I
have rarely worked with a team with whom I did not trust.

**Lets be pragmatic**

Feature branches and Pull Requests are useful...

* When there is a new feature being worked on, the developer has some valid concerns of it leaking out into production
half finished. Sure you could use a feature toggle. However in some cases the extra code to implement a feature
toggle, just isn't worth it. So long as the team understands that the feature branch exists and this is not an ideal situation,
it is the pragmatic solution.

* I have worked on a team where we used a pull request for releases and the whole team would do a bit of a review.
This worked by using `master` branch as our mainline and `staging`, `production` for other environments. We'd submit a
PR from `master` to `staging` etc. This worked reasonably well, although most code review happened via pair programming.

**Closing**

Clearly Pull requests and feature branch are fantastic. Pull requests have changed the face of open source
 software, thank you github. However for a software team working on proprietary software. Please default to Continuous
 Integration and use feature branches when necessary. 
 
 
