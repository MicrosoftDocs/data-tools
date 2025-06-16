---
title: Set the SQL Server Connection for the SQL Server Agent Service
description: "Set the SQL Server Connection for the SQL Server Agent Service"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Agent, connections"
  - "connections [SQL Server], SQL Server Agent service"
---

# Set the SQL Server Connection for the SQL Server Agent Service

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic describes how to set the connection between [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent and the [!INCLUDE[ssDE](../includes/ssde-md.md)] in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio. The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service can connect to a local instance of SQL Server by using Windows Authentication.  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Restrictions"></a>Limitations and Restrictions  
  
-   Object Explorer only displays the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent node if you have permission to use it.  
  
-   Beginning with [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent does not support [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication. This option is available only when you administer an earlier version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].  
  
### <a name="Security"></a>Security  
  
#### <a name="Permissions"></a>Permissions  
To perform its functions, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. The account must have the following Windows permissions:  
  
-   Log on as a service (SeServiceLogonRight)  
  
-   Replace a process-level token (SeAssignPrimaryTokenPrivilege)  
  
-   Bypass traverse checking (SeChangeNotifyPrivilege)  
  
-   Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)  
  
For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Setting Up Windows Service Accounts](/sql/database-engine/configure-windows/configure-windows-service-accounts-and-permissions).  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To set the SQL Server connection  
  
1.  In **Object Explorer**, click the plus sign to expand the server that you want to set up with a connection to its SQL Server Agent Service.  
  
2.  Right-click **SQL Server Agent** and select **Properties**.  
  
3.  In the **SQL Server Agent Properties** dialog box, under **Select a page**, click **Connection**.  
  
4.  Under **SQL Server connection**, select **Use Windows Authentication** to enable [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to connect to an instance of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] with [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication. Connections to [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] and later databases require Windows Authentication.  
