---
title: "Implement Jobs"
description: "Implement Jobs"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "jobs [SQL Server Agent]"
  - "SQL Server Agent jobs"
  - "SQL Server Agent jobs, about jobs"
  - "jobs [SQL Server Agent], about jobs"
---
# Implement Jobs
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

You can use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs to automate routine administrative tasks and run them on a recurring basis, making administration more efficient.  
  
A job is a specified series of operations performed sequentially by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent. A job can perform a wide range of activities, including running [!INCLUDE[tsql](../includes/tsql-md.md)] scripts, command-line applications, Microsoft ActiveX scripts, Integration Services packages, Analysis Services commands and queries, or Replication tasks. Jobs can run repetitive tasks or those that can be scheduled, and they can automatically notify users of job status by generating alerts, thereby greatly simplifying [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] administration.  
  
You can run a job manually, or you can configure it to run according to a schedule or in response to alerts.  
  
## Related Tasks  
  
|Description|Topic|  
|-|-|   
|Contains information about creating jobs and assigning ownership.|[Create Jobs](create-jobs.md)|  
|Contains information about organizing jobs into categories.|[Organize Jobs](organize-jobs.md)|  
|Contains information about the different kinds of job steps you can create and how to manage them.|[Manage Job Steps](manage-job-steps.md)|  
|Contains information about how to define when jobs start running and how often they should run.|[Create and Attach Schedules to Jobs](create-and-attach-schedules-to-jobs.md)|  
|Contains information about manually running jobs (without a schedule).|[Run Jobs](run-jobs.md)|  
|Contains information about how you can configure [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to respond to jobs. For example, you can configure [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to notify administrators when jobs are finished.|[Specify Job Responses](specify-job-responses.md)|  
|Contains information about how to view existing jobs, their history once executes, and how to modify them.|[View or Modify Jobs](view-or-modify-jobs.md)|  
|Contains information about how to delete jobs.|[Delete Jobs](delete-jobs.md)|  
  
## See Also  
[Implement SQL Server Agent Security](implement-sql-server-agent-security.md)  
