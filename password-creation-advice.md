---
layout: default
description: Advice on choosing passwords.
---

There is much advice about how to choose passwords, and much of the advice is bad.
It doesn't consider the threat models, it doesn't consider human fallibility.

You do not want to remember many passwords.
You should remember as few passwords as possible, while still using a different password for every site.
So the best solution is to use one of the [password management tools][] and let it generate very strong passwords for you.

Then you just remember your password to get into that tool, and perhaps one or
two others where you have no choice, such as for buying things on a tablet
computer.

You take backups of the password tool's database, and you consider printing
out the passwords to put them in a safe, protected by trained attack tigers.

If you really must treat passwords for remote web-sites as something which
mere humans have to remember, and you accept that you're fighting a losing
battle but are prepared to fight valiantly nonetheless, then here is some
advice.

 * Use the “mnemonic phrase” approach to generating a password; make it at
   least 10 words long.
   - Example password (do not use!): `cd!b&dNamh1kt`
   - Mnemonic: “cats do not bounce and do not ask me how I know this”
   - Note that the password ends up being unpredictable, but you can still
     manage to remember the mnemonic with only a little practice
   - I was introduced to this approach, at the very latest, when I started
     work at an ISP in 1999.  It's the only approach which has stood the test
     of time and which experts still recommend.
     <https://www.schneier.com/blog/archives/2014/03/choosing_secure_1.html>
 * Do not use anything based on words being present in the password, or small
   changes to words, or facts about you, or anything which might be figured
   out by the Veronica Mars folks in your life.
 * Do not make a password which consists of a few full words; XKCD was wrong
 * Keep written records of the mnemonic somewhere safe; if you know how to use
   encryption software, then that's the safest (and you don't need to write
   down the passphrase), but if you're more worried about attackers breaking
   down your door than about forgetting a password of mnemonic, then:
   - you have a strange life;
   - use a password management tool instead.
 * Don't use a password less than 10 characters.  Aim to be a little longer.
 * You _might_ end up having to avoid some characters for badly broken
   websites which can't handle them; if `&` or `'` or `"` results in weird
   error messages instead of “password not allowed, here's the allowed
   characters” then stop using the site -- it's dangerously broken.

[password management tools]: password-management-tools
