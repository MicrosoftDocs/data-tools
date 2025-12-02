---
title: "Disable or Enable a Job"
description: Disable or enable a SQL Server Agent job, using SQL Server Management Studio or Transact-SQL.
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/01/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "stopping jobs"
  - "disabling jobs"
  - "SQL Server Agent jobs, disabling"
  - "jobs [SQL Server Agent], disabling"
---
# Disable or enable a SQL Server Agent job

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This article describes how to disable a [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent job in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio or [!INCLUDE [tsql](../includes/tsql-md.md)]. When you disable a job, it isn't deleted and can be enabled again when necessary.

## Security

For detailed information, see [Implement SQL Server Agent security](implement-sql-server-agent-security.md).

<a id="SSMS"></a>

## Use SQL Server Management Studio

1. In **Object Explorer**, connect to an instance of the [!INCLUDE [ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.

1. Expand **SQL Server Agent**.

1. Expand **Jobs**, and then right-click the job that you want to disable or enable.

1. To disable a job, select **Disable**. To enable a job, select **Enable**.

<a id="TSQL"></a>

## Use Transact-SQL

1. In **Object Explorer**, connect to an instance of [!INCLUDE [ssDE](../includes/ssde-md.md)].

1. On the Standard bar, select **New Query**.

1. Copy and paste the following example into the query window and select **Execute**. This example changes the name and description, and disables the status of the `NightlyBackups` job.

   ```sql
   USE msdb;
   GO

   EXECUTE dbo.sp_update_job
       @job_name = N'NightlyBackups',
       @new_name = N'NightlyBackups -- Disabled',
       @description = N'Nightly backups disabled during server migration.',
       @enabled = 0;
   GO
   ```

For more information, see [sp_update_job](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).
