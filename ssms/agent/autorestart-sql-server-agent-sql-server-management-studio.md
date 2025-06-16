---
title: Auto Restart SQL Server Agent
description: "Auto Restart SQL Server Agent"
author: rwestMSFT
ms.author: randolphwest
ms.date: 07/28/2021
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Agent, starting"
  - "autostart SQL Server Agent"
---

# Auto Restart SQL Server Agent

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic describes how to configure Microsoft SQL Server Agent to automatically restart if it should stop unexpectedly.  
  
## <a name="BeforeYouBegin"></a>Before You Begin
  
### <a name="Restrictions"></a>Limitations and Restrictions

Object Explorer only displays the SQL Server Agent node if you have permission to use it.  
  
### <a name="Security"></a>Security
  
#### <a name="Permissions"></a>Permissions

To perform its functions, SQL Server Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in SQL Server. The account must have the following Windows permissions:  
  
- Log on as a service (SeServiceLogonRight)  
  
- Replace a process-level token (SeAssignPrimaryTokenPrivilege)  
  
- Bypass traverse checking (SeChangeNotifyPrivilege)  
  
- Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)  
  
 > [!NOTE]
 > For Auto Restart to function properly, the account running the SQL Server Agent service must be a local administrator on the server.

For more information about the Windows permissions required for the SQL Server Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Setting Up Windows Service Accounts](/sql/database-engine/configure-windows/configure-windows-service-accounts-and-permissions).  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
### To configure SQL Server Agent to automatically restart  
  
1. In **Object Explorer**, click the plus sign to expand the server where you want to configure SQL Server Agent to automatically restart.  

2. Right-click **SQL Server Agent**, and then click **Properties**.  

3. On the **General** page, check **Auto restart SQL Server Agent if it stops unexpectedly**.  
