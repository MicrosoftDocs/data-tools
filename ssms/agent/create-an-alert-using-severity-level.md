---
title: "Create an Alert Using Severity Level"
description: "Create an Alert Using Severity Level"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "alerts [SQL Server], creating"
  - "SQL Server Agent, alerts"
  - "severity levels [SQL Server]"
  - "alerts [SQL Server], severity levels"
---
# Create an Alert Using Severity Level
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> On [Azure SQL Managed Instance](/azure/sql-database/sql-database-managed-instance), most, but not all SQL Server Agent features are currently supported. See [Azure SQL Managed Instance T-SQL differences from SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) for details.

This topic describes how to create a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent alert that is raised when an event of a specific severity level occurs in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio or [!INCLUDE[tsql](../includes/tsql-md.md)].  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Restrictions"></a>Limitations and Restrictions  
  
-   SQL Server Management Studio provides an easy, graphical way to manage the entire alerting system and is the recommended way to configure an alert infrastructure.  
  
-   Events generated with **xp_logevent** occur in the master database. Therefore, **xp_logevent** does not trigger an alert unless the **\@database_name** for the alert is **'master'** or NULL.  
  
-   Severity levels from 19 through 25 send a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] message to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows application log and trigger an alert. Events with severity levels less than 19 will trigger alerts only if you have used **sp_altermessage**, RAISERROR WITH LOG, or **xp_logevent** to force them to be written to the Windows application log.  
  
### <a name="Security"></a>Security  
  
#### <a name="Permissions"></a>Permissions  
By default, only members of the **sysadmin** fixed server role can execute **sp_add_alert**.  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To create an alert using severity level  
  
1.  In **Object Explorer,** click the plus sign to expand the server where you want to create an alert using severity level.  
  
2.  Click the plus sign to expand **SQL Server Agent**.  
  
3.  Right-click **Alerts** and select **New Alert**.  
  
4.  In the **New Alert** dialog box, in the **Name** box, enter a name for this alert.  
  
5.  In the **Type** list, select **SQL Server event alert**.  
  
6.  Under **Event alert definition**, in the **Database name** list, select a database to restrict the alert to a specific database.  
  
7.  Under **Alerts will be raised based on**, click **Severity** and then select the specific severity that will raise the alert.  
  
8.  Check the box corresponding to **Raise alert when message contains** check box to restrict the alert to a particular character sequence, and then enter a keyword or character string for the **Message text**. The maximum number of characters is 100.  
  
9. Click **OK**.  
  
## <a name="TsqlProcedure"></a>Using Transact-SQL  
  
#### To create an alert using severity level  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    -- Adds an alert (Test Alert) that notifies the
    -- Alert Operator via email when an error with a 
    -- severity of 23 is detected.
    
    -- Assumes that the Alert Operator already exists 
    -- and that database mail is configured.
    
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_alert @name=N'Test Alert', 
      @message_id = 0, 
      @severity = 23, 
      @enabled = 1, 
      @include_event_description_in = 1
    ;
    GO
    
    EXEC dbo.sp_add_notification @alert_name=N'Test Alert',
      @operator_name=N'Alert Operator',
      @notification_method=1
    ;
    GO

    ```  
  
For more information, see [sp_add_alert (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql).  
