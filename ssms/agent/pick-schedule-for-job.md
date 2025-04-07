---
title: "Pick Schedule for Job"
description: "Pick Schedule for Job"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.ag.job.pickscheduleforjob.f1"
helpviewer_keywords:
  - "Pick Schedule for Job dialog box"
---
# Pick Schedule for Job
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> On [Azure SQL Managed Instance](/azure/sql-database/sql-database-managed-instance), most, but not all SQL Server Agent features are currently supported. See [Azure SQL Managed Instance differences from SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) for details.

Use this dialog to pick an existing schedule for the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job.  
  
## Options  
**Available schedules**  
Lists the schedules available for this job. Because a job and a schedule must have the same owner, this list only includes schedules owned by the owner of the job.  
  
**Name**  
Displays the name of the schedule.  
  
**Enabled**  
Selected if the schedule is enabled.  
  
**Description**  
Describes the conditions under which the schedule runs the job.  
  
**Jobs in schedule**  
Lists the job numbers attached to the schedule. Click a number to view the properties of the job.  
  
**Properties**  
Launches the **Job Schedule Properties** dialog where you can view information about the schedule.  
  
## See Also  
[Create and Attach Schedules to Jobs](create-and-attach-schedules-to-jobs.md)  
