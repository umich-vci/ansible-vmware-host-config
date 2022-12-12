VMSA_2019_0011_workaround
=========

This role implements a workaround for
[VMSA-2019-0011](https://www.vmware.com/in/security/advisories/VMSA-2019-0011.html) as described in
[VMware kb 67920](https://kb.vmware.com/s/article/67920).

Requirements
------------

pyvmomi is required. This role assumes your inventory file contains each ESXi host you are managing.

Role Variables
--------------

### Required

- `vmware_host` - The hostname or address of the vCenter server.

- `inventory_hostname` - The hostname or address of the ESXi server.
