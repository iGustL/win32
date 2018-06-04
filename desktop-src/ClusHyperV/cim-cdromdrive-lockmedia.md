---
title: LockMedia method of the CIM\_CDROMDrive class
description: Represents a device that can use media to store and retrieve data.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 6fbf0a53-f10c-449c-88b3-d47642dca33d
ms.prod: windows-server-dev
ms.technology:
- failover-cluster-hyperv
- windows-management-instrumentation
ms.tgt_platform: multiple
keywords:
- LockMedia method
- LockMedia method, CIM_CDROMDrive class
- CIM_CDROMDrive class, LockMedia method
topic_type:
- apiref
api_name:
- CIM_CDROMDrive.LockMedia
api_location:
- VMMS.exe
api_type:
- COM
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# LockMedia method of the CIM\_CDROMDrive class

Represents a device that can use media to store and retrieve data.

## Syntax


```mof
uint32 LockMedia(
  [in] boolean Lock
);
```



## Parameters

<dl> <dt>

*Lock* \[in\]
</dt> <dd>

**true** to lock the media, or **false** to unlock the media.

</dd> </dl>

## Return value

This method returns "0" if successful, "1" if not supported, and any other value if an error occurred.

## Requirements



|                                     |                                                                                                        |
|-------------------------------------|--------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                                              |
| Minimum supported server<br/> | Windows Server 2016<br/>                                                                         |
| Namespace<br/>                | Root\\HyperVCluster\\v2<br/>                                                                     |
| MOF<br/>                      | <dl> <dt>WindowsHyperVCluster.V2.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>VMMS.exe</dt> </dl>                    |



## See also

<dl> <dt>

[**CIM\_CDROMDrive**](cim-cdromdrive.md)
</dt> </dl>

 

 




