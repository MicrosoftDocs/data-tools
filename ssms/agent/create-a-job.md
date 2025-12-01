---
title: Create a SQL Server Agent Job
description: Create a SQL Server Agent job using SQL Server Management Studio, Transact-SQL, or SQL Server Management Objects.
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

# Create a SQL Server Agent job

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> On [Azure SQL Managed Instance](/azure/sql-database/sql-database-managed-instance), most SQL Server Agent features are supported. For more information, see [Azure SQL Managed Instance T-SQL differences](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent).

This article explains how to create a SQL Server Agent job using SQL Server Management Studio (SSMS), Transact-SQL (T-SQL), or SQL Server Management Objects (SMO).

To add job steps, schedules, alerts, and notifications that can be sent to operators, see the links to articles in the [Related content](#related-content) section.

## Prerequisites

- User must be a member of SQL Server Agent fixed database roles or the **sysadmin** role.
- Only job owners or members of the **sysadmin** role can modify jobs.
- Assigning a job to another login doesn't guarantee sufficient permissions to run the job.

## Security considerations

- Only the **sysadmin** role can change the job owner.
- The **sysadmin** role can assign job ownership to other users and run any job.
- Jobs with steps requiring proxy accounts need to ensure the new owner has access to those proxies, or the job fails.

For detailed security information, see [Implement SQL Server Agent security](implement-sql-server-agent-security.md)

<a id="SSMS"></a>

## Use SQL Server Management Studio

1. In **Object Explorer**, expand the server where you're creating the job.

1. Expand **SQL Server Agent**.

1. Right-click **Jobs** and select **New Job...**.

1. On the **General** page, configure job properties. For more information, see [General page](job-properties-new-job-general-page.md).

1. On the **Steps** page, configure the job steps. For more information, see [Steps page](job-properties-new-job-steps-page.md).

1. On the **Schedules** page, set job schedules. For more information, see [Schedules page](job-properties-new-job-schedules-page.md).

1. On the **Alerts** page, configure job alerts. For more information, see [Alerts page](job-properties-new-job-alerts-page.md).

1. On the **Notifications** page, configure job completion notifications. For more information, see [Notifications page](job-properties-new-job-notifications-page.md).

1. On the **Targets** page, configure the target servers. For more information, see [Targets page](job-properties-new-job-targets-page.md).

1. Select **OK** to save the job.

<a id="TSQL"></a>

## Use Transact-SQL

1. In **Object Explorer**, connect to the server.
1. Open a **New Query** window.
1. Copy and paste the following script:

   ```sql
   USE msdb;
   GO

   EXECUTE dbo.sp_add_job @job_name = N'Weekly Sales Data Backup';
   GO

   EXECUTE sp_add_jobstep
       @job_name = N'Weekly Sales Data Backup',
       @step_name = N'Set database to read only',
       @subsystem = N'TSQL',
       @command = N'ALTER DATABASE SALES SET READ_ONLY',
       @retry_attempts = 5,
       @retry_interval = 5;
   GO

   EXECUTE dbo.sp_add_schedule
       @schedule_name = N'RunOnce',
       @freq_type = 1,
       @active_start_time = 233000;
   GO

   EXECUTE sp_attach_schedule
       @job_name = N'Weekly Sales Data Backup',
       @schedule_name = N'RunOnce';
   GO

   EXECUTE dbo.sp_add_jobserver @job_name = N'Weekly Sales Data Backup';
   GO
   ```

For more information, see:

- [sp_add_job](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)
- [sp_add_jobstep](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)
- [sp_add_schedule](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql)
- [sp_attach_schedule](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)
- [sp_add_jobserver](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)

<a id="SMO"></a>

## Use SQL Server Management Objects

To create a SQL Server Agent job using SQL Server Management Objects (SMO):

Call the **Create** method of the **Job** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell. For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](/sql/relational-databases/server-management-objects-smo/tasks/scheduling-automatic-administrative-tasks-in-sql-server-agent).

## Related content

- [Job Properties - New Job (Steps Page)](job-properties-new-job-steps-page.md)
- [Create a Job Category](create-a-job-category.md)
