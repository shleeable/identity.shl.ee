# Course Notes - PingFederate 3

## Startup Files

PingFed startup is controlled by the `run.properties` and the `run.sh/run.bat` files located in the &lt;pingfed&gt;/bin directory.

Changes to the startup files will require a restart to take effect

## run.properties file

Controls the admin console and runtime behaviour of PingFed

* **pf.console.bind.address**: bind to one or multiple NICs
* **pf.admin.https.port**: admin console port. default 9999
* **pf.console.title**: unique name on the console. 
* **pf.console.session.timeout**: inactive timeout. 1m min. 480max. 30 default.
* **pf.console.authentication**: indicates admins login using creds managed locally or externally
* **pf.console.login.mode**: Single or Multiple
* **pf.log.eventdetail**: detailed event logging of console actions. default is disabled.
* **pg.admin.api.authentication**:  Defines authentication method by admin API
* **ldap.properties.file**: If LDAP is enabled, path to config file.
* **cert.properties.file:** ?
* **radius.properties.file**: ? 
* pf.https.port
* pf.http.port
* * 










