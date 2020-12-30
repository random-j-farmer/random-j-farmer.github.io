---
layout:    page
title:     Decloaking Simulator
permalink: /decloaking-simulator/
date:      2016-04-24 17:00:00 +0200
---

Visualization of decloaking probabilities for various ship sizes, velocities and angles.

For an explanation of the mechanics:

* [Decloaking guide for dictors](https://www.reddit.com/r/Eve/comments/43kpvp/decloaking_guide_for_dictors/czj5a34)
* [Guide: Basic Decloaking](http://jestertrek.blogspot.co.at/2011/02/guide-basic-decloaking.html)

Some interesting ship radii:

* Interceptors: around 30m
* Blockade runners: from 150m (Viator) to 350m (Crane)
* Orbiting drones increase the radius of the attacker by 1000-1500 m.

Drag the mouse around in the diagram and watch the decloaking probability change!


<div id="decloaking-div">
</div>
<script type="text/javascript" src="/js/decloaking-opt.js"></script>
<script>decloaking.Main().main(document.getElementById('decloaking-div'));</script>
