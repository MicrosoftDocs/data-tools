---
title: "View a Job"
description: View a SQL Server Agent job using SQL Server Management Studio, Transact-SQL, or SQL Server Management Objects.
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/01/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "jobs [SQL Server Agent], viewing"
  - "viewing jobs"
  - "SQL Server Agent jobs, viewing"
  - "displaying jobs"
---

# View a SQL Server Agent job

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This article describes how to view [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio or [!INCLUDE [tsql](../includes/tsql-md.md)].

## Security

You can only view jobs that you own, unless you're a member of the **sysadmin** fixed server role. Members of this role can view all jobs. For detailed information, see [Implement SQL Server Agent security](implement-sql-server-agent-security.md).

<a id="SSMS"></a>

## Use SQL Server Management Studio

1. In **Object Explorer,** connect to an instance of the [!INCLUDE [ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.

1. Expand **SQL Server Agent**, and then expand **Jobs**.

1. Right-click a job, and then select **Properties**.

<a id="TSQL"></a>

## Use Transact-SQL

1. In **Object Explorer**, connect to an instance of [!INCLUDE [ssDE](../includes/ssde-md.md)].

1. On the Standard bar, select **New Query**.

1. Copy and paste the following example into the query window and select **Execute**. This example lists all aspects of the information for the `NightlyBackups` job.

   ```sql
   USE msdb;
   GO

   EXECUTE dbo.sp_help_job
       @job_name = N'NightlyBackups',
       @job_aspect = N'ALL';
   GO
   ```

<a id="SMO"></a>

## Use SQL Server Management Objects

**To view a job**

Use the **Job** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell. For more information, see [SQL Server Management Objects (SMO)](/sql/relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide).
