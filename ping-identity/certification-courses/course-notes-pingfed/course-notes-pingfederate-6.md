# Course Notes - PingFederate 6

## Adapters

Adapters are Plugins for PingFed - Java JAR files used to integrate PingFed with other infrastructure.

* First Mile Integration: IdP Adapters, Directory/Database Adapters
* Last Mile Integration: SP Adapters, Customer Apps, WebApps

**IdP Adapters** are used to handle Authentication, and if required pull attributes into PingFederate.

**SP Adapters** are used to take incoming user attributes from an incoming connection and pass them to the target application.

PingFederate comes bundled with a set of adapters built-in. 

* **HTML Form Adapter**: Used with \(PCV\) "password credential validators". Provides integration with LDAP datastores or direct user login using credentials maintained by PingFed.
* **HTTP Basic Adapter**: + Similar to HTML Form above.
* **Kerberos Adapter**: Provides desktop SSO experience for Windows environments. Supports \(AMA\) "Authentication Mechanism Assurance", and is recommended for new configurations over the existing/legacy \(IWA\) "Integrated Windows Authentication" Integration kit.
* **OpenToken Adapter:** Generic Interface to connect with standard applications \(Java/.Net\)
* **Composite Adapter:** Allows multiple configured IdP Adapters to execute in sequence. This is called "Adapter Chaining" may be used for single Adapter usage, or to support MFA via a series of adapters.

## Integration Kits

Integration Kits are packages that contain adapters used to connect to popular commercial solutions.

Wide range of solutions including commercial software, cloud identity providers, and popular SaaS services.

Language Kits for Java, .NET and PHP are available for connecting to customer applications.

**Integration Kits** include the compiled adapter JAR file, additional documentation and code examples/templates etc.

Example: PingFederate Server Add-ons page allows the latest version of kits to be downloaded. 

![](../../../.gitbook/assets/image%20%289%29.png)

## Outbound/Inbound Identity Adapters

**Outbound Identity Adapters** are used by identity providers to authenticate users and lookup attributes. Outbound assertions/Tokens are then sent to an SP.  
Examples: Microsoft AD, LDAP, RSA Secure ID, X.509, or a custom Adapter using the SDK to connect to Custom Authentication services.

**Inbound Identity Adapters** are used by SPs to pass incoming user attributes from PingFederate to an application.  
Eamples: Citrix, sharepoint, WebSphere, Apache, or a customer Adapter using the SDK or OpenToken SDK.

To install a new adapter, upload the JAR file to the `pingfederate/server/default/deploy/` directory.

## \(PCV\)  Password Credential Validators

Provides an authentication mechanism for various PingFederate components and configurations.

PCVs are used by certain adapters, such as the HTML Form Adapter or the HTTP Basic Adapter.

Multiple PCVs can be used with a single adapter to provide failover.

### PCV Types

* **LDAP Username PCV:** Validates Creds based on an LDAP look-up to an ORGs user-data store.
* **PingID PCV**: ?
* **PingOne Directory PCV**: ?
* **RADIUS Username PCV**: ?
* **Simple Username PCV**: ?

 



