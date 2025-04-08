---
title: "Proxy Account Properties - New Proxy Account (General Page)"
description: "Proxy Account Properties - New Proxy Account (General Page)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.ag.proxy.general.f1"
---
# Proxy Account Properties - New Proxy Account (General Page)
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> On [Azure SQL Managed Instance](/azure/sql-database/sql-database-managed-instance), most, but not all SQL Server Agent features are currently supported. See [Azure SQL Managed Instance T-SQL differences from SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) for details.

Use this page to view or change the properties of a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent proxy account.  
  
## Options  
**Proxy name**  
Type the name of the proxy.  
  
**Credential name**  
Type the name of the credential for the proxy.  
  
> [!NOTE]  
> The credential name provided must be the name of an existing credential. For information on creating credentials, see [How to: Create a Proxy](/sql/relational-databases/security/authentication-access/create-a-credential)  
  
**...**  
Launches the **Select Credential** dialog.  
  
**Description**  
Type the description for the proxy.  
  
**Active to the following subsystems**  
Select the subsystems that the proxy account has access to.  
  
**Reassign job steps to**  
Select the proxy to reassign job steps to. This list is enabled when you revoke access to a subsystem that the proxy previously had access to.  
  
## See Also  
[Create a SQL Server Agent Proxy](create-a-sql-server-agent-proxy.md)  
