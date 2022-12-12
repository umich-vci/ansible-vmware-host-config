foreshadow_mitigation
=========

Configure a host for mitigation against the Foreshadow CPU vulnerability at the specified level.

Requirements
------------

pyvmomi is required. This role assumes your inventory file contains each ESXi host you are managing.

Role Variables
--------------

### Defaults

- `scheduler` - The default value is `SCAv1`.  Other options are `unmitigated` or `SCAv2`. Note that if you specify
  a mitigation level that cannot be applied to a host, it will be skipped.  If you specify `SCAv2` for a host that
  only supports `SCAv1` only `SCAv1` mitigations will be applied.

### Required

- `vmware_host` - The hostname or address of the vCenter server.

- `inventory_hostname` - The hostname or address of the ESXi server.
