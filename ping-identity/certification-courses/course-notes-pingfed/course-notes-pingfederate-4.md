# Course Notes - PingFederate 4

## PingFed Server Endpoints

{% hint style="info" %}
Notes: "Endpoints provide a methods for outside parties to retrieve information about PingFed without using the admin console or admin API"
{% endhint %}

Endpoints are HTTP requests .

### System Services Endpoints

PingFed has five System-Services Endpoints. These are globally available depending on the server roles used \(IdP, SP or both etc\)

* **/pf/heartbeat.ping**: Returns status 200 and body "OK" if the server is functional. Recommended to use with load balances to determine service help.
* **/pf/adapter2adapter.ping**: Initiates direct IdP to SP adapter mapping when the feature is configured. DOCO: [https://documentation.pingidentity.com/pingfederate/pf92/index.shtml\#adminGuide/adapterToAdapterMapping.html](https://documentation.pingidentity.com/pingfederate/pf92/index.shtml#adminGuide/adapterToAdapterMapping.html)
* **/pf/sts.wst**: Initiates direct STS \(Security Token Service\) token-to-token exchange and token validation from an IdP token processor to an P token generator when it is enabled. _Example: Kerberos Token -&gt; ENDPOINT -&gt; 3rd party token_ DOCO: [https://documentation.pingidentity.com/pingfederate/pf92/index.shtml\#adminGuide/tokenExchangeMapping\_idpToSpBridging.html](https://documentation.pingidentity.com/pingfederate/pf92/index.shtml#adminGuide/tokenExchangeMapping_idpToSpBridging.html)
* **/pf/sts\_mex.ping**: \(STS Metadata Exchange\) returns STS metadata used for configuring web-service applications. _Example: this endpoint accepts the partner SP ID and IdP IDs as parameters._
* **/pf/federation\_metadata.ping**: returns SAML and WS-Federation metadata. _Example: This pointless accepts the partner SP ID and IdP IDs as parameters._

### Protocol Endpoints

Protocol Endpoints affect specific protocols \(or PingFed Roles\) on your instance.

The IdP, SP, or OAUTH Authorization Server Roles \(including the OpenID Connect\) have their own endpoints depending on the protocols options selected.

**Protocol endpoints will be covered later in detail with each protocol .**

### Extra: Heartbeat

Edit the `/pingfederate/server/default/conf/template/heartbeat.page.template` Velocity template file to specify the desired information to be returned by the heartbeat endpoint. \(An inline sample is provided. Template customization does not require a restart of PingFederate.\)

## Certificate Management

PingFed provides built-in cert management to handle SSL/TLS server security, as well as certificate signing and verification for SSO and other transactions. PingFed uses certs for multiple purposes.

### Certificate and Key Management in the admin console

* **Trusted CAs:** Import your partners root CA certs. This can be used for domains, LDAPS or other services using the CA.  _Note: It is not required to add any CA that is trusted by the java runtime truststore._
* **SSL Server Certificates:**  _Note: "Manages access to the PingFed Admin Console, or incoming HTTP connections at runtime?"_
* **SSL Client Keys & Certificates:** Used to identify the PingFed Server when it acting as a client in an outbound SSL/TLS transaction.
* **Signing & Decryption Keys & Certificates:** Used to sign outbound requests/responses/assertions/Access tokens. The same type of certificate is used for decryption. Note: PingFed recommends using separate certificates for signing, and decryption.
* **OAuth & OpenID Connect Keys:** Specifies if PingFed should use static or dynamic rotating keys for OAuth and OpenID Connect. These keys are used to sign ID Tokens, JWTs for client authentication and OpenID Connect request objects.
* **Certificate Revocation Checking:** ?

### SSL/TLS

SSL/TLS is the standard for establishing encrypted links between web services \(such as the browser and the web server over HTTPS\)

The encryption is handled using certificates, and certificates are used to validate ownership of a FQDN using PKI \(Public key infrastructure\).

### PingFed default \(selfsigned\) Certificates

On installation, PingFed will generate some selfsigned certs for localhost that need to be replaced for the admin console and the Runtime Engine.

These default certs can be changed at any time in the admin console. Clicking **SSL Server Certificates** and clicking Create New or Import.



\*\*\*\*

