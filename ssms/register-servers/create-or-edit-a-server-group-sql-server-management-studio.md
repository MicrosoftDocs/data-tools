---
title: Create or Edit a Server Group
description: "Create or Edit a Server Group (SQL Server Management Studio)"
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mikeray
ms.date: 03/01/2017
ms.service: sql-server-management-studio
ms.topic: conceptual
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.editgroup.f1"
  - "sql13.swb.newgroup.f1"
helpviewer_keywords:
  - "Registered Servers [SQL Server], server groups"
  - "server groups [SQL Server]"
  - "groups [SQL Server], server"
---

# Create or Edit a Server Group (SQL Server Management Studio)

[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This topic describes how to organize the servers in Registered Servers in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by creating server groups, and placing the servers in the server groups. You can create server groups in Registered Servers at any time, or you can create server groups when you register servers.  

## <a name="SSMSProcedure"></a>

### To create a server group in Registered Servers  

1. In Registered Servers, click the server type on the Registered Servers toolbar. If Registered Servers is not visible, click **Registered Servers** on the **View** menu.  

2. Right-click a server or a server group, point to **New**, and then click **Server Group**.  

3. In the **New Server Group** dialog box, in the **Group name** list box, type a unique name for the server group. The server group name must be unique for the current location in the Registered Servers tree.

4. In the **Group description** list box, optionally type a friendly name that describes the server group, for example, "Finance Servers for Latin America."  

5. In the **Select a location for the new server group** box, click a location for the group, and then click **Save**.  

   > [!NOTE]
   > You can also create a new server group while you are registering a server by clicking **New Group**, and then completing the **New Group** dialog box.  

## See Also

[Register Servers](register-servers.md)
