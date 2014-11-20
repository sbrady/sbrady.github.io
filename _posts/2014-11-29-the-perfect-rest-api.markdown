---
layout: post
title:  "The Perfect REST API"
date:   2014-11-29 00:01:15
categories: REST api
---

I want to make the ideal self documenting REST API.

Essentially I believe it should be possible to create an API with a single starting point. A Developer could then navigate the site learn how it works.
I want the API to...

* Use hypermedia as the engine of application state (hateoas)
* Versioning using Hypermedia/Mime types
* Have Authentication requirements

I'll achieve this by creating a simple social friend of a friend type app.
We'll use: 
* HAL
* Grails
* implement OPTIONS
* use Vnd.Error




