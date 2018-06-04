---
title: Resource Type Control Codes
description: Resource type control code usage in the Failover Cluster API.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: a854829d-ed05-40a0-b7c8-c3e5ab888220
ms.prod: windows-server-dev
ms.technology: failover-clustering
ms.tgt_platform: multiple
keywords:
- resource type control codes Failover Cluster
- control codes Failover Cluster ,resource type
- resource types Failover Cluster ,control codes
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# Resource Type Control Codes

[Resource type](resource-types.md) [control codes](about-control-codes.md) are used in the following ways.

-   Applications use [external control codes](external-control-codes.md) as [**ClusterResourceTypeControl**](/previous-versions/windows/desktop/api/ClusAPI/nf-clusapi-clusterresourcetypecontrol) parameters to initiate operations on a resource type.
-   The [Cluster service](cluster-service.md) uses [internal](internal-control-codes.md) resource type control codes to notify [resource DLLs](resource-dlls.md) of changes to the [*cluster*](https://www.bing.com/search?q=*cluster*) environment.
-   Resource DLLs receive internal and external resource type control codes as parameters to the [**ResourceTypeControl**](/previous-versions/windows/desktop/api/ResApi/nc-resapi-presource_type_control_routine) entry point function. A resource DLL may implement special procedures in response to a control code, depending on the control code and the needs of the resource type it manages. For more information, see [Implementing ResourceTypeControl](implementing-resourcetypecontrol.md).

For more information, refer to the following topics:

-   [External Resource Type Control Codes](external-resource-type-control-codes.md)
-   [Internal Resource Type Control Codes](internal-resource-type-control-codes.md)

Resource type control codes use the **CLUS\_OBJECT\_RESOURCE\_TYPE** value of the [**CLUSTER\_CONTROL\_OBJECT**](/previous-versions/windows/desktop/api/ClusAPI/ne-clusapi-cluster_control_object) enumeration to indicate that the control code applies to cluster resource types. For more information about control codes, see [Control Code Architecture](control-code-architecture.md).

Resource type control codes are enumerated by the [**CLUSCTL\_RESOURCE\_TYPE\_CODES**](/previous-versions/windows/desktop/api/ClusAPI/ne-clusapi-clusctl_resource_type_codes) enumeration.

## Related topics

<dl> <dt>

[Failover Cluster Control Codes](control-codes.md)
</dt> <dt>

[**ClusterResourceTypeControl**](/previous-versions/windows/desktop/api/ClusAPI/nf-clusapi-clusterresourcetypecontrol)
</dt> </dl>

 

 



