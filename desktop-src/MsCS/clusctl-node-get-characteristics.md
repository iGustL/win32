---
title: CLUSCTL\_NODE\_GET\_CHARACTERISTICS control code
description: Retrieves the intrinsic characteristics of a node.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 8979b006-5494-4587-9675-983ee9021273
ms.prod: windows-server-dev
ms.technology: failover-clustering
ms.tgt_platform: multiple
keywords:
- CLUSCTL_NODE_GET_CHARACTERISTICS control code Failover Cluster
topic_type:
- apiref
api_name:
- CLUSCTL_NODE_GET_CHARACTERISTICS
api_location:
- ClusAPI.h
api_type:
- HeaderDef
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# CLUSCTL\_NODE\_GET\_CHARACTERISTICS control code

Retrieves the intrinsic characteristics of a [node](nodes.md). Applications use this [control code](about-control-codes.md) as a [**ClusterNodeControl**](/previous-versions/windows/desktop/api/ClusAPI/nf-clusapi-clusternodecontrol) parameter.


```C++
ClusterNodeControl( 
  hNode,                            // node handle
  hHostNode,                        // optional host node
  CLUSCTL_NODE_GET_CHARACTERISTICS, // this control code
  NULL,                             // input buffer (not used)
  0,                                // input buffer size (not used)
  lpOutBuffer,                      // output buffer: DWORD bitmask
  cbOutBufferSize,                  // allocated buffer size (bytes)
  lpcbBytesReturned );              // actual size of resulting data (bytes)
```



## Parameters

The following control code function parameter is specific to this control code. For complete parameter descriptions, see [**ClusterNodeControl**](/previous-versions/windows/desktop/api/ClusAPI/nf-clusapi-clusternodecontrol).

<dl> <dt>

*lpOutBuffer* 
</dt> <dd>

On a successful return, contains a **DWORD** bitmask describing the node's characteristics enumerated from the [**CLUS\_CHARACTERISTICS**](/previous-versions/windows/desktop/api/ClusAPI/ne-clusapi-clus_characteristics) enumeration. Only one bitmask is currently defined.

<dt>

<span id="CLUS_CHAR_UNKNOWN"></span><span id="clus_char_unknown"></span>

<span id="CLUS_CHAR_UNKNOWN"></span><span id="clus_char_unknown"></span>**CLUS\_CHAR\_UNKNOWN** (0x00000000)


</dt> <dd>

The Network Interface has no known characteristics.

</dd> <dt>

<span id="CLUS_CHAR_DELETE_REQUIRES_ALL_NODES"></span><span id="clus_char_delete_requires_all_nodes"></span>

<span id="CLUS_CHAR_DELETE_REQUIRES_ALL_NODES"></span><span id="clus_char_delete_requires_all_nodes"></span>**CLUS\_CHAR\_DELETE\_REQUIRES\_ALL\_NODES** (0x00000002)


</dt> <dd>

Resources of this type cannot be deleted unless all nodes are active.

</dd> <dt>

<span id="CLUS_CHAR_REQUIRES_STATE_CHANGE_REASON"></span><span id="clus_char_requires_state_change_reason"></span>

<span id="CLUS_CHAR_REQUIRES_STATE_CHANGE_REASON"></span><span id="clus_char_requires_state_change_reason"></span>**CLUS\_CHAR\_REQUIRES\_STATE\_CHANGE\_REASON** (0x00000010)


</dt> <dd>

The [resource DLL](resource-dlls.md) will receive the [CLUSCTL\_RESOURCE\_STATE\_CHANGE\_REASON](clusctl-resource-state-change-reason.md) control code.

</dd> <dt>

<span id="CLUS_CHAR_SINGLE_CLUSTER_INSTANCE"></span><span id="clus_char_single_cluster_instance"></span>

<span id="CLUS_CHAR_SINGLE_CLUSTER_INSTANCE"></span><span id="clus_char_single_cluster_instance"></span>**CLUS\_CHAR\_SINGLE\_CLUSTER\_INSTANCE** (0x00000040)


</dt> <dd>

Only one instance of this resource type is allowed in a cluster.

</dd> <dt>

<span id="CLUS_CHAR_SINGLE_GROUP_INSTANCE"></span><span id="clus_char_single_group_instance"></span>

<span id="CLUS_CHAR_SINGLE_GROUP_INSTANCE"></span><span id="clus_char_single_group_instance"></span>**CLUS\_CHAR\_SINGLE\_GROUP\_INSTANCE** (0x00000080)


</dt> <dd>

Only one instance of this resource type is allowed in a group.

</dd> </dl> </dd> </dl>

## Return value

[**ClusterNodeControl**](/previous-versions/windows/desktop/api/ClusAPI/nf-clusapi-clusternodecontrol) returns one of the following values.

<dl> <dt>

**ERROR\_SUCCESS**
</dt> <dd>

The operation completed successfully. This value is returned if the *lpcbBytesReturned* parameter points to the actual size of the returned data.

</dd> <dt>

**ERROR\_MORE\_DATA**
</dt> <dd>

More data is available. This value is returned if the output buffer pointed to by *lpOutBuffer* was not large enough to hold the data resulting from the operation. The *lpcbBytesReturned* parameter points to the size required for the output buffer.

</dd> <dt>

**[System error code](https://msdn.microsoft.com/library/windows/desktop/ms681381)**
</dt> <dd>

If any other value is returned, the operation failed. The value of *lpcbBytesReturned* is unreliable.

</dd> </dl>

## Remarks

ClusAPI.h defines the 32 bits of CLUSCTL\_NODE\_GET\_CHARACTERISTICS as follows (for more information, see [Control Code Architecture](control-code-architecture.md)).



| Component      | Bit location | Value                                            |
|----------------|--------------|--------------------------------------------------|
| Object code    | 24 31        | **CLUS\_OBJECT\_NODE** (0x4)<br/>          |
| Global bit     | 23           | **CLUS\_NOT\_GLOBAL** (0x0)<br/>           |
| Modify bit     | 22           | **CLUS\_NO\_MODIFY** (0x0)<br/>            |
| User bit       | 21           | **CLCTL\_CLUSTER\_BASE** (0x0)<br/>        |
| Type bit       | 20           | External (0x0)<br/>                        |
| Operation code | 0 23         | **CLCTL\_GET\_CHARACTERISTICS** (0x5)<br/> |
| Access code    | 0 1          | **CLUS\_ACCESS\_READ** (0x1)<br/>          |



 

## Requirements



|                                     |                                                                                      |
|-------------------------------------|--------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                            |
| Minimum supported server<br/> | Windows Server 2008 Enterprise, Windows Server 2008 Datacenter<br/>            |
| Header<br/>                   | <dl> <dt>ClusAPI.h</dt> </dl> |



## See also

<dl> <dt>

[Node Control Codes](node-control-codes.md)
</dt> <dt>

[**ClusterNodeControl**](/previous-versions/windows/desktop/api/ClusAPI/nf-clusapi-clusternodecontrol)
</dt> <dt>

[**CLUS\_CHARACTERISTICS**](/previous-versions/windows/desktop/api/ClusAPI/ne-clusapi-clus_characteristics)
</dt> </dl>

 

 




