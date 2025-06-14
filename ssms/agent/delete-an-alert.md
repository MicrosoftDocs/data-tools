---
title: "Delete an Alert"
description: "Delete an Alert"
author: rwestMSFT
ms.author: randolphwest
ms.date: 02/04/2021
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Agent, alerts"
  - "alerts [SQL Server], deleting"
  - "deleting alerts"
  - "canceling alerts"
  - "dropping alerts"
  - "disabling alerts"
  - "removing alerts"
---

# Delete an Alert

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This article describes how to delete Microsoft SQL Server Agent alerts using SQL Server Management Studio or Transact-SQL.

## <a name="BeforeYouBegin"></a>Before you begin

### <a name="Restrictions"></a>Limitations and restrictions

Removing an alert also removes any notifications associated with the alert.

### <a name="Security"></a>Security

#### <a name="Permissions"></a>Permissions

By default, only members of the **sysadmin** fixed server role can delete alerts.  

## <a name="SSMSProcedure"></a>Using SQL Server Management Studio

### To delete an alert

1. In **Object Explorer,** select the plus sign to expand the server that contains the SQL Server Agent alert that you want to delete.

2. Select the plus sign to expand **SQL Server Agent**.

3. Select the plus sign to expand the **Alerts** folder.

4. Right-click the alert you want to delete and select **Delete**.

5. In the **Delete Object** dialog box, confirm you chose the correct alert then select **OK**.

## <a name="TsqlProcedure"></a>Using Transact-SQL

### To delete an alert

1. In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].

2. On the Standard bar, select **New Query**.  

3. Copy and paste the following example into the query window and select **Execute**.

    ```
    -- deletes the SQL Server Agent alert called 'Test Alert.'
    USE msdb ;
    GO
  
    EXEC dbo.sp_delete_alert
       @name = N'Test Alert' ;
    GO
    ```

For more information, see [sp_delete_alert (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-delete-alert-transact-sql).
