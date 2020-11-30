# Course Notes - PingFederate 3

## PingFed Admin console - Wizards

The console "tasks" makes use of wizards in the console. Allowing admins to complete step by step. there is a summary at the end of the wizards before it is applied.

##  PingFed Admin console - Admin account management

PingFed supports Single-user administrator mode or multi-user administrator mode.

* Native authentication
* LDAP
* RADIUS
* x509 certs

## PingFed Admin console - Role based access control for Users

Local users for Pingred is managed using roles.

* Account Types \(Admin and Auditor\)
  * Admin has three different privileged roles
  * Auditor is a read only account for all admin functions
* Admin Roles \(Admin, Crypto Admin and User Admin\)
  * Admin role: Config partner connections. Can't modify local PingFed user accounts, or local keys and certs.
  * Crypto admin role: Config local keys and certs
  * User Admin role: Config local PingFed user accounts





