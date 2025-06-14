---
title: "Organize Jobs"
description: "Organize Jobs"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "job category"
  - "organize jobs"
---
# Organize Jobs
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

Job categories help you organize your jobs for easy filtering and grouping. For example, you can organize all your database backup jobs in the Database Maintenance category. You can also create your own job categories.  
  
> [!WARNING]  
> Multiserver categories exist only on a master server. There is only one default job category available on a master server: [**Uncategorized (Multi-Server)**]. When a multiserver job is downloaded, its category is changed to **Jobs From MSX** at the target server.  
  
## Related Tasks  
  
|Description|Topic|  
|-|-|  
|Describes how to create a job category.|[Create a Job Category](create-a-job-category.md)|  
|Describes how to delete a job category.|[Delete a Job Category](delete-a-job-category.md)|  
|Describes how to assign a job to a job category.|[Assign a Job to a Job Category](assign-a-job-to-a-job-category.md)|  
|Describes how to change the membership of a job category.|[Change the Membership of a Job Category](change-the-membership-of-a-job-category.md)|  
|Describes how to list the category information.|[List Job Category Information](list-job-category-information.md)|  
