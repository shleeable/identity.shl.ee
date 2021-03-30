# Course Notes - PingFederate 6

## Adapters

Adapters are Plugins for PingFed - Java JAR files used to integrate PingFed with other infrastructure.

* First Mile Integration: IdP Adapters, Directory/Database Adapters
* Last Mile Integration: SP Adapters, Customer Apps, WebApps

**IdP Adapters** are used to handle Authentication, and if required pull attributes into PingFederate.

**SP Adapters** are used to take incoming user attributes from an incoming connection and pass them to the target application.

PingFederate comes bundled with a set of adapters. 

* HTML Form Adapter: Used with PCV \(password credential validators\)
* HTTP Basic Adapter:
* Kerberos Adapter: Provides desktop SSO experience for Windows environments. Supports \(AMA\) "Authentication Mechanism Assurance", and 
* OpenToken Adapter:
* Composite Adapter:



