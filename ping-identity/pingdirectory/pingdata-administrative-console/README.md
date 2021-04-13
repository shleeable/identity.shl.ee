# PingData Administrative Console

## Configuration Sections

### Web Services and Applications

* \*\*\*\*[**Consent Definitions**](consent-definitions.md)\*\*\*\*
  * A Consent Definition represents a type of consent to share data.
  * Each Consent Definition represents an individual's consent to share particular data \(the "what"\) for a particular purpose \(the "why"\). Consent Definitions always should have one or more child Consent Definition Localizations, which contain the localized text that is presented to an individual when collecting consent. 
* \*\*\*\*[**Consent Service**](consent-service.md)\*\*\*\*
  * The Consent Service contains the properties that affect the overall operation of the Directory Server Consent API. 
* \*\*\*\*[**Constructed Attributes**](constructed-attributes.md)\*\*\*\*
  * A constructed attribute constructs values for an attribute by using a combination of fixed text and values of other attributes from the entry. Note that just creating one of these objects will not have any effect. The object must be referenced from another configuration object such as a Delegated Admin Resource Type. 
* \*\*\*\*[**Delegated Admin Attribute Categories**](delegated-admin-attribute-categories.md)\*\*\*\*
  * A Delegated Admin Attribute Category defines a collection of attributes which belong together. Attributes in the same Delegated Admin Attribute Category are grouped together when displayed to the end user. 
* \*\*\*\*[**Delegated Admin Rights**](delegated-admin-rights.md)\*\*\*\*
  * A Delegated Admin Rights defines a user, or group of users, who can manage resources through the Delegated Admin API. ****
* \*\*\*\*[**HTTP Configuration**](untitled-35.md)\*\*\*\*
  * The HTTP Configuration provides the configuration for the Directory Server HTTP service. ****
* \*\*\*\*[**HTTP Servlet Cross Origin Policies**](untitled-34.md)\*\*\*\*
  * This object describes a configuration for handling Cross-Origin HTTP requests using the Cross Origin Resource Sharing \(CORS\) protocol. An instance of HTTP Servlet Cross Origin Policy can be associated with zero or more HTTP Servlet Extensions to set the Cross-Origin policy for those servlets. ****
* \*\*\*\*[**HTTP Servlet Extensions**](untitled-33.md)\*\*\*\*
  * HTTP Servlet Extensions may be used to define classes and initialization parameters that should be used for a servlet invoked by an HTTP connection handler. ****
* \*\*\*\*[**REST Resource Types**](untitled-32.md)\*\*\*\*
  * A REST Resource Type defines a specific type of resource exposed by the Delegated Admin HTTP servlet extension, and accessible through the Delegated Admin application. ****
* \*\*\*\*[**SCIM Resource Types**](untitled-31.md)\*\*\*\*
  * SCIM Resource Types provide a view of a class of Directory entries over a SCIM2 interface. The SCIM Resource Type determines the attributes that can be accessed by a client application. ****
* \*\*\*\*[**SCIM Schemas**](untitled-30.md)\*\*\*\*
  * SCIM Schemas defines a SCIM schema comprising a set of attributes. ****
* \*\*\*\*[**Web Application Extensions**](untitled-29.md)\*\*\*\*
  * Web Application Extensions may be used to define web applications to be hosted by the server. ****

### Core

* \*\*\*\*[**Client Connection Policies**](untitled-28.md)\*\*\*\*
  * A Client Connection Policy is used to classify a client connection based on the client address, protocol, identity, and whether it is using a secure communication mechanism. It may be used to control which types of operations that client may perform and the types of data that it may access. 
* **Connection Handlers**
  * Connection Handlers are responsible for handling all interaction with the clients, including accepting the connections, reading requests, and sending responses. 
* **DN Maps**
  * A DN Map constructs DN values from attributes and the DN of a source entry, and fixed text. It is used to construct the DN for an entry as well as values for attributes that store DNs such as isMemberOf. 
* **Extended Operation Handlers**
  * Extended Operation Handlers processes the different types of extended operations in the server. 
* **External Servers**
  * External Servers are used to identify external servers and to provide a mechanism to connect to them. 
* **Global Configuration**
  * The Global Configuration contains properties that affect the overall operation of the Directory Server. 
* **JSON Attribute Constraints**
  * JSON Attribute Constraints may be used to specify a number of properties and constraints for JSON objects to be stored in attributes with a "JSON object" syntax. Each JSON Attribute Constraints definition will be associated with a set of json-field-constraints definitions that can collectively define a complete or partial schema for the JSON objects, and may also provide additional information about the way the server should treat those fields \(e.g., whether any of the fields should be indexed for faster searching, or have their values tokenized for more compact storage\). 
* **Locations**
  * Locations are used to define collections of servers which may have similar performance characteristics when accessed from this Directory Server. For example, a separate Location may be defined for each data center. 
* **Plugin Root**
  * The Plugin Root defines the parent entry for all plug-ins defined in the server. 
* **Recurring Tasks**
  * Recurring Tasks encapsulate the information to be included in administrative tasks that are to be invoked on a recurring basis within the server. Recurring Tasks must be included in a recurring task chain to actually be scheduled for processing. 
* **Recurring Task Chains**
  * Recurring Task Chains are sets of one or more recurring tasks that will automatically be invoked on a regular basis according to a defined schedule. 
* **Result Code Maps**
  * Result Code Maps provide a way to customize the result codes that should be returned for various error conditions. 
* **Root DN**
  * The Root DN configuration contains all the Root DN Users defined in the Directory Server. In addition, it also defines the default set of privileges that Root DN Users automatically inherit. 
* **Root DSE Backend**
  * The Root DSE Backend contains the Directory Server root DSE. 
* **Soft Delete Policies**
  * General policy settings for soft delete operations. 
* **Virtual Attributes**
  * Virtual Attributes are responsible for dynamically generating attribute values that appear in entries but are not persistently stored in the backend. 
* **Work Queue**
  * The High Throughput Work Queue may be used to ensure that operations requested of the server are processed in a timely manner. It maintains multiple blocking queues which are serviced by separate sets of worker threads to avoid too much contention around a single blocking queue.

### Backends, Indexing, and Caching

* **Backends**
  * Backends are responsible for providing access to the underlying data presented by the server. 
* **Uncached Attribute Criteria**
  * Uncached Attribute Criteria objects are used to indicate which attributes should be stored in the uncached-id2entry database \(rather than the id2entry database\) in order to reduce the amount of memory required to cache them. 
* **Uncached Entry Criteria**
  * Uncached Entry Criteria objects are used to indicate which entries should be stored in the uncached-id2entry database \(rather than the id2entry database\) in order to reduce the amount of memory required to cache them.

### Authentication and Password Management

* **Certificate Mappers**
  * Certificate Mappers are responsible for establishing a mapping between a client certificate and the entry for the user that corresponds to that certificate. 
* **Failure Lockout Actions**
  * Failure Lockout Actions may be used to specify the behavior that the server should exhibit for accounts that have too many failed authentication attempts. 
* **ID Token Validators**
  * ID Token Validators validate ID tokens issued by an OpenID Connect provider used for single sign-on \(SSO\). 
* **Identity Mappers**
  * Identity Mappers are responsible for establishing a mapping between an identifier string provided by a client, and the entry for the user that corresponds to that identifier. Identity Mappers are used to process several SASL mechanisms to map an authorization ID \(e.g., a Kerberos principal when using GSSAPI\) to a directory user. They are also used when processing requests with the proxied authorization control. 
* **Password Generators**
  * Password Generators are used by the password modify extended operation to construct a new password for the user. 
* **Password Policies**
  * Password Policies define a number of password management rules, as well as requirements for authentication processing. 
* **Password Storage Schemes**
  * Password Storage Schemes encode new passwords provided by users so that they are stored in an encoded manner. This makes it difficult or impossible for someone to determine the clear-text passwords from the encoded values. 
* **Password Validators**
  * Password Validators are responsible for determining whether a proposed password is acceptable for use and could include checks like ensuring it meets minimum length requirements, that it has an appropriate range of characters, or that it is not in the history. 
* **SASL Mechanism Handlers**
  * The SASL mechanism handler configuration entry is the parent for all SASL mechanism handlers defined in the Directory Server. 

### Logging, Monitoring, and Notifications

* **Account Status Notification Handlers**
  * Account Status Notification Handlers are invoked to provide notification to users in some form \(for example, by an email message\) when the status of a user's account has changed in some way. The Account Status Notification Handler can be used to notify the user and/or administrators of the change. 
* **Alarm Manager**
  * The Alarm Manager provides an interface between components that raise alarms and persistence of those alarms into the alarms backend. 
* **Alert Handlers**
  * Alert Handlers are used to notify administrators of significant problems or notable events that occur in the Directory Server. 
* **Gauges**
  * Gauges convey real-time, key performance indicators in the monitor backend, and can be configured to raise alarms when the measured value exceeds defined thresholds or matches specific string patterns. 
* **Gauge Data Sources**
  * A Gauge Data Source defines the source of gauge data obtained from the monitor backend. 
* **LDAP SDK Debug Logger**
  * The LDAP SDK Debug Logger may be used to capture and record debug messages generated by the UnboundID LDAP SDK for Java. 
* **Log Field Mappings**
  * The Log Field Mapping provides a mapping to column names in a table used to store log elements. 
* **Log File Rotation Listeners**
  * Log File Rotation Listeners allow the server to take some action whenever a log file is rotated out of service so that the server will start writing to a new file. Log File Rotation Listeners must not delete, move, rename, or otherwise alter rotated log files in any way. 
* **Log Publishers**
  * Log Publishers are responsible for distributing log messages from different loggers to a destination. 
* **Log Retention Policies**
  * Log Retention Policies are used to specify when log files should be cleaned. 
* **Log Rotation Policies**
  * Log Rotation Policies are used to specify when log files should be rotated. 
* **Monitor Providers**
  * Monitor Providers can be used to provide information about the state of the server or one of its components. 
* **Monitoring Endpoints**
  * A Monitoring Endpoint defines a destination where server metric data should be sent for monitoring, such as a Splunk indexer or a StatsD daemon.

### Security and Authorization

* **Access Control Handler**
  * The DSEE Compat Access Control Handler provides an implementation that uses syntax compatible with the Sun Java System Directory Server Enterprise Edition access control handler. 
* **Access Token Validators**
  * Access Token Validators are used to validate an access token that may be used to access protected resources of the Directory Server. An Access Token Validator is responsible for decoding the token and returning token metadata such as described in RFC 7662. 
* **Cipher Stream Providers**
  * Cipher Stream Providers are used to obtain cipher input and output streams which may be used to read and write encrypted data. 
* **Data Security Auditors**
  * Data Security Auditors are used to identify potential risks in the data stored in the Directory Server. 
* **Key Manager Providers**
  * Key Manager Providers are responsible for managing the key material that is used to authenticate a secure connection to its peer. 
* **Key Pairs**
  * The Key Pair represents a public-private key pair that may be used to provide credentials for digital signatures and public-key encryption. An administrator may either import an existing key-pair or have the system generate a new one. 
* **OAuth Token Handlers**
  * The OAuth Token Handler is used to support OAuth 2.0 bearer tokens in the SCIM HTTP Servlet Extension. Implementations are created in third-party code using the UnboundID Server SDK. Since RFC 6750 does not specify the format for the contents of a bearer token, the OAuthTokenHandler API allows us to handle different implementations of the token from different types of Authorization Servers. 
* **OTP Delivery Mechanisms**
  * OTP Delivery Mechanism are used to deliver one-time passwords to users for use with the UNBOUNDID-DELIVERED-OTP SASL mechanism. Delivery mechanisms should send a one-time password value to the user via some out-of-band mechanism \(e.g., e-mail, SMS, voice call, etc.\) rather than over LDAP. 
* **Obscured Values**
  * Obscured Values can be used to store arbitrary values in the configuration that will be stored in obscured form, in which the plaintext representation is not obvious from its obscured representation. This may be particularly useful when developing Server SDK extensions that may need to store credentials used to access external systems or other sensitive information. 
* **Sensitive Attributes**
  * Sensitive Attributes provide a means of declaring one or more attributes to contain sensitive data so that the server can enforce additional protection for operations attempting to interact with them. 
* **Trust Manager Providers**
  * Trust Manager Providers determine whether to trust presented certificates. 
* **Trusted Certificates**
  * The Trusted Certificate represents a trusted public key that may be used to verify credentials for digital signatures and public-key encryption. The public key is represented as an X.509v3 certificate. For example, when configured on an access token validator, it may be used to validate the signature of an incoming JWT access token before the product REST APIs consume the access token for Bearer token authentication. 
* **Vault Authentication Methods**
  * Vault Authentication Methods are used to authenticate to an instance of a HashiCorp Vault server in order to obtain an access token.

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

