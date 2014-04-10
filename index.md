---
layout: default
description: Introduction to site
title: How to stop the bleeding.
---

You've probably heard of this “HeartBleed” problem that tech folks are talking about.
But what does it mean for you?

It means that, for every site on the Internet where you have a password,
you probably need to change the password.
Not yet, but when the site has fixed their issues.

You use a web-browser to connect to a web-site.
For secure web-sites, you get a padlock, as your web-brower uses something called “HTTPS” to connect to the server.
The way that HTTPS works is to make normal web-site requests (“HTTP”)
over a connection made secure with “Transport Layer Security”, or “TLS”
(old and now-insecure versions of which were called “SSL”).

The software used by a majority of sites to implement TLS had a tiny coding mistake which has had huge consequences.
A “heartbeat” mechanism was implemented without a safety check on a value received,
which would result in the server sending back chunks of extra things it currently knows.
Such as, say:

 * recent usernames and passwords used by other people
 * the special “cookies” given to people recently to prove that they're signed in
 * the secret key used to prove to your browser that the web-server is entitled to present its “certificate” to you;
   that is, the secret key with which an attacker can pretend to be that site.
   Say, someone in the same café as you, on the wireless network (WiFi).

There is evidence now of attacks going back at least as far as November 2013.
So “the bad guys” have known about this for a while and have been collecting data.
This is not some airy theoretical attack which maybe somehow a bad person could use.
The bad people have been using it.  Passwords have been stolen.  Keys have been stolen.

Not _all_ sites are affected, but so many that you have to assume they have been, until they say otherwise.
The best current estimates are that more than two thirds of all secure web-sites are affected.

Some sites use special devices called “load balancers” to handle the TLS; some
versions of some of those load-balancers are based on OpenSSL and are affected.
We suspect that some sites who claim that “we don't use OpenSSL” are being
careful in their phrasing or have only done a superficial analysis and have
not fully analysed whether or not the dedicated appliances they use, such as
load-balancers, mean that their customers are impacted.

There are various tools around which let you see if a site is still vulnerable;
using these tools against a site you are not responsible for running is an attack and is probably a federal offence.
Don't do it.
Besides, they don't tell you if the site is safe to use yet.

See, the site operators need to:

 1. Deploy fixed code to every web-server which they run.
   - big sites are not one server some place; they're made up of tens, hundreds or thousands of servers,
     spread around the globe, and they're not all fixed at once.
     No tool will tell you when it's really safe, only when the server which that tool reached happened to be fixed.
 2. Check their internal systems, to make sure that no stolen staff passwords were used by attackers to get into their systems
    and set up sneaky back-doors to get back in.
 3. Generate a new secret (“key”), for a replacement padlock for your web-browser.
 4. Buy a shiny new certificate to show to browsers, for secure access
 5. Deploy the new secret and certificate, to all their servers
 6. Pay to have the old, unsafe, certificate “revoked”,
    so that browsers which actually check such things can be protected against bad guys using the stolen secret.
 7. Let you, their customers or users, know that all of this has been done.

or:

 1. Check that they didn't use the broken software anywhere, no really truly.
 2. Let you, their customers or users, know that you're in the clear.

**There are no safe short-cuts**

**This has to happen for EVERY WEBSITE WHICH HAS PASSWORDS**.  Every.  Single.  One.

That's why this is such a big, huge, deal.

So, how do you know which sites have done this?
You have to find their announcement.
We're tracking announcements, to build a big searchable list which you can use to find details for a given site.

Have fun changing those passwords.

Oh, and now is probably a good time to look into
[password management tools][] and read some [password creation advice][].


[password management tools]: password-management-tools
[password creation advice]: password-creation-advice
