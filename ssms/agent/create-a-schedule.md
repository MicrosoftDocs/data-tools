---
title: "Create a Schedule"
description: Learn how to create a SQL Server Agent schedule.
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/07/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "scheduling jobs [SQL Server]"
  - "SQL Server Agent jobs, scheduling"
  - "jobs [SQL Server Agent], scheduling"
  - "schedules [SQL Server], jobs"
---
# Create a schedule

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

You can create a schedule for [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio, [!INCLUDE [tsql](../includes/tsql-md.md)], or SQL Server Management Objects.

## Security

For detailed information, see [Implement SQL Server Agent security](implement-sql-server-agent-security.md).

<a id="SSMS"></a>

## Use SQL Server Management Studio

1. In **Object Explorer**, connect to an instance of the [!INCLUDE [ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.

1. Expand **SQL Server Agent**, right-click **Jobs**, and select **Manage Schedules**.

1. In the **Manage Schedules** dialog box, select **New**.

1. In the **Name** box, type a name for the new schedule.

1. If you don't want the schedule to take effect immediately after it has been created, clear the **Enabled** check box.

1. For **Schedule Type**, select one of the following:

   - To start the job when the CPUs reach an idle condition, select **Start whenever the CPUs become idle**.

   - If you want a schedule to run repeatedly, select **Recurring**. To set the recurring schedule, complete the **Frequency**, **Daily Frequency**, and **Duration** groups on the dialog.

   - If you want the schedule to run only one time, select **One time**. To set the **One time** schedule, complete the **One-time occurrence** group on the dialog box.

<a id="TSQL"></a>

## Use Transact-SQL

1. In **Object Explorer**, connect to an instance of [!INCLUDE [ssDE](../includes/ssde-md.md)].

1. On the Standard bar, select **New Query**.

1. Copy and paste the following example into the query window and select **Execute**. This example creates a schedule named `RunOnce`. The schedule runs one time, at 23:30 on the day that the schedule is created.

   ```sql
   USE msdb;
   GO

   EXECUTE dbo.sp_add_schedule
       @schedule_name = N'RunOnce',
       @freq_type = 1,
       @active_start_time = 233000;
   GO
   ```

For more information, see [sp_add_schedule](/sql/relational-databases/system-stored-procedures/sp-add-schedule-transact-sql).

<a id="SMO"></a>

## Use SQL Server Management Objects

Use the **JobSchedule** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell. For more information, see [SQL Server Management Objects (SMO)](/sql/relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide).
