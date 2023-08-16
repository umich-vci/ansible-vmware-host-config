pure_storage_best_practices
=========

This role configures an ESXi host for the best practices when using Pure storage.  The settings are
from the [Best practices guide](https://support.purestorage.com/Solutions/VMware_Platform_Guide/001VMwareBestPractices/dddVMware_ESXi_Host_Configuration) and
[VAAI Guide](https://support.purestorage.com/Solutions/VMware_Platform_Guide/001VMwareBestPractices/Web_Guide%3A_VMware_Storage_APIs_for_Array_Integration_with_the_Pure_Storage%C2%AE_FlashArray).
Additional info is also available in [VMware KB 2146167](https://kb.vmware.com/s/article/2146167).

Requirements
------------

pyvmomi is required. This role assumes your inventory file contains each ESXi host you are managing.

Role Variables
--------------

### Defaults

- `Third_Party_Array_Not_Support_ATS_HB` - If a third party array also used in the environment
  has issues using ATS heartbeats, it is ok to disable this functionality. The default value is `false`.

- `Third_Party_Array_Not_Support_Max_HW_Transfer_Size` - If a third party array also used in the environment
  has issues increasing the maximum size of VAAI XCOPY operations, it is ok to leave MaxHWTransferSize
  at the default. The default value is `false`.

- `MaxHWTransferSize` - By default this is set to `4096`, but for best performance on Pure storage it should
  be set to `16384`.  It will automatically be calculated based on the value of
  `Third_Party_Array_Not_Support_Max_HW_Transfer_Size`.  You might want to override it if you have another
  array in the environment that supports operations larger than the default but smaller than Pure's recomendation.

- `DisableSmartd` - There appears to be an issue where
  [vSphere tries to read SMART data from Pure volumes](https://www.jacobhopkinson.com/2019/08/09/vmware-and-scsi-why-do-my-pure-storage-datastores-report-scsi-0x85-errors-every-30-minutes/)
  , but those obviously don't support SMART.  If you don't have any local storage, it should be safe
  to disable SMART. Defaults to `false`.

### Required

- `vmware_host` - The hostname or address of the vCenter server.

- `inventory_hostname` - The hostname or address of the ESXi server.
