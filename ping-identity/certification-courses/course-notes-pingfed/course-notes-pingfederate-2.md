# Course Notes - PingFederate 2

## Administrative Console Introduction

* Login to the admin console. `https://pf.int.course-ping.com:9999:/pingfederate/app`
* On the left of the console, each enabled server role should be displayed. Server Configuration should be shown below.

![Administrator Menu with all three roles enabled.](../../../.gitbook/assets/image.png)

### Identity Provider

#### Application Integration

{% hint style="info" %}
Notes: "Used to create adapters which will connect to your authentication and user store backend"
{% endhint %}

* Adapters: 
* Default URL:
* Application Endpoints:

#### Authentication Policies

{% hint style="info" %}
Notes: "manage your authentication policies, selectors and contracts for the IdP role"
{% endhint %}

* Policies:
* Selectors:
* Policy Contracts:
* Sessions:

#### Local Identity

{% hint style="info" %}
Notes: "Allow users to authenticate against a third party Identity Provider"
{% endhint %}

* Identity Profiles: 

#### SP Connections

{% hint style="info" %}
Notes: Shows your SP \(Service Provider\) Connections.
{% endhint %}

### Service Provider

#### IDP-TO-SP Bridging

Note: "Provided for special use cases when PingFed is acting as both an IdP and an SP... user attributes from an IdP adapter are used to create an authentication session via an SP adapter on the same PingFed Server"

* Adapter-to-Adapter Mappings: 

#### Federation Info

* Protocol Endpoints: list of all of the protocol endpoints for this PingFeds SP Role

#### SP Affiliations

"Manage links to affiliated service partners as defined by the SAML 2.0 Spec."

### OAuth Server

#### Authorization Server

{% hint style="info" %}
Notes: 
{% endhint %}

*  Authorization Server Settings
* Scope Management
* Client Settings
* Client Registration Policies

#### Grant Mapping

{% hint style="info" %}
Notes: 
{% endhint %}

* IdP Adapter Mapping
* Authenication Policy Contract Mapping
* Resource owner credentials Mapping

{% hint style="info" %}
ROPC \(Resource Owner Password Credentials\) Grant Type:
{% endhint %}

#### Clients

?

### Server Configuration

#### Token Mapping

{% hint style="info" %}
Notes: Controls now attribute are mapped to access tokens. Also configure OpenID Connect polices and mappings.
{% endhint %}

* Access Token Management: 

#### Authorization Server Info

{% hint style="info" %}
Notes: 
{% endhint %}

* OAuth Endpoints

  








