---
title: Change the Scheduling Details for a Master Job
description: "Change the Scheduling Details for a SQL Server Agent Master Job"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---

# Change the Scheduling Details for a SQL Server Agent Master Job

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic describes how to change the scheduling details for a job definition in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio or [!INCLUDE[tsql](../includes/tsql-md.md)].  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Restrictions"></a>Limitations and Restrictions  
A [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.  

> [!WARNING]
> It is possible to attach multiple jobs to the same schedule. Note that updating a schedule will impact all the jobs attached to the schedule.

### <a name="Security"></a>Security  
  
#### <a name="Permissions"></a>Permissions  
Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own. For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To change the scheduling details for a job definition  
  
1. In **Object Explorer,** click the plus sign to expand the server that contains the job whose schedule you want to edit.  
  
2. Click the plus sign to expand **SQL Server Agent**.  
  
3. Click the plus sign to expand the **Jobs** folder.  
  
4. Right-click the job whose schedule you want to edit and select **Properties**.  
  
5. In the **Job Properties -**_job\_name_ dialog box, under **Select a page**, select **Schedules**. For more information on the available options on this page, see [Job Properties - New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md).  
  
6. When finished, click **OK**.  
  
## <a name="TsqlProcedure"></a>Using Transact-SQL  
  
#### To change the scheduling details for a job definition
  
1. In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].  
  
2. On the Standard bar, click **New Query**.  
  
3. Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    -- changes the enabled status of the NightlyJobs schedule to 0
    -- and sets the owner to terrid.
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_schedule  
        @name = 'NightlyJobs',  
        @enabled = 0,  
        @owner_login_name = 'terrid' ;  
    GO  
    ```  
  
For more information, see [sp_update_schedule (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql).
