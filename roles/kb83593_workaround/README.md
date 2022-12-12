vmware_kb83593_workaround
=========

This role configures a host for the workaround described in [VMware KB 83593](https://kb.vmware.com/s/article/83593)
and [HPE Advisory a00117965](https://support.hpe.com/hpesc/public/docDisplay?docId=emr_na-a00117965en_us).

If the workaround needs to be applied, the host will be put into maintenance mode and rebooted.

Requirements
------------

pyvmomi is required. This role assumes your inventory file contains each ESXi host you are managing.

Role Variables
--------------

### Required

- `vmware_host` - The hostname or address of the vCenter server.

- `inventory_hostname` - The hostname or address of the ESXi server.
