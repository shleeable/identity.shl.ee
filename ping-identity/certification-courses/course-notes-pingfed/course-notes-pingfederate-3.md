# Course Notes - PingFederate 3

## Startup Files

PingFed startup is controlled by the `run.properties` and the `run.sh/run.bat` files located in the `<pingfed>/bin` directory.

Changes to the startup files will require a restart to take effect

## run.properties file

Controls the admin console and runtime behavior of PingFed

* **pf.console.bind.address**: bind console to one or multiple NICs
* **pf.admin.https.port**: admin console port. default 9999
* **pf.console.title**: unique name on the console. 
* **pf.console.session.timeout**: inactive timeout. 1m min. 480max. 30 default.
* **pf.console.authentication**: indicates admins login using creds managed locally or externally
* **pf.console.login.mode**: "Single" or "Multiple"
* **pf.log.eventdetail**: detailed event logging of console actions. default is disabled.
* **pg.admin.api.authentication**:  Defines authentication method by admin API
* **ldap.properties.file**: If LDAP is enabled, path to config file.
* **cert.properties.file:** ?
* **radius.properties.file**: ? 
* **pf.https.port**: PingFed runtime engine port for HTTPS traffic. default is `9031`
* **pf.http.port**: Disabled by default. Runtime port for unencrypted HTTP traffic. Do not use.
* **pf.secondary.https.port**: used for Mutual TLS auth for clients and protocol requests \(SAML, WS-Trust, OAuth\)
* **pf.engine.bind.address:** bind runtime engine to one or multiple NICs
* **pf.monitor.bind.address:** Bind SNMP/JMX agent to one or multiple NICs
* **pf.engine.prefer\_ipv4**: Defaults to true to enable IPv4 ONLY. Disabling enables IPv4 and IPv6.
* **http.proxyHost / http.proxyPort**: proxy for PingFed server to send outbound HTTP traffic.
* **https.proxyHost / https.proxyPort**: proxy for PingFed server to send outbound HTTPS traffic.
* **http.nonProxyHosts:** specifies hosts to bypass the proxy 
* **pf.runtime.context.path**: Allows custom server paths for PingFed endpoints.
* **pf.log.dir**: path to log folder. Default to `<pingfed/pingfederate/log>`
* **pf.hsm.mode**: Toggles a FIPs-compliance HSM \(hardware Security Module\). When enabled, secure key material is stored on the HSM and not on the PingFed instance.
* **pf.hsm.hybrid**: Toggles the optional ability for secure key materials \(keys, certs\) to be stored locally and transfered to the HSM later.
* **pf.provisioner.mode**: Toggles outbound provisioning. Default is disabled.
* **pf.heartbeat.system.monitoring**: Toggles the PingFed heartbeat endpoint `/pf/heartbeat.ping` which returns detailed system information used for monitoring. \(customizable Velocity template file\)
* **org.apache.xml.security.ignoreLineBreaks:** Defaults to true. PingFed does not insert line breaks in XML digital signatures.

## run.bat / run.sh

running these commands will start the PingFed server. Ctrl+C to stop the PingFed server cleanly.

Windows Server service files can be installed or uninstalled from &lt;PingFed\sbin\win-x86-64&gt; directory  
Linux daemon files can be found in the &lt;PingFed\sbin\linux&gt;

## Java Properties

JVM and garbage collection options can be modified from the &lt;PingFed/bin/jvm-memory.options&gt; file.  
PingFed must be restarted to applied any chances to the file.















