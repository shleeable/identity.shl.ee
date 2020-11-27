# Cert Notes – PingFederate

### Technologies and Concepts \(Recommended Reading\):

* JWT \(JSON Web Tokens\) [https://jwt.io/introduction/](https://jwt.io/introduction/)
* PKI [https://www.youtube.com/watch?v=QCvHWA7qQNI](https://www.youtube.com/watch?v=QCvHWA7qQNI)
* SSL/TLS [https://www.youtube.com/watch?v=iQsKdtjwtYI](https://www.youtube.com/watch?v=iQsKdtjwtYI)
* HTTP/HTTPS [https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/](https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/) [https://www.youtube.com/watch?v=JCvPnwpWVUQ](https://www.youtube.com/watch?v=JCvPnwpWVUQ) [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)
* SAML [https://www.youtube.com/watch?v=0fmNoqz6Urw](https://www.youtube.com/watch?v=0fmNoqz6Urw) [https://www.pingidentity.com/content/dam/pic/downloads/resources/white-papers/en/saml-101-white-paper.pdf](https://www.pingidentity.com/content/dam/pic/downloads/resources/white-papers/en/saml-101-white-paper.pdf) [http://docs.oasis-open.org/security/saml/v2.0/saml-core-2.0-os.pdf](http://docs.oasis-open.org/security/saml/v2.0/saml-core-2.0-os.pdf)
* SSO & Federation [https://www.pingidentity.com/en/company/blog/posts/2017/what-is-single-sign-on-sso.html](https://www.pingidentity.com/en/company/blog/posts/2017/what-is-single-sign-on-sso.html) [https://docs.pingidentity.com/csh?pubname=developer&context=dev\_fed\_sso\_overview](https://docs.pingidentity.com/csh?pubname=developer&context=dev_fed_sso_overview) \(broken?\) [https://www.pingidentity.com/en/lp/ultimate-guide-to-sso.html](https://www.pingidentity.com/en/lp/ultimate-guide-to-sso.html)
* OAuth [https://www.pingidentity.com/en/resources/client-library/articles/oauth.html](https://www.pingidentity.com/en/resources/client-library/articles/oauth.html) [https://oauth.net/getting-started/](https://oauth.net/getting-started/) [https://oauth.net/2/](https://oauth.net/2/)
* OpenID Connect [https://openid.net/connect/](https://openid.net/connect/) [https://pingidentity.docebosaas.com/learn/course/329/play/2060:243/course-introduction-v2;lp=39](https://pingidentity.docebosaas.com/learn/course/329/play/2060:243/course-introduction-v2;lp=39) \(Broken!\)

### PingFederate Overview:

* Single Sign-On  using SAML/OAUTH/OpenID/SCIM.
* Authentication Authority  Auth polities /w MFA and directory services intergration.
* Workspace, Customer, and Partner Identities provides registration/profile management/password reset services.. while connecting to social media authenications methods.

### PingFederate Features:

* Identity Provider \(IdP\) Regarding Browser SSO, PingFed can authenticate users \(using login or directory services\) and using industry standard protocols such as SAML/WS-Federation/WS-Trust, PingFed can build _outbound assertions_ for supported applications. 
* Service Provider \(SP\) Pingfed supports acceptiong _inbound assertions_ and passing the _user attributes_ from these assertions. Example: Using Social media profiles \(Twitter\) using the supported OpenID connectors.
* Account Provisioning  
* OAUTH
* OpenID Connect
* Relying Party

