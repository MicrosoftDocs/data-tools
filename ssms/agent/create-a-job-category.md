---
title: "Create a Job Category"
description: "Create a Job Category"
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/19/2024
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Agent jobs, categories"
  - "jobs [SQL Server Agent], categories"
  - "categories [SQL Server Agent jobs]"
---

# Create a Job Category

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This article describes how to create a job category in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio, [!INCLUDE [tsql](../includes/tsql-md.md)] or [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Management Objects.

[!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent provides built-in job categories that you can assign jobs to, or you can create a job category and assign jobs to it. Job categories help you organize your jobs for easy filtering and grouping. For example, you can organize all your database backup jobs in the Database Maintenance category. You can also create your own job categories.

## <a id="BeforeYouBegin"></a> Before You Begin

### <a id="Restrictions"></a> Limitations and Restrictions

Multiserver categories exist only on a master server. There is only one default job category available on a master server: [**Uncategorized (Multi-Server)**]. When a multiserver job is downloaded, its category is changed to **Jobs From MSX** at the target server.

### <a id="Security"></a> Security

For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).

## <a id="SSMS"></a> Using SQL Server Management Studio

#### To create a job category

1. In **Object Explorer**, select the plus sign to expand the server where you want to create a job category.

1. Select the plus sign to expand **SQL Server Agent**.

1. Right-click the **Jobs** folder and select **Manage Job Categories**.

1. In the **Manage Job Categories**_server_name_ dialog box, select **Add**.

1. In the new dialog box, in the **Name** box, enter a name for the new job category.

1. Select the **Show all jobs** check box. Select one or more jobs for the new category by checking the boxes corresponding to the jobs.

1. Select **OK**.

1. In the **Manage Job Categories**_server_name_ dialog box, select **Refresh** to ensure that the new job category is active. If everything looks as expected, close this dialog box.

For more information on these dialog boxes, see [Job Categories - Manage Job Categories](job-categories-manage-job-categories.md) and [Job Categories Properties - New Job Category](job-categories-properties-new-job-category.md).

## <a id="TSQL"></a> Using Transact-SQL

#### To create a job category

1. In **Object Explorer**, connect to an instance of [!INCLUDE [ssDE](../includes/ssde-md.md)].

1. On the Standard bar, select **New Query**.

1. Copy and paste the following example into the query window and select **Execute**.

    ```sql
    -- creates a local job category named AdminJobs
    USE msdb ;
    GO
    EXEC dbo.sp_add_category
        @class=N'JOB',
        @type=N'LOCAL',
        @name=N'AdminJobs' ;
    GO
    ```

For more information, see [sp_add_category (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-add-category-transact-sql).

## <a id="SMO"></a> Using SQL Server Management Objects

**To create a job category**

Call the **JobCategory** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell. For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](/sql/relational-databases/server-management-objects-smo/tasks/scheduling-automatic-administrative-tasks-in-sql-server-agent).

## Related content

- [Create a Job Step](job-properties-new-job-steps-page.md)
- [Create a Job](create-a-job.md)
