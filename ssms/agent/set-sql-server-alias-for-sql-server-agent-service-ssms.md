---
title: Set a SQL Server Alias for the SQL Server Agent Service
description: "Set a SQL Server Alias for the SQL Server Agent Service"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "aliases [SQL Server], creating"
  - "SQL Server Agent, aliases"
---

# Set a SQL Server Alias for the SQL Server Agent Service

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> On [Azure SQL Managed Instance](/azure/sql-database/sql-database-managed-instance), most, but not all SQL Server Agent features are currently supported. See [Azure SQL Managed Instance T-SQL differences from SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) for details.

This topic describes how to set a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] alias for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to use to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] by using SQL Server Management Studio. By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service connects to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] over named pipes by using dynamic server names that require no additional client configuration. You need to configure a server connection alias only if you are not using the default network transport or if you are connecting to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that listens on an alternate named pipe.  

## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Restrictions"></a>Limitations and Restrictions  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent will not work correctly unless you select an alias that refers to the local instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].  
  
-   Object Explorer only displays the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent node if you have permission to use it.  
  
### <a name="Security"></a>Security  
  
#### <a name="Permissions"></a>Permissions  
To perform its functions, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. The account must have the following Windows permissions:  
  
-   Log on as a service (SeServiceLogonRight)  
  
-   Replace a process-level token (SeAssignPrimaryTokenPrivilege)  
  
-   Bypass traverse checking (SeChangeNotifyPrivilege)  
  
-   Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)  
  
For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Setting Up Windows Service Accounts](/sql/database-engine/configure-windows/configure-windows-service-accounts-and-permissions).  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To set a SQL Server Alias for the SQL Server Agent Service  
  
1.  In the **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] and then expand that instance.  
  
2.  Right-click **SQL Server Agent**, and then click **Properties**.  
  
3.  In the **SQL Server Agent Properties**_server\_name_ dialog box, under **Select a page**, select **Connection**, and  
  
4.  In the **Alias local host server** box, type the alias of the server to which [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should connect.  
  
5.  Click **OK**.  
