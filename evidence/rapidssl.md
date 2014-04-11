---
layout: default
description: RapidSSL advert/impact email
---

### Date: 2014-04-11
### Company: RapidSSL

RapidSSL is aware of the vulnerability, dubbed “Heartbleed”, which is a security concern for users of OpenSSL, a widely-used opensource cryptographic software library. It can allow attackers to read the memory of the systems using vulnerable versions of OpenSSL library (1.0.1 through 1.0.1f). This may disclose the secret keys of vulnerable servers, which allows attackers to decrypt and eavesdrop on SSL encrypted communications and impersonate service providers. In addition, other data in memory may be disclosed, which conceivably could include usernames and passwords of users or other data stored in server memory. 

To be clear, this is a vulnerability of the OpenSSL library, and not a flaw with SSL/TLS, nor certificates issued by RapidSSL. At no time were RapidSSL’s SSL or Code-Signing roots and intermediates at risk, nor was there ever an issue with RapidSSL certificates.

## Steps to Success:

 * Identify if your web servers are vulnerable (running OpenSSL versions 1.0.1 through 1.0.1f with heartbeat extension enabled).  Use our [SSL Toolbox][] to detect this.  If you’re running a version of OpenSSL prior to 1.0.1, no further action is required.
 * If your server is impacted, update to the latest patched version of OpenSSL (1.0.1g), or recompile OpenSSL without the heartbeat extension.
 * Generate a new Certificate Signing Request (CSR).
 * [Reissue][] any SSL certificates for affected web servers using the new CSR (do this after moving to a patched version of OpenSSL).
 * Install the new SSL certificate and test your installation.
 * After the new certificate is successfully installed, [revoke][] any certificates that were replaced.
 * Website administrators should also consider resetting end-user passwords that may have been visible in a compromised server memory.
 * Always refer back to the [Knowledge Base][] for further support more information.
 * If you have additional questions, please contact your SSL Reseller for further support and more information.

Best Regards,


Tom Powledge  
V.P., Trust Services

[SSL Toolbox]: https://ssltools.geotrust.com/checker/
[Reissue]: https://knowledge.rapidssl.com/support/ssl-certificate-support/index?page=content&actp=CROSSLINK&id=SO5757
[revoke]: https://knowledge.rapidssl.com/support/ssl-certificate-support/index?page=content&id=SO9717&actp=search&viewlocale=en_US
[Knowledge Base]: https://knowledge.rapidssl.com/support/ssl-certificate-support/index?page=content&id=AD834
