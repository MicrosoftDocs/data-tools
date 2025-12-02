---
title: "Create a Transact-SQL Job Step"
description: Create a Transact-SQL job step in SQL Server Agent, using SQL Server Management Studio, Transact-SQL, or SQL Server Management Objects.
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/01/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "Transact-SQL job step"
  - "job steps [Transact-SQL]"
  - "SQL Server Agent jobs, Transact-SQL step"
---
# Create a Transact-SQL job step in SQL Server Agent

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This article describes how to create a [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent job step that executes [!INCLUDE [tsql](../includes/tsql-md.md)] scripts in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio, [!INCLUDE [tsql](../includes/tsql-md.md)], or SQL Server Management Objects.

These job step scripts might call stored procedures and extended stored procedures. A single [!INCLUDE [tsql](../includes/tsql-md.md)] job step can contain multiple batches and embedded `GO` commands. For more information on creating a job, see [Create SQL Server Agent jobs](create-jobs.md).

## Security

For detailed information, see [Implement SQL Server Agent security](implement-sql-server-agent-security.md).

<a id="SSMS"></a>

## Use SQL Server Management Studio

1. In **Object Explorer,** connect to an instance of the [!INCLUDE [ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.

1. Expand **SQL Server Agent**, create a new job or right-click an existing job, and then select **Properties**.

1. In the **Job Properties** dialog, select the **Steps** page, and then select **New**.

1. In the **New Job Step** dialog, type a job **Step name**.

1. In the **Type** list, select **Transact-SQL Script (TSQL)**.

1. In the **Command** box, type the [!INCLUDE [tsql](../includes/tsql-md.md)] command batches, or select **Open** to select a [!INCLUDE [tsql](../includes/tsql-md.md)] file to use as the command.

1. Select **Parse** to check your syntax.

1. The message "Parse succeeded" is displayed when your syntax is correct. If an error is found, correct the syntax before continuing.

1. Select the **Advanced** page to set job step options, such as:

   - what action to take if the job step succeeds or fails,
   - how many times [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and
   - the file or table where [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent can write the job step output.

   Only members of the **sysadmin** fixed server role can write job step output to an operating system file. All SQL Server Agent users can log output to a table.

1. If you're a member of the **sysadmin** fixed server role and you want to run this job step as a different SQL login, select the SQL login from the **Run as user** list.

<a id="TSQL"></a>

## Use Transact-SQL

1. In **Object Explorer**, connect to an instance of [!INCLUDE [ssDE](../includes/ssde-md.md)].

1. On the Standard bar, select **New Query**.

1. Copy and paste the following example into the query window and select **Execute**.

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

<a id="SMO"></a>

## Use SQL Server Management Objects

Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, C#, or PowerShell.
