---
title: "Change the Membership of a Job Category"
description: "Change the Membership of a Job Category"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Agent jobs, categories"
  - "jobs [SQL Server Agent], categories"
  - "categories [SQL Server Agent jobs]"
  - "members [SQL Server], job categories"
---
# Change the Membership of a Job Category
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> On [Azure SQL Managed Instance](/azure/sql-database/sql-database-managed-instance), most, but not all SQL Server Agent features are currently supported. See [Azure SQL Managed Instance T-SQL differences from SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) for details.

This topic describes how to change the membership of the job category in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio, [!INCLUDE[tsql](../includes/tsql-md.md)], or SQL Server Management Objects.  
  
Job categories help you organize your jobs for easy filtering and grouping. You can create your own job categories. You can also change Microsoft SQL Server Agent jobs membership in job categories.  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Security"></a>Security  
For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).  
  
## <a name="SSMS"></a>Using SQL Server Management Studio  
  
#### To change the membership of a job category  
  
1.  In **Object Explorer**, click the plus sign to expand the server where you want to edit a job category.  
  
2.  Click the plus sign to expand **SQL Server Agent**.  
  
3.  Right-click the **Jobs** folder and select **Manage Job Categories**.  
  
4.  In the **Manage Job Categories**_server_name_ dialog box, select the job category that you want to edit, and then click **View Jobs**.  
  
5.  Select the **Show all jobs** check box.  
  
6.  To add a job to the category, in the main grid, select the check box in the **Select** column corresponding to the job. To remove a job from the category, clear the box. When finished, click **OK**.  
  
7.  Close the **Manage Job Categories**_server_name_ dialog box.  
  
## <a name="TSQL"></a>Using Transact-SQL  
  
#### To change the membership of a job category  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    -- adding a new job category to the "NightlyBackups" job  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @category_name = N'[Uncategorized (Local)]';  
    GO  
    ```  
  
For more information, see [sp_update_job (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).  
  
## <a name="SMO"></a>Using SQL Server Management Objects  
**To change the membership of a job category**  
  
Use the **JobCategory** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.  
