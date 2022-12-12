configure_syslog
=========

Configure syslog on an ESXi host

Requirements
------------

pyvmomi is required. This role assumes your inventory file contains each ESXi host you are managing.
Syslog filters from a template cannot be configured on ESXi 6.0 due to the filecmp python module missing.

Role Variables
--------------

### Defaults

- `configure_remote_syslog` - Defaults to no.  If set to yes, will configure a host to send syslogs to a remote host.  Requires a variable named `syslog_servers` if yes.

- `configure_syslog_filters` - Defaults to no.  If set to yes, will configure a host to filter certain syslog messages from a template named logfilters.j2.

### Required

- `vmware_host` - The hostname or address of the vCenter server.

- `inventory_hostname` - The hostname or address of the ESXi server.
