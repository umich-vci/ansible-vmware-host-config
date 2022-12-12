configure_active_directory
=========

Configure an ESXi host to be a member of the specified Active Directory Domain.

Requirements
------------

pyvmomi is required. This role assumes your inventory file contains each ESXi host you are managing.

Role Variables
--------------

### Defaults

- `esx_admins_group` - The AD group to treat as Admins of the ESXi host.  Defaults to `ESX Admins`.

### Required

- `winrm_ad_host` - A remote Windows host to use to create the Computer Object for the ESXi host.

- `ad_service_account_user` - A service account with access to winrm_ad_host with permission to create computer
  objects and join the ESXi host to Active Directory.

- `ad_service_account_password` - The password for `ad_service_account_user`

- `ad_domain` - The DNS name of the Active Directory domain you would like to join.

- `ad_ou` - The OU you would like the Computer Object created in.

- `vmware_host` - The hostname or address of the vCenter server.

- `inventory_hostname` - The hostname or address of the ESXi server.
