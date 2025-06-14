---
title: Define the Response to an Alert
description: "Define the Response to an Alert"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Agent, alerts"
  - "alerts [SQL Server], responding to"
  - "responding to alerts"
---

# Define the Response to an Alert

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic describes how to define how [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] responds to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio or [!INCLUDE[tsql](../includes/tsql-md.md)].  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Restrictions"></a>Limitations and Restrictions  
  
-   The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. Avoid using these features in new development work, and plan to modify applications that currently use these features.  
  
-   Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators. For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).  
  
-   SQL Server Management Studio provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.  
  
### <a name="Security"></a>Security  
  
#### <a name="Permissions"></a>Permissions  
Only members of the **sysadmin** fixed server role can define the response to an alert.  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To define the response to an alert  
  
1.  In **Object Explorer**, click the plus sign to expand the server that contains the alert on which you want to define a response.  
  
2.  Click the plus sign to expand **SQL Server Agent**.  
  
3.  Click the plus sign to expand the **Alerts** folder.  
  
4.  Right-click the alert on which you want to define a response and select **Properties**.  
  
5.  In the _alert\_name_**alert properties** dialog box, under **Select a page**, select **Response**.  
  
6.  Select the **Execute job** check box and, from the list below the **Execute job** check box, select a job to execute when the alert occurs. You can create a new job by clicking **New Job**. You can view more information about the job by clicking **View Job**. For more information about the available options in the **New Job** and **Job Properties**_job\_name_ dialog boxes, see [Create a Job](create-a-job.md) and [View a Job](view-a-job.md).  
  
7.  Select the **Notify Operators** check box if you want to notify operators when the alert is activated. In the **Operator list**, select one or more of the following methods for notifying the operator or operators: **E-mail**, **Pager**, or **Net Send**. You can create a new operator by clicking **New Operator**. You can view more information about an operator by clicking **View Operator**. For more information about the available options in the **New Operator** and **View Operator Properties** dialog boxes, see [Create an Operator](create-an-operator.md) and [View Information About an Operator](view-information-about-an-operator.md).  
  
8.  When finished, click **OK**.  
  
## <a name="TsqlProcedure"></a>Using Transact-SQL  
  
#### To define the response to an alert  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    -- adds an e-mail notification for Test Alert.  
    -- assumes that Test Alert already exists and that
    -- François Ajenstat is a valid operator name   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_notification  
     @alert_name = N'Test Alert',  
     @operator_name = N'François Ajenstat',  
     @notification_method = 1 ;  
    GO  
    ```  
  
For more information, see [sp_add_notification (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).
