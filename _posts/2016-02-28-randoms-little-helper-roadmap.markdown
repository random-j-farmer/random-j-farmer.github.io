---
layout: post
title:  "A Roadmap for Random's Little Helper"
comments: true
date:   2016-02-28 14:15:00 +0100
tags: 
 - little-helper
---
[Random's Little Helper](https://github.com/random-j-farmer/little-helper) started as a demo project to play 
with unfamiliar technology.  It seems to have acquired a life of its own, these days it is the main
thing that keeps me from logging into EVE.  It's a local and d-scan analyzer, the latest feature 
is browser-side history.  Pretty neat in IGB where the solar system of the scan is known.

A public instance is running at [https://randoms-littlehelper.rhcloud.com/](https://randoms-littlehelper.rhcloud.com/)

![Example D-Scan History](/img/2016-02-28-dscan-history.png)

Hard Requirements
-----------------

* Must respond while still in gate cloak, max 15-20 seconds for big local scans
* May show outdated information to speed up response time
* Possible to use anonymously, although it's ok to require a login for some features
* Must be deployable on free hosting service - no big fancy databases, low disk footprint

Short-Term Goals
----------------

* Smart switching between Local/D-Scan tabs. Gate cloak time is precious, don't require
  the user to be in the correct tab for the input.
* Optional CREST Login, use CREST to get solar system information.  This would make the history
  useful in all browsers.  While doing all this JSON stuff, also switch to JAWN parser.
* Diffs for Local history, i.e. for local scans in the same solar system within couple of minutes,
  show which pilots are new and which ones left.  I am not sure how to do a useful diff for d-scan.
* Help tab.  Should explain
  + why some features require a login
  + stale/fresh indicators
  + background api requests
  + consequences of unresponsive backends (zkillboard, eve xml api, ...)


Long-Term Goal: Events
----------------------

Local and directional scans should produce server-side events that are forwarded to interested parties.  
E.g. the scans of a scout should show up in the FC's browser automatically.

This will require log in, faking IGB headers is too easy.  Also not useful without solar system
information.

It will require configuration, i.e. who do I want to share my events with, and who do I want to show
up in my event screen.

* Configuration Tab: share with alliance/corp/individuals.  Show events from alliance/corp/individuals.
* Client opens websocket and receives events.  Long polling should be possible in IGB.
  Maybe restrict receiving events to real browsers?


Long-Term Goal: Shopping List
-----------------------------

The app should be able to parse fittings and inventory lists.  It should be possible to make shopping lists
by including some inputs and exluding others.  E.g. import 5 fits, exclude your Jita inventory.

There should be price analysis.  Items should be divided into items for immediate buy (cheap items, or items where buy and
sell price are not too far apart) and items for making dedicated buy orders.  Ideally all the "immediate buy" items
would be purchased with one mouseclick.  Will have to investigate available APIs for this.

For buy orders, it would be nice if the app could detect when orders are outbid.
