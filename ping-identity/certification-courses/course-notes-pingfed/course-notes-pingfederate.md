# Course Notes – PingFederate 1

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
    * multi core Intel xeon. 4 CPU/cores or higher
    * 4GB of memory with 1.5GB for PingFed
    * 1GB of Disk 
* PingFed is a Java App - Supports
  * Oracle Java SE Runtime \(Server JRE\) 8
  * Oracle Java SE Development Kit 11 LTS
  * OpenJDK 11
  * Amazon Corretto 8
  * Amazon Corretto 11
  * "Other JREs can be used and may be supported on a best effort basis" 
* Web browser support
  * Runtime Server
    * Google Chrome
    * Google Android Chrome 9
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
* Data Store Integration
  * for Attribute Lookup, Provisioning, OAuth client config and OAuth persistent grants
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
* Request a license key

For _Windows_, use the MSI.  
For _RHEL_, use bash install script to automatically download/install as a daemon using systemd.  
For _all other Linux OSes_, there is a full distro zip. Configuration/daemon setup must be done manually.

### Notes: PingFed Start up files

* run.sh and run.bat in the &lt;install path/bin&gt; folder \(to m $$a = b$$ anually start the server in a console\)
* run.properties \(contains settings that are only applied at startup\)

### Installation Tasks on Windows Server

* Run PingFed Installation MSI
* Select Operational Mode
  * Standalone \(For a single node that will operate independently\)
  * Clustered Admin Node \(Only one node in a cluster can be the admin node\)
  * Clustered  Runtime Node
* Pick the PingFed Admin Console HTTPS/API TCP Port \(Default is 9999\)
* Pick the PingFed Runtime Engine HTTPS TCP Port \(Default is 9031\)
  * Supports a secondary HTTPS Port for additional security measures \(used with WS-Federation or SAML artifact binding types\)
* Pick the PingFed install path
* Complete the MSI Installation stage \(should be running now as a windows service\)
* The PingFed Admin Portal should be avaiable now - https://localhost:9999/pingfederate/app

### Installation Tasks on RHEL

* Disable SELinux \(ONLY DURING INSTALLATION?\)
* Download and run the installation script `./pf-install.sh` as root
* Select Operational Mode
  * Standalone \(For a single node that will operate independently\)
  * Clustered Admin Node \(Only one node in a cluster can be the admin node\)
  * Clustered  Runtime Node
* Pick the IP the admin console should bind \(Default to 0.0.0.0\)
* Pick the PingFed Admin Console HTTPS/API TCP Port \(Default is 9999\)
* Pick the PingFed Runtime Engine HTTPS TCP Port \(Default is 9031\)
  * Supports a secondary HTTPS Port for additional security measures \(used with WS-Federation or SAML artifact binding types\)
* Complete the script prompts to setup the service as a daemon using systemd
* The PingFed Admin Portal should be available now - https://localhost:9999/pingfederate/app

### Initial Config Wizard using Admin console

Note: the PingFed Admin portal creates a selfsigned TLS cert for HTTPS by default - this can be replaced later.

* Accept the PingFed License Agreement \(Most definitely read the whole thing... yeah...\)
* Optional: Connect to PingOne if you have one premade.
* Upload the PingFed License File
* Pick the BASE URL as a FQDN \(Example: https://admin.pingfed.darkarts.club:9031\)
* Pick an ENTITYID. I assume this is a unique identifier. \(Example: MyPingFedInstance\)
* Pick the Server Roles \(there can be enabled/disabled later\)
  * Identity Provider
  * Service Provider
  * OAuth Authorisation Server
* Optional: Connect to a Microsoft Active Directory Domain
* Pick the username/password for the administrator account.
* View configuration summary
* Complete the wizard. `Click Done`.

### Upgrading

* Ping recommend performing the upgrade in a test environment.
* PingFed can be updated using the installer on Windows to automatically update the Windows Services paths.
* PingFed supports using the PingFed Upgrade Utility on Windows/RHEL/Other Linux.
* The PingFed Upgrade will **only copy** existing integration kids to the updated release - 
* To upgrade integration kits after the PingFed upgrade, download the integration packages from the PingFed Webpage as usual.

### Upgrade Checklist

* Read the PingFed Release Notes / Upgrade guide for every releas
* Obtain a new license key is required
* Confirm the JRE version required and update the JAVA\_HOME/PATH env vars if required.
* Complete any unfinished/draft connections as they will be deleted

### Upgrade Process for Windows Server \(using the MSI\)

* Download the PingFed Installer MSI
* Click next twice
* View the upgrade logs for any errors/warnings.
* Complete the MSI Upgrade stage \(should be running now as a windows service\)

### Upgrade Process for Windows Server \(using the upgrade utility\)

* Download the PingFed Upgrade Utility
* Read the utility documentation
* Upgrade the PingFed using the upgrade utility
  * To upgrade from 9.1.4 to 9.2.0`c:\pf-upgrade-9.2.0\bin\upgrade "<path to 9.1.4>" "<path to 9.2.0>" "<path to pingfederate-9.2.0.zip>"` 
* Fix the broken path for PingFederate Windows Service \(not required using MSI installer\)

### Upgrade Process for RHEL \(using the installation script\)

* Download the PingFed Installation Script for the new version
* Read the script documentation
* Upgrade the PingFed instance using the install script
  * to upgrade an existing PingFed 9 to 9.2.0 `c./pf-install.sh -u -f /opt/PingIdentity/pingfederate-9etc -o /opt/PingIdentity/pingfederate-9.2.0`
* View the upgrade logs for any errors/warnings
* Reset the PingFed Instance manually \(update systemd service paths if required\)

### Upgrade Process for RHEL \(using the upgrade utility\)

* Download the PingFed Upgrade Utility
* Download the PingFed 9.2.0 Disto zip
* Read the utility documentation
* Upgrade the PingFed using the upgrade utility
  * To upgrade from 9.1.4 to 9.2.`./tmp/pf-upgrade-9.2.0/bin/upgrade "/opt/PingIdentity/pingfederate-9etc" "/opt/PingIdentity/pingfederate-9.2.0" "<path to pingfederate-9.2.0.zip>"` 
* View the upgrade logs for any errors/warnings
* Reset the PingFed Instance manually \(update systemd service paths if required\)

### Post-Upgrade tasks

* Review database changes and log configurations
* Copy any customerised files or settings to the new installation such as Velocity HTML templates for user facing scenes, email notifications, and custom Jetty/JBOSS configurations.



