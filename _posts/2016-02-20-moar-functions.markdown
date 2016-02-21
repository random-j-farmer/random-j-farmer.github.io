---
layout: post
title:  "Moar Functions"
comments: true
date:   2016-02-20 18:05:00 +0100
tags: 
 - scala
---
I was going to write a post about generic copy operations.

But then I read [Strategic Scala Style: Principle of Least Power](https://lihaoyi.github.io/post/StrategicScalaStylePrincipleofLeastPower.html) and a light bulb went off.  More accurately, I read it a couple of days ago, and today I had an 'Aha!' moment.

Just use a bloody function.

I model with traits too much. I guess it is a habit I acquired by extended exposure to Java.

I don't have a problem using an API with functions, it's one of my favorite things about Scala.  I just don't use them enough in my own APIs.  Passive versus active vocabulary.

So I am writing this down instead: I need to use functions more.
