---
title: Move a Registered Server or Server Group
description: Overview of how to move a registered server or registered server group in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "moving registered server or server group"
  - "Registered Servers [SQL Server], server groups"
  - "server groups [SQL Server]"
  - "Registered Servers [SQL Server], moving server or server group"
  - "groups [SQL Server], server"
---

# Move a registered server or registered server group in SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This article describes how to organize the servers in Registered Servers by moving a registered server or server group. A server group can contain registered servers, or other server groups. Both servers and server groups can be moved from one server group to another.

If the Registered Servers tool window isn't visible in SQL Server Management Studio (SSMS), select **View** > **Registered Servers**, or type **Ctrl**+**Alt**+**G**.

## Move a registered server or server group

1. Within Local Server Groups or Central Management Servers, find the registered server or server group to move.

1. Right-click on the server or server group, and then select **Tasks** > **Move To...**.

1. In the **Move Server Registration** dialog box, expand the list of server groups, select the node where you want the server or server group to exist, and then select **OK**.

## Related content

- [Registered Servers in SQL Server Management Studio](register-servers.md)
- [Create or edit a server group (SQL Server Management Studio)](create-or-edit-a-server-group-sql-server-management-studio.md)
