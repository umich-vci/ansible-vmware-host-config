netapp_best_practices
=========

This role configures an ESXi host for the best practices when using NetApp storage.  The settings are
from the [NetApp documentation](https://www.netapp.com/us/media/tr-4597.pdf).  Additional info is also
available in [VMware KB 2016122](https://kb.vmware.com/s/article/2016122).

Requirements
------------

pyvmomi is required. This role assumes your inventory file contains each ESXi host you are managing.

Role Variables
--------------

### Required

- `vmware_host` - The hostname or address of the vCenter server.

- `inventory_hostname` - The hostname or address of the ESXi server.
