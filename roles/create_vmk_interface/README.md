create_vmk_interface
=========

It is not possible to create a VMKernel interface directly on a DVswitch with Ansible presently.
This role will create one on a temporary standard vSwitch and move it to the specified DVswitch.

Requirements
------------

pyvmomi is required. This role assumes your inventory file contains each ESXi host you are managing.

Role Variables
--------------

### Defaults

- `enable_ft` - no

- `enable_mgmt` - no

- `enable_vmotion` - no

- `enable_vsan` - no

- `mtu` - 1500

- `vlan_id` - null

### Required

- `interface` - The vmk interface we are creating (i.e. vmk1).  Note that this is only checked
  for existance, it is not specified as part of the creation. Interface numbers are assigned
  sequentially so use this with that in mind.

- `ip_address` - The IP address you are assigning to the interface. This role assumes you are
  using a static address.

- `subnet_mask` - The IP address you are assigning to the interface. This role assumes you are
  using a static address.

- `dvs_portgroup` - The target DVswitch portgroup you would like the interface to be on.

- `dvswitch` - The target DVswitch that the previously mentioned `dvs_portgroup` is on.

- `vmware_host` - The hostname or address of the vCenter server.

- `inventory_hostname` - The hostname or address of the ESXi server.
