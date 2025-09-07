---
title: "Stop a Job"
description: Stop a SQL Agent job with SQL Server Management Studio, Transact-SQL, or SQL Server Management Objects.
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/07/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "jobs [SQL Server Agent], stopping"
  - "SQL Server Agent jobs, stopping"
  - "stopping jobs"
---
# Stop a job

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This article describes how to stop a [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent job. A job is a specified series of actions that SQL Server Agent performs.

## Limitations

If a job is currently executing a step of type **CmdExec** or **PowerShell**, the process that is being run (for example, `MyProgram.exe`) is forced to end prematurely. This can cause unpredictable behavior, such as files that are being used by the process being held open.

For a multiserver job, a `STOP` instruction for the job is posted to all target servers of the job.

## Security

For detailed information, see [Implement SQL Server Agent security](implement-sql-server-agent-security.md).

<a id="SSMS"></a>

## Use SQL Server Management Studio

### Stop a job

1. In **Object Explorer,** connect to an instance of the [!INCLUDE [ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.

1. Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to stop, and then select **Stop Job**.

1. If you want to stop multiple jobs, right-click **Job Activity Monitor**, and then select **View Job Activity**. In the Job Activity Monitor, select the jobs you want to stop, right-click your selection, and then select **Stop Jobs**.

## Use Transact-SQL

1. In **Object Explorer**, connect to an instance of [!INCLUDE [ssDE](../includes/ssde-md.md)].

1. On the Standard bar, select **New Query**.

1. Copy and paste the following example into the query window and select **Execute**. This example stops a job named `Weekly Sales Data Backup`.

   ```sql
   USE msdb;
   GO

   EXECUTE dbo.sp_stop_job N'Weekly Sales Data Backup';
   GO
   ```

For more information, see [sp_stop_job](/sql/relational-databases/system-stored-procedures/sp-stop-job-transact-sql).

<a id="SMO"></a>

## Use SQL Server Management Objects

Call the **Stop** method of the **Job** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell. For more information, see [SQL Server Management Objects (SMO)](/sql/relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide).
