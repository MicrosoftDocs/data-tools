---
title: "View Job Activity"
description: "View Job Activity"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
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
# View Job Activity
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic describes how to view the runtime state of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio or [!INCLUDE[tsql](../includes/tsql-md.md)].  
  
When the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service starts, a new session is created and the **sysjobactivity** table in the **msdb** database is populated with all the existing defined jobs. This table records current job activity and status. You can use the Job Activity Monitor in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to view the current state of jobs. If the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service unexpectedly terminates, you can refer to the **sysjobactivity** table to see which jobs were being executed when the service terminated.  
  
## Before You Begin  
  
### <a name="Security"></a>Security  
For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).  
  
## <a name="SSMS"></a>Using SQL Server Management Studio  
  
#### To view job activity  
  
1.  In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.  
  
2.  Expand **SQL Server Agent**.  
  
3.  Right-click **Job Activity Monitor** and click **View Job Activity**.  
  
4.  In the **Job Activity Monitor**, you can view details about each job that is defined for this server.  
  
5.  Right-click a job to start it, stop it, enable or disable it, refresh its status as displayed in the Job Activity Monitor, delete it, or view its history or properties.  To start, stop, enable or disable, or refresh multiple jobs, select multiple rows in the Job Activity Monitor, and right-click your selection.  
  
6.  To update the Job Activity Monitor, click **Refresh**. To view fewer rows, click **Filter** and enter filter parameters.  
  
## <a name="TSQL"></a>Using Transact-SQL  
  
#### To view job activity  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    -- lists activity for all jobs that the current user has permission to view.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_jobactivity ;  
    GO  
    ```  
  
For more information, see [sp_help_jobactivity (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql).  
