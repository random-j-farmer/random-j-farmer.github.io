---
layout: post
title:  "Faster than the Speed of Decloak"
comments: true
date:   2016-04-24 17:00:00 +0200
tags: 
 - theory
 - cloak
---

Some days ago, I was late for a Ferox fleet so I jumped in an interceptor and caught up with them.
A goon interceptor was following the fleet, he'd warp to the gate at some distance and cloak up.

I tried to decloak him, but no joy.  After my second attempt he convoed me, telling me I came
within 2km of him but didn't decloak him because I was going too fast - the server just checks
current positions every server tick.  This made sense, so I thanked him for the information.

![some things should not be decloaked](/img/2016-04-24-some-things-should-not-be-decloaked.jpg "Some things should not be decloaked")

Goons being goons I asked in fleet if you could go too fast for decloaking, and they said no,
the goon was just messing with my head.

Still, it sounded logical, so after fleet I did some googling.  Not a whole lot of information,
but I found two very interesting links:

* [Guide: Basic Decloaking](http://jestertrek.blogspot.co.at/2011/02/guide-basic-decloaking.html)
* [Decloaking guide for dictors](https://www.reddit.com/r/Eve/comments/43kpvp/decloaking_guide_for_dictors/czj5a34)

Jester's post "Guide: Basic Decloaking" does not talk about server ticks and ship velocity,
but he recommends turning off the MWD so you do not overshoot the target - otherwise,
you'll be out of scram range once you have acquired lock.

The reddit comment talks about server ticks and speed at length.  Do read it, and look
at the images he linked - I love them.  According to this comment, decloaking is tick
based and only looks at the current position at that time.  So going too fast would
entail the risk of not decloaking your victim despite coming close enough in your approach.

There is one problem with those images though: they are not at scale.  I wanted something
at scale to figure out good speeds for various distances and ship sizes.  So I wrote a
[program to do that for me](/decloaking-simulator/)

It turns out having drones out gives you an incredible edge - Jester is absolutely correct.
It allows you to go much faster without lowering your decloak probability, and it allows
a significantly wider angle in your approach.

3000 m/s seems to be a good maximum speed for a ship without drones out - "Decloaking guide
for dictors" gets it right.  With drones, assuming a 1500m radius perfect circle of drones,
even 6000 m/s would look good for decloaking.  But as Jester notes, decloaking is worthless
without landing that scram ...

Also interesting: decloaking a Crane (350m radius) is easier than a Viator (150m radius),
but not that much easier - it allows you about one degree in your approach angle, but that's it.
I'd always refrained from using a Prorator (220m radius) in favor of a Viator.
I think I will give Prorator a try soon.

Thank you, Nameless Goon.

And thank you for the funny picture, Drackarn - I stole it from
[Sand, Cider and Spaceships](http://sandciderandspaceships.blogspot.com/)
