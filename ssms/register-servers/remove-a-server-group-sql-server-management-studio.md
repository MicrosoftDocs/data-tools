---
title: Remove a Server Group
description: Remove a server group in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "removing server groups"
  - "Registered Servers [SQL Server], server groups"
  - "server groups [SQL Server]"
  - "deleting server groups"
  - "groups [SQL Server], server"
---

# Remove a server group in SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This article describes how to remove a server group in Registered Servers in SQL Server Management Studio (SSMS). You can delete a server group at any time. If the server group isn't empty, any servers or server groups contained in the deleted server group are also deleted.

Before deleting a server group, move any servers or server groups that you want to retain to a new server group.

If the Registered Servers tool window isn't visible in SSMS, select **View** > **Registered Servers**, or type **Ctrl**+**Alt**+**G**.

## Remove a server group

1. In the Registered Servers pane, find the server group you want to remove, right-click, and select **Delete**.
1. In the **Delete Confirmation** dialog box, select **Yes**.

## Related content

- [Move a registered server or registered server group in SQL Server Management Studio](move-a-registered-server-or-registered-server-group.md)
