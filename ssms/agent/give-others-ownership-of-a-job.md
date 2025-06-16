---
title: "Give Others Ownership of a Job"
description: "Give Others Ownership of a Job"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "jobs [SQL Server Agent], owners"
  - "owners [SQL Server], jobs"
  - "SQL Server Agent jobs, owners"
---
# Give Others Ownership of a Job
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic describes how to reassign ownership of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs to another user.  
  
-   **Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)  
  
-   **To give others ownership of a job, using:**  
  
    [SQL Server Management Studio](#SSMSProc2)  
  
    [Transact-SQL](#TsqlProc2)  
  
    [SQL Server Management Objects](#SMOProc2)  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Restrictions"></a>Limitations and Restrictions  
To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role. A job can be edited only by its owner or members of the **sysadmin** role. For more information about the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).  
  
You must be a system administrator to change the owner of a job.  
  
Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.  
  
### <a name="Security"></a>Security  
For security reasons, only the job owner or a member of the **sysadmin** role can change the definition of the job. Only members of the **sysadmin** fixed server role can assign job ownership to other users, and they can run any job, regardless of the job owner.  
  
> [!NOTE]  
> If you change job ownership to a user who is not a member of the **sysadmin** fixed server role, and the job is executing job steps that require proxy accounts (for example, [!INCLUDE[ssIS](../includes/ssis-md.md)] package execution), make sure that the user has access to that proxy account or else the job will fail.  
  
#### <a name="Permissions"></a>Permissions  
For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).  
  
## <a name="SSMSProc2"></a>Using SQL Server Management Studio  
**To give others ownership of a job**  
  
1.  In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.  
  
2.  Expand **SQL Server Agent**, expand **Jobs**, right-click the job, and then click **Properties**.  
  
3.  In the **Owner** list, select a login. You must be a system administrator to change the owner of a job.  
  
    Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.  
  
## <a name="TsqlProc2"></a>Using Transact-SQL  
**To give others ownership of a job**  
  
1.  In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.  
  
2.  On the toolbar, click **New Query**.  
  
3.  In the query window, enter the following statements that use the [sp_manage_jobs_by_login (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-manage-jobs-by-login-transact-sql) system stored procedure. The following example reassigns all jobs from `danw` to `françoisa`.  
  
    ```  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_manage_jobs_by_login  
        @action = N'REASSIGN',  
        @current_owner_login_name = N'danw',  
        @new_owner_login_name = N'françoisa' ;  
    GO  
    ```  
  
## <a name="SMOProc2"></a>Using SQL Server Management Objects  
**To give others ownership of a job**  
  
1.  Call the **Job** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell. For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](/sql/relational-databases/server-management-objects-smo/tasks/scheduling-automatic-administrative-tasks-in-sql-server-agent).  
  
## See Also  
[Implement Jobs](implement-jobs.md)  
[Create Jobs](create-jobs.md)  
