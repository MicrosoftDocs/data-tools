---
title: "Create a User-Defined Event"
description: "Create a User-Defined Event"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Agent alerts, user-defined events"
  - "user-defined events [SQL Server]"
  - "multiple language support [SQL Server], alerts"
  - "languages [SQL Server], alerts"
  - "severity levels [SQL Server]"
  - "global considerations [SQL Server], alerts"
  - "events [SQL Server], user-defined"
  - "SQL Server Agent alerts, multiple-language environments"
  - "alerts [SQL Server], user-defined events"
  - "alerts [SQL Server], multiple-language environments"
  - "custom events [SQL Server Agent]"
  - "international considerations [SQL Server], alerts"
---
# Create a User-Defined Event
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> On [Azure SQL Managed Instance](/azure/sql-database/sql-database-managed-instance), most, but not all SQL Server Agent features are currently supported. See [Azure SQL Managed Instance T-SQL differences from SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) for details.

You can create user-defined events if you want to monitor events other than events that are predefined by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. You can also assign a severity level to each user-defined event.  
  
> [!NOTE]  
> When using SQL Server Management Studio, select the **Write to Windows application event log** option for each user-defined event message, to ensure that the messages are logged. By default, user-defined messages of severity lower than 19 are not sent to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows application log when they occur. User-defined messages of severity lower than 19 therefore do not trigger SQL Server Agent alerts.  
  
User-defined events must have a unique message number. Message numbers for a user-defined event must be greater than 50,000. You can define messages for the event in multiple languages. However, an **En-US** error message must exist before messages in other languages can be added.  
  
If you administer a multiple-language [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] environment, create user-defined messages in each of the languages that are supported. For example, if you are creating a new event message to be used on both an English and a German server, use the same message number and severity for both, but assign a different language to each.  
  
The following tasks provide information about how to create user-defined events and alerts that respond to them:  
  
**To create an alert based on a message number**  
  
-   [SQL Server Management Studio](create-an-alert-using-an-error-number.md)  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
**To create an alert based on severity levels**  
  
-   [SQL Server Management Studio](create-an-alert-using-severity-level.md)  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
**To define the response to an alert**  
  
-   [SQL Server Management Studio](define-the-response-to-an-alert-sql-server-management-studio.md)  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)  
  
**To create a user-defined event error message**  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql)  
  
**To modify a user-defined event error message**  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-altermessage-transact-sql)  
  
**To delete a user-defined event error message**  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-dropmessage-transact-sql)  
  
**To disable or reactivate an alert**  
  
-   [SQL Server Management Studio](disable-or-reactivate-an-alert.md)  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql)  
  
## See Also  
[sp_update_alert (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql)  
