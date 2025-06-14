---
title: "Job Properties - New Job (General Page)"
description: "Job Properties - New Job (General Page)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.ag.job.general.f1"
---
# Job Properties - New Job (General Page)
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

Use this page to view and modify the general properties of a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job.  
  
## Options  
**Name**  
Change the name of the job.  
  
**Owner**  
Select the owner for the job.  
  
**Category**  
Select the job category for the job.  
  
**...**  
View the jobs in the selected category.  
  
**Description**  
Change the description of the job.  
  
**Enabled**  
Enable the job. When the job is not enabled, the job does not run in response to a schedule or an alert, although you can still start the job using the **sp_start_job** stored procedure.  
  
**Source**  
Displays the master server for the job. Only available on the **Job PropertiesGeneral** page.  
  
**Created**  
Displays the date and time that the job was created. Only available on the **Job PropertiesGeneral** page.  
  
**Last modified**  
Displays the date and time that the job was last modified. Only available on the **Job PropertiesGeneral** page.  
  
**Last executed**  
Displays the date and time that the job last started running. Only available on the **Job PropertiesGeneral** page.  
  
**View Job History**  
View the job history for the job. Only available on the **Job PropertiesGeneral** page.  
  
## See Also  
[Implement Jobs](implement-jobs.md)  
[Job Categories - Manage Job Categories](job-categories-manage-job-categories.md)  
