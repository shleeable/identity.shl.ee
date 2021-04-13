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
  * A Client Connection Policy is used to classify a client connection based on the client address, protocol, identity, and whether it is using a secure communication mechanism. It may be used to control which types of operations that client may perform and the types of data that it may access. 
* Connection Handlers
  * Connection Handlers are responsible for handling all interaction with the clients, including accepting the connections, reading requests, and sending responses. 
* DN Maps
  * A DN Map constructs DN values from attributes and the DN of a source entry, and fixed text. It is used to construct the DN for an entry as well as values for attributes that store DNs such as isMemberOf. 
* Extended Operation Handlers
  * Extended Operation Handlers processes the different types of extended operations in the server. 
* External Servers
  * External Servers are used to identify external servers and to provide a mechanism to connect to them. 
* Global Configuration
  * The Global Configuration contains properties that affect the overall operation of the Directory Server. 
* JSON Attribute Constraints
  * JSON Attribute Constraints may be used to specify a number of properties and constraints for JSON objects to be stored in attributes with a "JSON object" syntax. Each JSON Attribute Constraints definition will be associated with a set of json-field-constraints definitions that can collectively define a complete or partial schema for the JSON objects, and may also provide additional information about the way the server should treat those fields \(e.g., whether any of the fields should be indexed for faster searching, or have their values tokenized for more compact storage\). 
* Locations
  * Locations are used to define collections of servers which may have similar performance characteristics when accessed from this Directory Server. For example, a separate Location may be defined for each data center. 
* Plugin Root
  * The Plugin Root defines the parent entry for all plug-ins defined in the server. 
* Recurring Tasks
  * Recurring Tasks encapsulate the information to be included in administrative tasks that are to be invoked on a recurring basis within the server. Recurring Tasks must be included in a recurring task chain to actually be scheduled for processing. 
* Recurring Task Chains
  * Recurring Task Chains are sets of one or more recurring tasks that will automatically be invoked on a regular basis according to a defined schedule. 
* Result Code Maps
  * Result Code Maps provide a way to customize the result codes that should be returned for various error conditions. 
* Root DN
  * The Root DN configuration contains all the Root DN Users defined in the Directory Server. In addition, it also defines the default set of privileges that Root DN Users automatically inherit. 
* Root DSE Backend
  * The Root DSE Backend contains the Directory Server root DSE. 
* Soft Delete Policies
  * General policy settings for soft delete operations. 
* Virtual Attributes
  * Virtual Attributes are responsible for dynamically generating attribute values that appear in entries but are not persistently stored in the backend. 
* Work Queue
  * The High Throughput Work Queue may be used to ensure that operations requested of the server are processed in a timely manner. It maintains multiple blocking queues which are serviced by separate sets of worker threads to avoid too much contention around a single blocking queue.

### Backends, Indexing, and Caching

* Backends
  * Backends are responsible for providing access to the underlying data presented by the server. 
* Uncached Attribute Criteria
  * Uncached Attribute Criteria objects are used to indicate which attributes should be stored in the uncached-id2entry database \(rather than the id2entry database\) in order to reduce the amount of memory required to cache them. 
* Uncached Entry Criteria
  * Uncached Entry Criteria objects are used to indicate which entries should be stored in the uncached-id2entry database \(rather than the id2entry database\) in order to reduce the amount of memory required to cache them.

### Authentication and Password Management

* Certificate Mappers
  * Certificate Mappers are responsible for establishing a mapping between a client certificate and the entry for the user that corresponds to that certificate. 
* Failure Lockout Actions
  * Failure Lockout Actions may be used to specify the behavior that the server should exhibit for accounts that have too many failed authentication attempts. 
* ID Token Validators
  * ID Token Validators validate ID tokens issued by an OpenID Connect provider used for single sign-on \(SSO\). 
* Identity Mappers
  * Identity Mappers are responsible for establishing a mapping between an identifier string provided by a client, and the entry for the user that corresponds to that identifier. Identity Mappers are used to process several SASL mechanisms to map an authorization ID \(e.g., a Kerberos principal when using GSSAPI\) to a directory user. They are also used when processing requests with the proxied authorization control. 
* Password Generators
  * Password Generators are used by the password modify extended operation to construct a new password for the user. 
* Password Policies
  * Password Policies define a number of password management rules, as well as requirements for authentication processing. 
* Password Storage Schemes
  * Password Storage Schemes encode new passwords provided by users so that they are stored in an encoded manner. This makes it difficult or impossible for someone to determine the clear-text passwords from the encoded values. 
* Password Validators
  * Password Validators are responsible for determining whether a proposed password is acceptable for use and could include checks like ensuring it meets minimum length requirements, that it has an appropriate range of characters, or that it is not in the history. 
* SASL Mechanism Handlers
  * The SASL mechanism handler configuration entry is the parent for all SASL mechanism handlers defined in the Directory Server. 

### Logging, Monitoring, and Notifications

* Account Status Notification Handlers
  * 
* Alarm Manager
  * 
* Alert Handlers
  * 
* Gauges
  * 
* Gauge Data Sources
  * 
* LDAP SDK Debug Logger
  * 
* Log Field Mappings
  * 
* Log File Rotation Listeners
  * 
* Log Publishers
  * 
* Log Retention Policies
  * 
* Log Rotation Policies
  * 
* Monitor Providers
  * 
* Monitoring Endpoints
  * 

### Security and Authorization

* Access Control Handler
  * 
* Access Token Validators
  * 
* Cipher Stream Providers
  * 
* Data Security Auditors
  * 
* Key Manager Providers
  * 
* Key Pairs
  * 
* OAuth Token Handlers
  * 
* OTP Delivery Mechanisms
  * 
* Obscured Values
  * 
* Sensitive Attributes
  * 
* Trust Manager Providers
  * 
* Trusted Certificates
  * 
* Vault Authentication Methods
  * 

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

