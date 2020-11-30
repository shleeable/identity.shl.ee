# Course Notes - PingFederate 2

## **Administrative Console Introduction**

* Login to the admin console. `https://pf.int.course-ping.com:9999:/pingfederate/app`
* On the left of the console, each enabled server role should be displayed. Server Configuration should be shown below.

![Administrator Menu with all three roles enabled.](../../../.gitbook/assets/image.png)

## Identity Provider

### Application Integration

{% hint style="info" %}
Notes: "Used to create adapters which will connect to your authentication and user store backend"
{% endhint %}

* Adapters: 
* Default URL:
* Application Endpoints:

### Authentication Policies

{% hint style="info" %}
Notes: "manage your authentication policies, authentication selectors and policy contracts for the IdP role"
{% endhint %}

* Policies:
* Selectors:
* Policy Contracts:
* Sessions:

### Local Identity

{% hint style="info" %}
Notes: "Allow users to authenticate against a third party Identity Provider"
{% endhint %}

* Identity Profiles: 

### SP Connections

{% hint style="info" %}
Notes: Shows your SP \(Service Provider\) Connections.
{% endhint %}

## Service Provider

### IDP-TO-SP Bridging

{% hint style="info" %}
Notes: "Provided for special use cases when PingFed is acting as both an IdP and an SP... user attributes from an IdP adapter are used to create an authentication session via an SP adapter on the same PingFed Server"
{% endhint %}

* Adapter-to-Adapter Mappings: 

### Federation Info

{% hint style="info" %}
Notes: "list of the protocol endpoints for this PingFeds IdP Role"
{% endhint %}

* Protocol Endpoints: 

### SP Affiliations

{% hint style="info" %}
Notes: "Manage links to affiliated service partners as defined by the SAML 2.0 Spec."
{% endhint %}

## OAuth Server

### Authorization Server

{% hint style="info" %}
Notes: "Manage global OAuth settings for the Authenization server. Management of your OAuth/OpenID connect scopes."
{% endhint %}

*  Authorization Server Settings
* Scope Management
* Client Settings
* Client Registration Policies

### Grant Mapping

{% hint style="info" %}
Notes: "Config for mapping user attributes into the persistent grant DB. Mapping can be done via the Adapters and Authentication Policy contracts. You can map clients using the ROPC \(Resource Owner Password Credentials\) Grant Type."
{% endhint %}

* IdP Adapter Mapping
* Authentication Policy Contract Mapping
* Resource owner credentials Mapping

### Clients

{% hint style="info" %}
Notes: "List of all the clients configured on the server. Add/modify or delete"
{% endhint %}

### Token Mapping

{% hint style="info" %}
Notes: "Controls now attribute are mapped to access tokens. Also configure OpenID Connect polices and mappings."
{% endhint %}

* Access Token Management: 

### Authorization Server Info

{% hint style="info" %}
Notes: "list of the protocol endpoints for this PingFed OAuth Server Role"
{% endhint %}

* OAuth Endpoints

## Server Configuration

### System Settings

{% hint style="info" %}
Notes: "Global server settings. Manage external data stores."
{% endhint %}

* Server Settings
* Connect to PingOne
* Data Stores
* IdP Discovery
* Redirect Validations

### Administrative Functions

{% hint style="info" %}
Notes: "Exporting \(SAML\) metadata. User accounts and licenses."
{% endhint %}

* Metadata Export \(SAML\)
* XML File Signatures
* Configuration Archive
* Account Management
* License Management
* Virtual Host Names

### Certification Management

{% hint style="info" %}
Notes: ""
{% endhint %}

* Trusted CAs
* SSL Server Certificates
* SSL Client Keys & Certificates
* Signing & Decryption Keys & Certificates
* OAuth & OpenID Connect Keys
* Certificate Revocation Checking
* Metadata URLs

### Authentication

{% hint style="info" %}
Notes: "Configure PCVs \(Password Credential Validators\)"
{% endhint %}

* Application Authentication
* Password Credential Validators
* Active Directory Domains/Kerberos Realms









