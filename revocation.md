---
layout: default
description: Certificate Revocation
---

Certificates can need to be revoked. There are few good solutions, but with
Heartbleed a lot of certs need to be revoked.

Certificates are issued by a “Certificate Authority” (CA), which is simply a
certificate configured by clients to be trusted to sign other certificates.
You probably haven't made this choice for yourself, someone else did it for
you: a browser vendor, an operating system vendor, or perhaps a local
administrator.  There are over 200 CAs which most clients trust, including
government agencies of many and varied nations.  That's how bad the house of
cards is, to start with.

But with Heartbleed, it looks as though (non-nation-state) criminals have been
gathering data, so those cards are on fire.  Revocation is how we put out the
fire, for now, and hope that there are few smouldering embers waiting to burst
back into flame.

The situation is not pretty.

The oldest mechanism is a “Certificate Revocation List”, or CRL, which is a
file signed by the CA's key listing the serial numbers of all revoked certs.
It can get bulky, but it's something which can be cached and retrieved in bulk
periodically.  It's probably about to get too bulky, but we'll find out over
the coming weeks what happens.

Next is the “Online Certificate Status Protocol”, OCSP, which is a way to ask
a CA to give a signed statement that a particular existing certificate is
still valid.  It has a lifetime, perhaps measured in hours or days, instead of
the years of the original certificate.

If browsers use OCSP to talk to the CAs, then CAs (or people who sniff their
traffic) can track all of the people visiting sites which use certificates
issued by that CA.  This is a major privacy violation and creates a new
tempting target.  Also, if the CA appears to be down then the only safe action
is to not connect to the site, so the CAs become single points of failure.
Who here thinks that a typical Certificate Authority is as good at running a
reliable site as is Google?

There's an alternative, called “OCSP Stapling”, in which the web Server
requests the OCSP proof and can give it to clients in the TLS handshake.  The
server operator already has a business relationship with the CA, has exchanged
money (or whatever) and the CA already knows the servers must exist, because
they issued the certs.  There's no privacy violation.  The server can start
trying to renew before the old OCSP proof expired, so that if there's a server
glitch, we can ride it out -- as long as the CA OCSP server can respond at
some point after the web-server starts trying to renew.  (If you know DHCP,
think of the T1 timer.)  If you have lots of servers, you can arrange to have
just one fetch the proof and distribute it to the others.

There is very little client support for OCSP Stapling.  Firefox appears to
support it now.  If you know of other clients, please do let us know!

There is server support of OCSP Stapling in current versions of nginx, Exim
(experimental feature, can be enabled at build time), Apache and a few others.

The sensible choices are for clients to prioritize OCSP Stapling support, and
to support CRLs.  Supporting clients making OCSP queries to CAs is a major
violation of trust.

So in summary: the tools people are using today are mostly not adequate to
safely recover from Heartbleed and many people will be making large Leaps of
Faith to recover.
