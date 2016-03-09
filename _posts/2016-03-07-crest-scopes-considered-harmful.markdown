---
layout: post
title:  "CREST Scopes Considered Harmful"
comments: true
date:   2016-03-07 19:30:00 +0100
tags: 
 - crest
---

Edit: This has been fixed, you can revoke access you granted now.

---------------------------------------------

The original post was:


> TL;DR
>
> CREST refresh tokens do NOT currently have any expiration.  If you grant "characterLocationRead"
> to some web app, that app will be able to track your character until Hell freezes over,
> aka CCP Soon.

I've been playing with "characterLocationRead" over the weekend, and it made me
think about how to protect the CREST `refresh_token` from prying eyes.  Because
the `refresh_token` is incredibly dangerous - it does not ever expire, so
anybody who gets his hands on it will be forever allowed access to the
CREST api on (or against) your behalf.

From the [documentation](http://eveonline-third-party-documentation.readthedocs.org/en/latest/sso/refreshtokens/):

> ... the refresh token can be stored and used indefinitely. (Users can revoke access for individual apps on the support site)

I've used authed CREST before with a market app I wrote, but I did not remember anything about revoking 
access for refresh tokens, so I took a look.

![just say no](/img/2016-03-07-crest-login.jpg)

There is a menu "Third Party Applications" on support.eveonline.com, but it does not even show you
the third party applications with tokens.  The screenshot below was taken immediately after
the login screenshot (above) and testing the location read API call.  And it should show
more than that.  I've been testing all weekend with multiple apps.

![pls give cancel ccp](/img/2016-03-07-crest-authorized-apps.jpg)

So it would seem CCP is aware of the problem, but they didn't give it priority.  Hopefully they
will do so soon.

Until they do, I won't be granting scopes to applications I did not write myself.
