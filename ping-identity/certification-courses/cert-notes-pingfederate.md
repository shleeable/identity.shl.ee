# Course Notes – PingFederate

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

### PingFederate Features/Server Roles:

* Identity Provider \(IdP\) Regarding Browser SSO, PingFed can authenticate users \(using login or directory services\) and using industry standard protocols such as SAML/WS-Federation/WS-Trust, PingFed can build _outbound assertions_ for supported applications. 
* Service Provider \(SP\) PingFed supports accepting _inbound assertions_ and passing the _user attributes_ from these assertions. Example: Using Social media profiles \(Twitter\) using the supported OpenID connectors. 
* Account Provisioning PingFed supports SCIM to create/manage user accounts. As an IdP, PingFed can create user accounts on outbound SPs. 
* OAuth 2.0 Protocol PingFed supports acting as a Oauth Authorization Server. "Allows a research owner, to grant auth to a client requesting access to a resource protected by a resource server"....  Example: SaaS provider wants access to social media account resources. 
* OpenID Connect \(Identity Layer built on OAuth 2.0\) Provides access to user information. "Who is making the request?" 
* Relying Party PingFed can act as a proxy? to complete the OAuth login on an OpenID Connect provider and pass the attributes onto a supported application.

### PingFed Deployment

Deployment as Stand Alone server \(direct to the internet/DMZ\) or via a reverse proxy server.

PingFed can be installed as Cluster - Multiple "Runtime Engine" with one Adminstrative Console.

Starting with PingFed 9.0, Adaptive Clusters support "dynamic discovery of cluster nodes". User state is stored in redundant replica sets.   
Cluster dynamic discover supports AWS EC2/S3/OpenStack Swift. allows for nodes to join/leave public and private cloud services. 

### PingFed Ecosystem

PingID as MFA provider  
PingOne - Multi tentent, Identity as a service solution.  
PingAccess - Identity enabled access management product. protects webapps/APIs by applying security policies to client requests. Using OAuth, PingFed can act as a authorisation source/Token provider for PingAccess.

### Installation Requirements

* OS Support
  * RHEL ES 6.10/7.6/8.0
  * Ubuntu 16.04 LTS/18.04 LTS
  * SUSE Enterprise 12 SP4/15 SP1
  * Oracle Enterprise 6.10/7.6/8.0
  * Windows Server 2016/2019
  * Docker 19.03.5
  * Amazon Linux 2
  * Apline 3.10 
* Hardware Requirements
  * Minimum recommendations
    * multi core intel xeon. 4 CPU/cores or higher
    * 4GB of memory with 1.5GB for PingFed
    * 1GB of Disk 
* PingFed is a Java App - Supports
  * Oracle Java SE Runtime \(Server JRE\) 8
  * Oracle Java SE Development Kit 11 LTS
  * OpenJDK 11
  * Amazon Corretto 8
  * Amazon Corretto 11
  * "Other JREs can be used and may be suported on a best effort basis" 
* Web browser support
  * Runtime Server
    * Google Chrome
    * Google Andorid Chrome 9
    * Mozilla Firefox
    * Apple Safari
    * Apple Safari iOS
    * Microsoft Edge
    * Microsoft IE 11 or higher
  * Admin Console
    * Google Chrome
    * Mozilla Firefox
    * Microsoft IE 11 or higher 
* Network requirements
  * Port 9999 TCP - Admin console
  * Port 9031 TCP - Runtime Engine
  * 443 TCP - HTTPS
  * 88 TCP/UDP - Active Directory and Kerberos Realms 
* Data Store Intergration
  * for Attribute Lookup, Privisioning, OAuth client config and OAuth persistent grants
    * Ping Directory
    * Microsoft Active Directory
    * Oracle Directory Service Enterprise Edition
    * Oracle Database
    * Oracle MySQL
    * PostgreSQL
    * MSSQL

### Pre-Installation Tasks

* Install a supported version of java
* Set JAVA\_HOME and PATH environment vars at system level
* Request a licence key

For Windows, use the MSI.  
For RHEL, use bash install script.  
For all OSes, there is a full distro zip.











