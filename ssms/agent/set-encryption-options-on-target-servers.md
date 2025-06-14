---
title: "Set Encryption Options on Target Servers"
description: "Set Encryption Options on Target Servers"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Agent, encryption"
  - "target servers [SQL Server], encryption"
  - "multiserver environments [SQL Server], setting encryption options on target servers"
---
# Set Encryption Options on Target Servers
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

If you cannot use a certificate for Transport Layer Security (TLS), previously known as Secure Sockets Layer (SSL), encrypted communications between master servers and some or all of your target servers, but you want to encrypt the channel between them, configure the target server to use the level of security required.  
  
To configure the appropriate level of security required for a specific master server/target server communication channel, set the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\**\<*instance_name*>**\SQLServerAgent\MsxEncryptChannelOptions(REG_DWORD)** on the target server to one of the following values. The value of \<*instance_name*> is **MSSQL.**_n_. For example, **MSSQL.1** or **MSSQL.3**.  
  
|Value|Description|  
|---------|---------------|  
|**0**|Disables encryption between this target server and the master server. Choose this option only when the channel between the target server and master server is secured by another means.|  
|**1**|Enables encryption only between this target server and the master server, but no certificate validation is required.|  
|**2**|Enables full TLS encryption and certificate validation between this target server and the master server. This setting is the default. Unless you have specific reason to choose a different value, we recommend not changing it.|  
  
If **1** or **2** is specified, you must have TLS enabled on both the master and target servers. If **2** is specified, you must also have a properly signed certificate present on the master server.  
  
> [!CAUTION]  
> [!INCLUDE[ssNoteRegistry](../includes/ssnoteregistry-md.md)]  
  
## See Also  
[How to: Enable Encrypted Connections to the Database Engine (SQL Server Configuration Manager)](/sql/database-engine/configure-windows/configure-sql-server-encryption)
