# Course Notes - PingFederate 5

## Data Stores

* System -&gt; External systems -&gt; Data Stores under the External systems category.

PingFed "Data Stores" represent systems outside of PingFed where user objects, attributes and other data are stored.

When an external data store is defined, you can configure PingFed to retrieve user attributes from data stores for contract fulfillment and token authorization for various use-cases.

Note: All Data Stores are tested on a scheduled basis. You can modify this interval in seconds in the Data Stores Screen. `Data-Store Validation Interval (Secs)` defaults to 300 seconds or 5 minutes.

Two types \(Database JDBC or Directory LDAP\)

JDBC or Java Database Connectivity is a framework to allow Java Apps access to external databases.

{% hint style="info" %}
Note: JDBC drivers are installed in the &lt;PingFed/server/default/lib&gt; folder. PingFed must be restarted after adding new drivers.
{% endhint %}

### Adding a LDAP Data Store \(Using a generic LDAP server\)

* Click `Add New Data Store` in the Data Stores screen
* **Data Store Type:** Add Name \("Internal LDAP Server"\) and Select type \(Directory LDAP\)
* **LDAP Configuration:** Hostnames, use LDAPS, Use DNS SRV Record, LDAP Type \(Active Directory, Generic, Oracle Directory Server or PingDirectory\), Bind anonymously, User DN _Distinguished name_ and Password.
* Click next and PingFed will validate the details.
* View the summary and click Save to commit these changes.

### Adding a JDBC Data Store \(MySQL\)

PingFed requires the JDBC driver to be installed for the DB you wish to use. These vendor specific drivers are generally provided by the database vendor.

* Click `Add New Data Store` in the Data Stores screen
* **Data Store Type:** Add Name \("User DB"\) and Select type \(Database JDBC\)
* **Database Config**: JDBC URL \(_jdbc:mysql://localhost/userinfo_\), Driver Class \(_com.mysql.jdbc.Driver_\), username, password, validated connection sql field is optional.
* Allow Multi-Value SQL is enabled by default.
* Click next and PingFed will validate the details.
* View the summary and click Save to commit these changes.

### Advanced LDAP Options

* **Test connection on borrow**: Validate objects before borrowing by the pool. Not enabled by default.
* **Test connection on return:** Validate object before returning to the pool. Not enabled by default.
* **Create new connections if necessary**: Create temp connections if maximum connections is reached. Enabled by default.
* **Verify LDAPS hostname**: Vertify the LDAP certificate. Enabled by default.
* **Minimum connection**s: connections per pool \(bind pool/search pool\). A value of 1 opens 1 connection in both pools.  _Note: For optimal performance, Use 50% of the maxthreads value in the Jetty config -_ `Jetty.threadPool.maxThreads`
* **Maximum connections**: Largest number of connections per tool. Equal or larger than the Minimum connections value.  _Note: For optional performance, use 75-100% of the maxthreads value in the Jetty config -_ `Jetty.threadPool.maxThreads`
* **Maximum Wait \(milliseconds\)**: Maximum time the pools will wait for a connection to become avaiable. `-1` will cause the pool to make a new connection instead of using an existing connection or error if not available.
* **Time between evictions \(milliseconds\)**: time between the evictor cleaning connections. `-1` will disable the evictions. Defaults to 60000
* **Read Timeout \(milliseconds\)**: Time to wait for a response before returning an error. `-1` will make the wait forever. Defaults to 3000
* **Connection Timeout \(milliseconds\)**: Time for a connection attempt before returning an error. `-1` will make the pool wait forever. Defaults to 3000
* **DNS TTL \(milliseconds\)**: Time to cache the DNS SRV record. On TTL, PingFed will retrieve a refreshed DNS SRV record.
* **LDAP DNS SRV RECORD PREFIX**: . Default to `_ldap._tcp`
* **LDAPS DNS SRV RECORD PREFIX**: . Default to `_ldaps._tcp`

### Advanced JDBC Options

* **Minimum Pool Size**: Smallest number of connections in the pool for this Data store.  _Note: If the service is new or unused, the actual connections might be lower than the minimum until they are established._
* **Maximum Pool Size**: larger number of connections in the pool for this Data store.
* **Blocking timeout \(Milliseconds\)**: Time to wait for a connection from the connection pool before it fails and returns an error.
* **Idle Timeout \(milliseconds\)**: Time to wait before the connection is idle before it is closed. Once the pool is established, the minimum pool size is applied.

## Attribute Mapping

Attribute mapping is used to associate properties about the specific user with their current login session.  
  
Attributes can be sent to a SP partner as part of an SSO transaction, or used to create an authentication or identity token via the OAuth Authorization server.

### Attribute Contracts

Attribute Contacts define what attribute are expected by the ??Login event?? using PingFed and what context.  
Attribute Contracts apply to adapters, connections, and during OAuth/OpenID connection token mapping.  
Attribute Contracts are fulfilled using attributes entered by the user at login \(username, domain, etc\) or by lookups to external data sources.

### Connection Mapping

Adapters such as the HTML form adapter has common attributes like "username"

The connection might require SAML\_SUBJECT and Email... username can be mapped to SAML\_SUBJECT, but the Email requirement might be mapped from one of the data store using connection attribute mapping.

![](../../../.gitbook/assets/image%20%282%29.png)

Multiple connections might use a single adapter, but have common attributes shared on them such as email - if the additional user data such as email is stored in a data store. You should be able to retrieve the email using the username attribute from the adapter to pass onto those connections.

![](../../../.gitbook/assets/image%20%283%29.png)

## Attribute Mapping Screens

The Attribute Mapping screens share a common design. The same layout can be expected on SP Connections/IdP Connections/Access Token Management screens.

![](../../../.gitbook/assets/image%20%286%29.png)

Attribute Contracts have four parts - the name such as `SAML_SUBJECT`. The source and the value. such as "adapter `SAML_SUBJECT` addribute source being an adapters username value". 

![](../../../.gitbook/assets/image%20%284%29.png)

## Core vs Extended Contract Attributes

`Core Contract` are values which are always provided/present even if they're not used

`Extend the Contract` are additional attributes added manually and can be added/removed on demand.

**Example**: The HTML Form Adapter contract includes two core attributes: username and policy.action

![](../../../.gitbook/assets/image%20%285%29.png)

DOCS: [https://docs.pingidentity.com/bundle/pingfederate-93/page/dri1564003022949.html](https://docs.pingidentity.com/bundle/pingfederate-93/page/dri1564003022949.html)







