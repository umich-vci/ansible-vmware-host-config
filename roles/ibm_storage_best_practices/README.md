ibm_storage_best_practices
=========

This role configures an ESXi host for the best practices when using IBM storage. For more info
see [IBM Alert S1005201](http://www-01.ibm.com/support/docview.wss?uid=ssg1S1005201),
[VMware KB 2113956](https://kb.vmware.com/s/article/2113956), and
[VMware KB 2008333](https://kb.vmware.com/s/article/2008333).

Requirements
------------

pyvmomi is required. This role assumes your inventory file contains each ESXi host you are managing.

Role Variables
--------------

### Required

- `vmware_host` - The hostname or address of the vCenter server.

- `inventory_hostname` - The hostname or address of the ESXi server.
