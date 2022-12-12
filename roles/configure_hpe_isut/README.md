configure_hpe_isut
=========

Configure iSUT on an HPE Gen10 host running vSphere

Requirements
------------

pyvmomi is required. This role assumes your inventory file contains each ESXi host you are managing.

Role Variables
--------------

### Defaults

- `isut_mode` - The default value is `AutoDeploy`. Valid options are `AutoDeploy`, `AutoDeployReboot`, `AutoStage`, and `OnDemand`.

### Required

- `vmware_host` - The hostname or address of the vCenter server.

- `inventory_hostname` - The hostname or address of the ESXi server.
