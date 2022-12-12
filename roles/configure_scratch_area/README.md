configure_scratch_area
=========

Configures the scratch area of an ESXi host

Requirements
------------

pyvmomi is required. This role assumes your inventory file contains each ESXi host you are managing.

Role Variables
--------------

### Default

- `shared_scratch_area` - Configure a scratch area that is shared by multiple hosts.  Defaults to yes

- `shared_scratch_directory` - The directory on the shared scratch datastore that should contain the scratch areas.
  Defaults to 'HostScratch'.

### Required

- `shared_scratch_area_datastore` - The shared datastore the scratch area should be configured on.  Required when
  `shared_scratch_area` is true.

- `local_scratch_datastore` - The local datastore the scratch area should be configured on.  Required when
  `shared_scratch_area` is false.

- `vmware_host` - The hostname or address of the vCenter server.

- `inventory_hostname` - The hostname or address of the ESXi server.
