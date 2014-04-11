---
layout: default
description: Comodo advert/impact email
---

### Date: 2014-04-11
### Company: Comodo

Dear Valued customer,

As you may or may not know, a recent vulnerability known as 'Heartbleed' was discovered in an OpenSSL which could theoretically allow an attacker to steal the private keys of SSL certificates.

We advise customers to running affected versions to patch OpenSSL, to get a replacement Comodo certificate and to revoke their previous certificate. We would also like to confirm that the vulnerability lies with the OpenSSL software and not with Comodo certificates, Comodo systems or Comodo CA keys. Comodo is not aware of any real-world exploits of this flaw at this point in time.

Full details of the vulnerability, including more technical details, can be found at: <http://heartbleed.com/>

Comodo have published a full customer advisory on our site here:
<http://www.comodo.com/e-commerce/ssl-certificates/openssl-advisory.php>

-- What is affected? --

OpenSSL versions affected:

 * 1.0.1 through to 1.0.1f (inclusive).


OpenSSL versions NOT affected:

 * 1.0.1g
 * 1.0.0 (entire branch)
 * 0.9.8 (entire branch)

The release of OpenSSL 1.0.1g on the 7th April 2014 fixes the bug.

-- Is my site affected? --

Customers can test whether they are affected by visiting <https://sslanalyzer.comodoca.com/> to verify the presence of this vulnerability.

-- How do I fix it? --

Any systems using vulnerable versions of OpenSSL need to be patched or updated. OpenSSL themselves have released a patch, and many other software vendors have updated their software as well.

Please contact your vendor for further details.

** Patch OpenSSL before you install your new certificate **.

If you put a new certificate onto a vulnerable server you risk compromising the key of the new certificate. Because there is a theoretical possibility that Heartbleed could already have been exploited, you must replace certificates on affected systems and the previous certificates should be revoked.

-- What about my certificates? --

If your servers are running OpenSSL versions 1.0.1 through 1.0.1f with the heartbeat extension enabled, you should take the following actions as soon and as quickly as possible to mitigate any possible damage:

 * Upgrade your server to the latest version of OpenSSL (version 1.0.1g or later).
 * Get a replacement certificate from Comodo and then revoke all certificates that have used on vulnerable version of OpenSSL. Start by creating a new key pair and Certificate Signing Request (CSR) on your webserver software.

Comodo, unlike other CAs, has a no-charge reissue policy - so replacing your certificate and maintaining the security of your website and your systems is simple and incurs no additional cost. To perform a reissue, please follow the normal procedures - reissuing via our web-interface, management portal or the APIs.

Should you need any additional assistance, please contact: <mailto:support@comodo.com> or submit a ticket to: <https://support.comodo.com/>

-- Other workarounds --

Only if you are unable to upgrade to the latest OpenSSL version, do one of the following:

 * Rollback to OpenSSL version 1.0.0 or earlier.
 * Recompile OpenSSL with the `OPENSSL_NO_HEARTBEATS` flag.

We will work with all customers and partner to ensure all affected servers are replaced.

Regards,  
The Comodo CA team  
<https://support.comodo.com/>
<mailto:support@comodo.com>
