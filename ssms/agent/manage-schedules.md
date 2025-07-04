---
title: "Manage Schedules"
description: "Manage Schedules"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.ag.job.manageschedules.f1"
---
# Manage Schedules
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

Allows you to view and change properties for [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job schedules.  
  
## Options  
**Available schedules**  
Lists the schedules available for this user. Notice that a job and a schedule must have the same owner. Therefore, this list only includes schedules owned by the owner of the job.  
  
**Name**  
Displays the name of the schedule.  
  
**Enabled**  
Select this option to enable the schedule.  
  
**Description**  
Describes the conditions under which the schedule runs the job.  
  
**Jobs in schedule**  
Lists the job numbers attached to the schedule. Click a number to view the properties of the job.  
  
**New**  
Click this button to create a new schedule.  
  
**Delete**  
Click this button to delete the selected schedule.  
  
**Properties**  
Click this button to change the properties of the selected schedule.  
  
## See Also  
[Create and Attach Schedules to Jobs](create-and-attach-schedules-to-jobs.md)  
