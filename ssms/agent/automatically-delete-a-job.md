---
title: "Automatically Delete a Job"
description: "Automatically Delete a Job"
author: rwestMSFT
ms.author: randolphwest
ms.date: 06/03/2020
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "dropping jobs"
  - "SQL Server Agent jobs, removing"
  - "automatic job removal"
  - "jobs [SQL Server Agent], deleting"
  - "deleting jobs"
  - "removing jobs"
---

# Automatically Delete a Job

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> On [Azure SQL Managed Instance](/azure/sql-database/sql-database-managed-instance), most, but not all SQL Server Agent features are currently supported. See [Azure SQL Managed Instance T-SQL differences from SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) for details.

This topic describes how to configure [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] to automatically delete jobs when they succeed, fail, or complete by using SQL Server Management Studio or SQL Server Management Objects.  
  
Job responses ensure that database administrators know when jobs complete and how frequently they run. Typical job responses include:  
  
-   Notifying the operator by using e-mail, electronic paging, or a **net send** message.  
  
    Use one of these job responses if the operator must perform a follow-up action. For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.  
  
-   Writing an event message to the Windows application log.  
  
    You can use this response only for failed jobs.  
  
-   Automatically deleting the job.  
  
    Use this job response if you are certain that you do not need to rerun this job.  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Security"></a>Security  
For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).  
  
## <a name="SSMS"></a>Using SQL Server Management Studio  
  
#### To automatically delete a job  
  
1.  In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.  
  
2.  Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.  
  
3.  Select the **Notifications** page.  
  
4.  Check **Automatically delete job**, and choose one of the following:  
  
    -   Click **When the job succeeds** to delete the job status when it has completed successfully.  
  
    -   Click **When the job fails** to delete the job when it has completed unsuccessfully.  
  
    -   Click **When the job completes** to delete the job regardless of completion status.  
  
## <a name="SMO"></a>Using SQL Server Management Objects  
**To automatically delete a job**  
  
Use the **DeleteLevel** property of the **Job** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell. For more information, see [SQL Server Management Objects (SMO)](/sql/relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide).  
