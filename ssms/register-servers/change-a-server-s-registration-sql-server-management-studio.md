---
title: "Change a Server's Registration"
description: Overview of changing a server's registration in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---

# Change a server's registration in SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This article describes how to change a server's registration in SQL Server Management Studio (SSMS). You can change the connection information for a registered server at any time. If the Registered Servers tool window isn't visible in SSMS, select **View** > **Registered Servers**, or type **Ctrl**+**Alt**+**G**.

## Change a server's registration (local server groups)

1. Within the Local Server Groups, find the registered server to modify.

1. Right-click on the registered server and select **Properties...**.

1. In the **Edit Server Registration Properties** dialog box, modify the server, login information, connection properties, or registered server name, and select **Save**.

## Change a server's registration (Central Management Servers)

1. Within Central Management Servers, find the registered server to modify.

1. Right-click on the registered server and select **Properties...**.

1. In the **Server Registration** dialog box, modify the server, registered server name, or description, and select **Save**.

## Related content

- [Registered Servers in SQL Server Management Studio](register-servers.md)
