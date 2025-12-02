---
title: "View the Job History"
description: View the SQL Server Agent job history log, using SQL Server Management Studio, Transact-SQL, or SQL Server Management Objects.
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/01/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "jobs [SQL Server Agent], history"
  - "viewing job history"
  - "SQL Server Agent jobs, history"
  - "historical information [SQL Server], jobs"
  - "displaying job history"
---
# View the SQL Server Agent job history

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This article describes how to view the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent job history log in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio, [!INCLUDE [tsql](../includes/tsql-md.md)], or SQL Server Management Objects.

## Security

For detailed information, see [Implement SQL Server Agent security](implement-sql-server-agent-security.md).

<a id="SSMS"></a>

## Use SQL Server Management Studio

1. In **Object Explorer,** connect to an instance of the [!INCLUDE [ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.

1. Expand **SQL Server Agent**, and then expand **Jobs**.

1. Right-click a job, and then select **View History**.

1. In the Log File Viewer, view the job history.

1. To update the job history, select **Refresh**. To view fewer rows, select the **Filter** button and enter filter parameters.

<a id="TSQL"></a>

## Use Transact-SQL

1. In **Object Explorer**, connect to an instance of [!INCLUDE [ssDE](../includes/ssde-md.md)].

1. On the Standard bar, select **New Query**.

1. Copy and paste the following example into the query window and select **Execute**. This example lists all job information for the `NightlyBackups` job.

   ```sql
   USE msdb;
   GO

   EXECUTE dbo.sp_help_jobhistory @job_name = N'NightlyBackups';
   GO
   ```

For more information, see [sp_help_jobhistory](/sql/relational-databases/system-stored-procedures/sp-help-jobhistory-transact-sql).

<a id="SMO"></a>

## Use SQL Server Management Objects

Call the `EnumHistory` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell. For more information, see [SQL Server Management Objects (SMO)](/sql/relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide).
