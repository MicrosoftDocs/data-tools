---
title: "Disable or Enable a Job"
description: "Disable or Enable a Job"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
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
# Disable or Enable a Job
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic describes how to disable a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio or [!INCLUDE[tsql](../includes/tsql-md.md)]. When you disable a job, it is not deleted and can be enabled again when necessary.  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Security"></a>Security  
For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).  
  
## <a name="SSMS"></a>Using SQL Server Management Studio  
  
#### To disable or enable a job  
  
1.  In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.  
  
2.  Expand **SQL Server Agent**.  
  
3.  Expand **Jobs**, and then right-click the job that you want to disable or enable.  
  
4.  To disable a job, click **Disable**. To enable a job, click **Enable**.  
  
## <a name="TSQL"></a>Using Transact-SQL  
  
#### To disable or enable a job  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    -- changes the name, description, and disables status of the job NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @new_name = N'NightlyBackups -- Disabled',  
        @description = N'Nightly backups disabled during server migration.',  
        @enabled = 0 ;  
    GO  
    ```  
  
For more information, see [sp_update_job (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).  
