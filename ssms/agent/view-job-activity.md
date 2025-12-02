---
title: "View Job Activity"
description: View the runtime state of SQL Server Agent job activity, using SQL Server Management Studio or Transact-SQL.
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/01/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "viewing job activity"
  - "jobs [SQL Server Agent], viewing"
  - "SQL Server Agent jobs, viewing"
  - "displaying job activity"
---
# View SQL Server Agent job activity

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This article describes how to view the runtime state of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio or [!INCLUDE [tsql](../includes/tsql-md.md)].

When the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent service starts, a new session is created and the `sysjobactivity` table in the `msdb` database is populated with all the existing defined jobs. This table records current job activity and status. You can use the Job Activity Monitor in [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent to view the current state of jobs. If the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent service unexpectedly terminates, you can refer to the `sysjobactivity` table to see which jobs were being executed when the service terminated.

## Security

For detailed information, see [Implement SQL Server Agent security](implement-sql-server-agent-security.md).

<a id="SSMS"></a>

## Use SQL Server Management Studio

1. In **Object Explorer**, connect to an instance of the [!INCLUDE [ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.

1. Expand **SQL Server Agent**.

1. Right-click **Job Activity Monitor** and select **View Job Activity**.

1. In the **Job Activity Monitor**, you can view details about each job that is defined for this server.

1. Right-click a job to start, stop, enable, or disable it. You can also refresh its status as displayed in the Job Activity Monitor, delete it, or view its history or properties. To start, stop, enable or disable, or refresh multiple jobs, select multiple rows in the Job Activity Monitor, and right-click your selection.

1. To update the Job Activity Monitor, select **Refresh**. To view fewer rows, select **Filter** and enter filter parameters.

<a id="TSQL"></a>

## Use Transact-SQL

1. In **Object Explorer**, connect to an instance of [!INCLUDE [ssDE](../includes/ssde-md.md)].

1. On the Standard bar, select **New Query**.

1. Copy and paste the following example into the query window and select **Execute**. This example lists activity for all jobs that the current user has permission to view.

   ```sql
   USE msdb;
   GO

   EXECUTE dbo.sp_help_jobactivity ;
   GO
   ```

For more information, see [sp_help_jobactivity](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql).
