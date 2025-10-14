---
title: Create or Edit a Server Group
description: "Create or edit a server group (SQL Server Management Studio)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 07/08/2025
ms.service: sql-server-management-studio
ms.topic: how-to
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

# Create or edit a server group (SQL Server Management Studio)

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This article describes how to organize the servers in Registered Servers in SQL Server Management Studio (SSMS) by creating server groups, and placing the servers in the server groups. You can create server groups in Registered Servers at any time, or you can create server groups when you register servers.

## Create a server group in Registered Servers

1. In Registered Servers, select the server type on the Registered Servers toolbar. If Registered Servers isn't visible, select **Registered Servers** on the **View** menu.

1. Right-click a server or a server group, point to **New**, and then select **Server Group**.

1. In the **New Server Group** dialog box, in the **Group name** list box, type a unique name for the server group. The server group name must be unique for the current location in the Registered Servers tree.

1. In the **Group description** list box, optionally type a friendly name that describes the server group, for example, "Finance Servers for Latin America."

1. In the **Select a location for the new server group** box, select a location for the group, and then select **Save**.

   > [!NOTE]  
   > You can also create a new server group while you're registering a server by selecting **New Group**, and then completing the **New Group** dialog box.

## Related content

- [Registered Servers in SQL Server Management Studio](register-servers.md)
