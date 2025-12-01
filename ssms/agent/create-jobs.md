---
title: "Create Jobs"
description: Learn how to create a SQL Server Agent job, which can perform a series of sequential operations.
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/01/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "jobs [SQL Server Agent], creating"
  - "SQL Server Agent jobs, creating"
---
# Create SQL Server Agent jobs

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

A job is a specified series of operations performed sequentially by [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent.

A job can perform a wide range of activities, including:

- running [!INCLUDE [tsql](../includes/tsql-md.md)] scripts
- command prompt applications
- SQL Server Integration Services (SSIS) packages
- Analysis Services commands and queries
- Replication tasks

Jobs can run repetitive or schedulable tasks, and they can automatically notify users of job status by generating alerts, which simplifies [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] administration.

## Create a SQL Server Agent job

To create a job, a user must be a member of one of the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role. A job can be edited only by its owner or members of the **sysadmin** role. Members of the **sysadmin** role can assign job ownership to other users, and they can run any job, regardless of the job owner. For more information about the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent fixed database roles](sql-server-agent-fixed-database-roles.md).

Jobs can be written to run on the local instance of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] or on multiple instances across an enterprise. To run jobs on multiple servers, you must set up at least one master server and one or more target servers. For more information about master and target servers, see [Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md)

[!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent records job and job step information in the job history.

## Related tasks

| Description | Article |
| --- | --- |
| Describes how to create a [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent job. | [Create a SQL Server Agent job](create-a-job.md) |
| Describes how to reassign ownership of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs to another user. | [Give others ownership of a job](give-others-ownership-of-a-job.md) |
| Describes how to set up the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent job history log. | [Set Up the Job History Log](set-up-the-job-history-log.md) |

## Related content

- [Manage job steps](manage-job-steps.md)
- [Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md)
- [Create and Attach Schedules to Jobs](create-and-attach-schedules-to-jobs.md)
- [Run Jobs](run-jobs.md)
- [View or Modify Jobs](view-or-modify-jobs.md)
