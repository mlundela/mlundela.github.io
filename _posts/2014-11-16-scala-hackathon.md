---
layout: post
title: "Berlin Scala Hackathon"
date:   2014-11-16
categories: blog
---

![demo](/assets/set.png "Set")

My team won the Scala Hackathon this weekend, which to me felt like a real achievement given that we were competing against some of the smartest people within the Scala community, including one super-team from Typesafe and another team with the author of [The Neophyte's Guide](http://danielwestheide.com/scala/neophytes.html), Daniel Westheide on board.

I presented my idea for a project on Friday, which was to create an online multiplayer game based on the card game [Set](http://en.wikipedia.org/wiki/Set_%28game%29), and it attracted a lot of interest among the audience.

Four of us formed a team, and we set out to use Play with Scala and Akka Persistence on the backend, ScalaJS for the frontend (after all it was a Scala hackathon!) and let them talk to each other through websockets. The ScalaJS code on the client actually turned out to look much like an Actor (!), doing pattern matching on case classes that were shared between the backend and frontend. 

You find the sourcecode [here](https://github.com/Reimerei/patternMatching).
