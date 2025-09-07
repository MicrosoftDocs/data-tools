---
title: "Notify an Operator of Job Status"
description: "Notify an Operator of Job Status"
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/07/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "status information [SQL Server], jobs"
  - "jobs [SQL Server Agent], notification options"
  - "SQL Server Agent jobs, status"
  - "jobs [SQL Server Agent], status"
  - "SQL Server Agent jobs, notification options"
  - "notifications [SQL Server], job status"
---
# Notify an operator of job status

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This article describes how to set notification options in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio, [!INCLUDE [tsql](../includes/tsql-md.md)], or SQL Server Management Objects, so [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent can send notifications to operators about jobs.

## Security

For detailed information, see [Implement SQL Server Agent security](implement-sql-server-agent-security.md).

<a id="SSMS"></a>

## Use SQL Server Management Studio

1. In **Object Explorer,** connect to an instance of the [!INCLUDE [ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.

1. Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and select **Properties**.

1. In the **Job Properties** dialog box, select the **Notifications** page.

1. If you want to notify an operator by e-mail, check **E-mail**, select an operator from the list, and then select one of the following:

   - **When the job succeeds** to notify the operator when the job completes successfully.
   - **When the job fails** to notify the operator when the job completes unsuccessfully.
   - **When the job completes** to notify the operator regardless of completion status.

1. If you want to notify an operator by pager, check **Page**, select an operator from the list, and then select one of the following:

   - **When the job succeeds** to notify the operator when the job completes successfully.
   - **When the job fails** to notify the operator when the job completes unsuccessfully.
   - **When the job completes** to notify the operator regardless of completion status.

1. If you want to notify an operator by net send, check `net send`, select an operator from the list, and then select one of the following:

   - **When the job succeeds** to notify the operator when the job completes successfully.
   - **When the job fails** to notify the operator when the job completes unsuccessfully.
   - **When the job completes** to notify the operator regardless of completion status.

<a id="TSQL"></a>

## Use Transact-SQL

1. In **Object Explorer**, connect to an instance of [!INCLUDE [ssDE](../includes/ssde-md.md)].

1. On the Standard bar, select **New Query**.

1. Copy and paste the following example into the query window and select **Execute**. This example adds an e-mail notification for the specified alert (`Test Alert`). It assumes that `Test Alert` already exists, `François Ajenstat` is a valid operator name.

   ```sql
   USE msdb;
   GO

   EXECUTE dbo.sp_add_notification
       @alert_name = N'Test Alert',
       @operator_name = N'François Ajenstat',
       @notification_method = 1;
   GO
   ```

For more information, see [sp_add_notification](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).

<a id="SMO"></a>

## Use SQL Server Management Objects

Use the **Job** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell. For more information, see [SQL Server Management Objects (SMO)](/sql/relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide).
