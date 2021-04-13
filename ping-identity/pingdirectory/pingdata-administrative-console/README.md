# PingData Administrative Console

## Configuration Sections

### Web Services and Applications

* **Consent Definitions** 
  * A Consent Definition represents a type of consent to share data.
  * Each Consent Definition represents an individual's consent to share particular data \(the "what"\) for a particular purpose \(the "why"\). Consent Definitions always should have one or more child Consent Definition Localizations, which contain the localized text that is presented to an individual when collecting consent. 
* **Consent Service** 
  * The Consent Service contains the properties that affect the overall operation of the Directory Server Consent API. 
* **Constructed Attributes** 
  * A constructed attribute constructs values for an attribute by using a combination of fixed text and values of other attributes from the entry. Note that just creating one of these objects will not have any effect. The object must be referenced from another configuration object such as a Delegated Admin Resource Type. 
* **Delegated Admin Attribute Categories**
  * A Delegated Admin Attribute Category defines a collection of attributes which belong together. Attributes in the same Delegated Admin Attribute Category are grouped together when displayed to the end user. 
* **Delegated Admin Rights**
  * A Delegated Admin Rights defines a user, or group of users, who can manage resources through the Delegated Admin API. ****
* **HTTP Configuration**
  * The HTTP Configuration provides the configuration for the Directory Server HTTP service. ****
* **HTTP Servlet Cross Origin Policies**
  * This object describes a configuration for handling Cross-Origin HTTP requests using the Cross Origin Resource Sharing \(CORS\) protocol. An instance of HTTP Servlet Cross Origin Policy can be associated with zero or more HTTP Servlet Extensions to set the Cross-Origin policy for those servlets. ****
* **HTTP Servlet Extensions**
  * HTTP Servlet Extensions may be used to define classes and initialization parameters that should be used for a servlet invoked by an HTTP connection handler. ****
* **REST Resource Types**
  * A REST Resource Type defines a specific type of resource exposed by the Delegated Admin HTTP servlet extension, and accessible through the Delegated Admin application. ****
* **SCIM Resource Types**
  * SCIM Resource Types provide a view of a class of Directory entries over a SCIM2 interface. The SCIM Resource Type determines the attributes that can be accessed by a client application. ****
* **SCIM Schemas**
  * SCIM Schemas defines a SCIM schema comprising a set of attributes. ****
* **Web Application Extensions**
  * Web Application Extensions may be used to define web applications to be hosted by the server. ****

### Core

* Client Connection Policies
  * 
* Connection Handlers
  * 
* DN Maps
  * 
* Extended Operation Handlers
  * 
* External Servers
  * 
* Global Configuration
  * 
* JSON Attribute Constraints
  * 
* Locations
  * 
* Plugin Root
  * 
* Recurring Tasks
  * 
* Recurring Task Chains
  * 
* Result Code Maps
  * 
* Root DN
  * 
* Root DSE Backend
  * 
* Soft Delete Policies
  * 
* Virtual Attributes
  * 
* Work Queue
  * 

### Backends, Indexing, and Caching

* Backends
  * 
* Uncached Attribute Criteria
  * 
* Uncached Entry Criteria
  * 

### Authentication and Password Management

* Certificate Mappers
  * 
* Failure Lockout Actions
  * 
* ID Token Validators
  * 
* Identity Mappers
  * 
* Password Generators
  * 
* Password Policies
  * 
* Password Storage Schemes
  * 
* Password Validators
  * 
* SASL Mechanism Handlers
  * 

### Logging, Monitoring, and Notifications

* Account Status Notification Handlers
* Alarm Manager
* Alert Handlers
* Gauges
* Gauge Data Sources
* LDAP SDK Debug Logger
* Log Field Mappings
* Log File Rotation Listeners
* Log Publishers
* Log Retention Policies
* Log Rotation Policies
* Monitor Providers
* Monitoring Endpoints

### Security and Authorization

* Access Control Handler
* Access Token Validators
* Cipher Stream Providers
* Data Security Auditors
* Key Manager Providers
* Key Pairs
* OAuth Token Handlers
* OTP Delivery Mechanisms
* Obscured Values
* Sensitive Attributes
* Trust Manager Providers
* Trusted Certificates
* Vault Authentication Methods

### Connection and Operation Classification

* **Connection Criteria**
  * Connection Criteria define sets of criteria for grouping and describing client connections based on a number of properties, including the protocol, client address, connection security, and authentication state for the connection. 
* **Request Criteria**
  * Request Criteria define sets of criteria for grouping and describing operation requests based on a number of properties, including properties for the associated client connection, the type of operation, target entry, request controls, target attributes, and other operation-specific items. 
* **Result Criteria**
  * Result Criteria define sets of criteria for grouping and describing operation results based on a number of properties, including properties of the associated client connection and operation request, the result code, response controls, privileges missing or used, and other operation-specific items. 
* **Search Entry Criteria**
  * Search Entry Criteria define sets of criteria for grouping and describing search result entries based on a number of properties, including properties of the associated client connection and operation request, the entry location and contents, and included controls. 
* **Search Reference Criteria**
  * Search Reference Criteria define sets of criteria for grouping and describing search result references based on a number of properties, including properties of the associated client connection and operation request, the reference contents, and included controls.

### Replication

* **Replication Assurance Policies**
  * A Replication Assurance Policy is used to specify the local and remote replication assurance levels and a timeout to use for update operations. Optionally, request and connection criteria can be configured in the policy to allow matching a policy to requests that satisfy such criteria. 
* **Synchronization Providers**
  * Synchronization Providers are responsible for handling synchronization of the Directory Server data with other Directory Server instances or other data repositories.

### Topology

* **License**
  * A license key is required for Directory Server use and can be imported from a license file. ****
* **Server Groups**
  * The Server Group represents a server group within the system. For example, servers may be grouped by location. ****
* **Server Instances**
  * The Server Instance represents a single server within the system that has one of the UnboundID products installed on it. ****
* **Topology Admin Users**
  * The Topology Admin User represents an administrative user that is stored in the topology registry and hence globally available across all servers in the topology.

