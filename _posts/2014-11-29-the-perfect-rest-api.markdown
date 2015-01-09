---
layout: post
title:  "The Perfect REST API"
date:   2014-11-29 00:01:15
categories: REST api
---

I want to make the ideal self documenting REST API.

Essentially I believe it should be possible to create an API with a single starting point. A Developer could then navigate the site learn how it works.

**I want the API to...**

* Use hypermedia as the engine of application state (hateoas)
* Versioning using Hypermedia/Mime types
* Have Authentication requirements

I'll achieve this by creating a simple social friend of a friend type app.

**We'll use:** 

* HAL
* Grails
* implement OPTIONS
* use Vnd.Error

**Update:** I've quite a bit of trouble getting grails HAL support working.

You can see some of the road blocks I ran into:

* [grails HAL, incorrect self links](http://stackoverflow.com/questions/27055547/getting-started-with-grails-hal-incorrect-self-links)
* [incorrect self links](https://jira.grails.org/browse/GRAILS-11857)
* [Customize Link Rendering type with HAL in Grails?](http://stackoverflow.com/questions/27328804/how-to-customize-link-rendering-type-with-hal-in-grails)

You can see how far I haven gotten: [perfect-rest-api](https://github.com/sbrady/perfect-rest-api). One interesting thing I found along the way is a nice way to setup restful routes in grails. I will put up a gist for it.

Going forward I'm going to switch to trying out Rails with [Roar](https://github.com/apotonick/roar-rails)

