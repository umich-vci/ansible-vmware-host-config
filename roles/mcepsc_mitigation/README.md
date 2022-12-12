mcepsc_mitigation
=========

Configure a host for mitigation against the MCEPSC CPU vulnerability as documented in [VMware KB 59139](https://kb.vmware.com/s/article/59139).

Requirements
------------

pyvmomi is required. This role assumes your inventory file contains each ESXi host you are managing.

Role Variables
--------------

### Defaults

- `mcepsc_mitigation_enabled` - The default value is `true`.

### Required

- `vmware_host` - The hostname or address of the vCenter server.

- `inventory_hostname` - The hostname or address of the ESXi server.
