---
title: CLUSCTL\_CLUSTER\_GET\_RO\_PRIVATE\_PROPERTIES control code
description: Retrieves the read-only private properties for a cluster.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: a51019bc-f412-4c91-8e6d-b32200c2e39c
ms.prod: windows-server-dev
ms.technology: failover-clustering
ms.tgt_platform: multiple
keywords:
- CLUSCTL_CLUSTER_GET_RO_PRIVATE_PROPERTIES control code Failover Cluster
topic_type:
- apiref
api_name:
- CLUSCTL_CLUSTER_GET_RO_PRIVATE_PROPERTIES
api_location:
- ClusAPI.h
api_type:
- HeaderDef
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# CLUSCTL\_CLUSTER\_GET\_RO\_PRIVATE\_PROPERTIES control code

Retrieves the read-only private properties for a cluster. Applications use this [control code](about-control-codes.md) as a [**ClusterControl**](/previous-versions/windows/desktop/api/ClusAPI/nf-clusapi-clustercontrol) parameter.


```C++
ClusterControl( 
  hCluster,                                   // cluster handle
  hHostNode,                                  // optional node handle
  CLUSCTL_CLUSTER_GET_RO_PRIVATE_PROPERTIES,  // this control code
  NULL,                                       // input buffer (not used)
  0,                                          // input buffer size (not used)
  lpOutBuffer,                                // output buffer: property list
  cbOutBufferSize,                            // output buffer size (bytes)
  lpcbBytesReturned                           // resulting data size (bytes)
);
```



## Parameters

The following control code function parameter is specific to this control code. For complete parameter descriptions, see [**ClusterControl**](/previous-versions/windows/desktop/api/ClusAPI/nf-clusapi-clustercontrol).

<dl> <dt>

*lpOutBuffer* 
</dt> <dd>

On a successful return, points to a [property list](property-lists.md) containing the specified cluster's read-only cluster [private properties](private-properties.md).

</dd> </dl>

## Return value

[**ClusterControl**](/previous-versions/windows/desktop/api/ClusAPI/nf-clusapi-clustercontrol) returns one of the following values.

<dl> <dt>

**ERROR\_SUCCESS**
</dt> <dd>

0

The operation completed successfully. The *lpcbBytesReturned* parameter points to the actual size of the returned data.

</dd> <dt>

**ERROR\_MORE\_DATA**
</dt> <dd>

234 (0xEA)

More data is available. The output buffer pointed to by *lpOutBuffer* was not large enough to hold the data resulting from the operation. The *lpcbBytesReturned* parameter points to the size required for the output buffer.

</dd> <dt>

**[System error code](https://msdn.microsoft.com/library/windows/desktop/ms681381)**
</dt> <dd>

If any other value is returned, then the operation failed. The value of *lpcbBytesReturned* is unreliable.

</dd> </dl>

## Remarks

For information on working with property lists, see [Using Property Lists](using-property-lists.md).

By default, failover clusters do not define any private cluster properties. ClusAPI.h defines the 32 bits of CLUSCTL\_CLUSTER\_GET\_RO\_PRIVATE\_PROPERTIES as follows (for more information, see [Control Code Architecture](control-code-architecture.md)).



| Component      | Bit location | Value                                          |
|----------------|--------------|------------------------------------------------|
| Object code    | 24 31        | **CLUS\_OBJECT\_CLUSTER** (0x7)                |
| Global bit     | 23           | **CLUS\_NOT\_GLOBAL** (0x0)                    |
| Modify bit     | 22           | **CLUS\_NO\_MODIFY** (0x0)                     |
| User bit       | 21           | **CLCTL\_CLUSTER\_BASE** (0x0)                 |
| Type bit       | 20           | External (0x0)                                 |
| Operation code | 0 23         | **CLCTL\_GET\_RO\_PRIVATE\_PROPERTIES** (0x7d) |
| Access code    | 0 1          | **CLUS\_ACCESS\_READ** (0x1)                   |



 

## Requirements



|                                     |                                                                                      |
|-------------------------------------|--------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                            |
| Minimum supported server<br/> | Windows Server 2008 Enterprise, Windows Server 2008 Datacenter<br/>            |
| Header<br/>                   | <dl> <dt>ClusAPI.h</dt> </dl> |



## See also

<dl> <dt>

[Cluster Control Codes](cluster-control-codes.md)
</dt> <dt>

[**ClusterControl**](/previous-versions/windows/desktop/api/ClusAPI/nf-clusapi-clustercontrol)
</dt> </dl>

 

 




