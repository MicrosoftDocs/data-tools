---
title: "Add Steps to a SQL Server Agent Master Job"
description: Learn how to add steps to a SQL Server Agent master job in SQL Server.
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/07/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---
# Add steps to a SQL Server Agent master job

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This article describes how to add steps to a SQL Server Agent master job in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] with [!INCLUDE [ssManStudioFull](../includes/ssmanstudiofull-md.md)] or [!INCLUDE [tsql](../includes/tsql-md.md)].

## Limitations

A [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent master job can't be targeted at both local and remote servers.

## Permissions

Unless you're a member of the **sysadmin** fixed server role, you can only modify jobs that you own. For detailed information, see [Implement SQL Server Agent security](../agent/implement-sql-server-agent-security.md).

<a id="SSMSProcedure"></a>

## Use SQL Server Management Studio

1. In **Object Explorer,** select the plus sign to expand the server that contains the job to which you want to add steps.

1. Select the plus sign to expand **SQL Server Agent**.

1. Select the plus sign to expand the **Jobs** folder.

1. Right-click the job to which you want to add steps and select **Properties**.

1. In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**. For more information on the available options on this page, see [Job Properties - New Job (Steps Page)](../agent/job-properties-new-job-steps-page.md).

1. When finished, select **OK**.

<a id="TsqlProcedure"></a>

## Use Transact-SQL

1. In **Object Explorer**, connect to an instance of [!INCLUDE [ssDE](../includes/ssde-md.md)].

1. On the Standard bar, select **New Query**.

1. Copy and paste the following example into the query window and select **Execute**. This example creates a job step that changes database access to read-only for the `Sales` database. It specifies five retry attempts, with each retry to occur after a 5-minute wait. The example assumes that the `Weekly Sales Data Backup` job already exists.

   ```sql
   USE msdb;
   GO

   EXECUTE sp_add_jobstep
       @job_name = N'Weekly Sales Data Backup',
       @step_name = N'Set database to read only',
       @subsystem = N'TSQL',
       @command = N'ALTER DATABASE SALES SET READ_ONLY',
       @retry_attempts = 5,
       @retry_interval = 5;
   GO
   ```

For more information, see [sp_add_jobstep](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).
