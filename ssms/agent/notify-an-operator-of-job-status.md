---
title: "Notify an Operator of Job Status"
description: "Notify an Operator of Job Status"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
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
# Notify an Operator of Job Status
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic describes how to set notification options in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio, [!INCLUDE[tsql](../includes/tsql-md.md)], or SQL Server Management Objects, so [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent can send notifications to operators about jobs.  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Security"></a>Security  
For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).  
  
## <a name="SSMS"></a>Using SQL Server Management Studio  
  
#### To notify an operator of job status  
  
1.  In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.  
  
2.  Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and select **Properties**.  
  
3.  In the **Job Properties** dialog box, select the **Notifications** page.  
  
4.  If you want to notify an operator by e-mail, check **E-mail**, select an operator from the list, and then select one of the following:  
  
    -   **When the job succeeds** to notify the operator when the job completes successfully.  
  
    -   **When the job fails** to notify the operator when the job completes unsuccessfully.  
  
    -   **When the job completes** to notify the operator regardless of completion status.  
  
5.  If you want to notify an operator by pager, check **Page**, select an operator from the list, and then select one of the following:  
  
    -   **When the job succeeds** to notify the operator when the job completes successfully.  
  
    -   **When the job fails** to notify the operator when the job completes unsuccessfully.  
  
    -   **When the job completes** to notify the operator regardless of completion status.  
  
6.  If you want to notify an operator by net send, check **Net send**, select an operator from the list, and then select one of the following:  
  
    -   **When the job succeeds** to notify the operator when the job completes successfully.  
  
    -   **When the job fails** to notify the operator when the job completes unsuccessfully.  
  
    -   **When the job completes** to notify the operator regardless of completion status.  
  
## <a name="TSQL"></a>Using Transact-SQL  
  
#### To notify an operator of job status  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    -- adds an e-mail notification for the specified alert (Test Alert).  
    -- This example assumes that Test Alert already exists
    --  and that François Ajenstat is a valid operator name.  
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_notification   
    @alert_name = N'Test Alert',   
    @operator_name = N'François Ajenstat',   
    @notification_method = 1 ;  
    GO  
    ```  
  
For more information, see [sp_add_notification (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).  
  
## <a name="SMO"></a>Using SQL Server Management Objects  
**To notify an operator of job status**  
  
Use the **Job** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell. For more information, see [SQL Server Management Objects (SMO)](/sql/relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide).  
