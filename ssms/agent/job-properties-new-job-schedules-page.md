---
title: "Job Properties - New Job (Schedules Page)"
description: "Job Properties - New Job (Schedules Page)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.ag.job.schedules.f1"
---
# Job Properties - New Job (Schedules Page)
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> On [Azure SQL Managed Instance](/azure/sql-database/sql-database-managed-instance), most, but not all SQL Server Agent features are currently supported. See [Azure SQL Managed Instance T-SQL differences from SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) for details.

Use this page to view and organize schedules for a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job.  
  
## Options  
**Schedule list**  
Lists the schedules for this job.  
  
**New**  
Create a new schedule. After you create the schedule, the schedule is added to the job.  
  
**Pick**  
Select a schedule from the existing schedules. Because a job and schedule must have the same owner, this option will only allow you to pick from schedules that you own.  
  
**Edit**  
Edit the selected schedule to change job schedule properties.  
  
**Remove**  
Remove the selected schedule from the job. If no other jobs use the schedule, the schedule is deleted from the database.  
  
## See Also  
[Implement Jobs](implement-jobs.md)  
