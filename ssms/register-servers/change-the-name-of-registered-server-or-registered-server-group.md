---
title: Change the Name of a Registered Server or Server Group
description: Overview of changing the name of a registered server or registered server group in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---

# Change the name of a registered server or registered server group in SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This article describes how to change the name of a registered server or server group using SQL Server Management Studio (SSMS). The name can be changed at any time. Changing the name of a server in Registered Servers only changes how the name is displayed. To connect to a different server, you must edit the connection properties of the registered server.

If the Registered Servers tool window isn't visible in SSMS, select **View** > **Registered Servers**, or type **Ctrl**+**Alt**+**G**.

## Change the name of a server

1. Within Local Server Groups or Central Management Servers, find the registered server to modify.
1. Right-click on the registered server and select **Properties...**.
1. In the **Registered server name** text box, enter the new name for the server registration, then select **Save**.

## Change the name of a server group

1. Within Local Server Groups or Central Management Servers, find the server group to modify.
1. Right-click on the server group and select **Properties...** to open the **Edit Server Group Properties** dialog.
1. In the **Group name** text box, enter the new name for the server group, then select **Save**.

## Related content

- [Change a server's registration in SQL Server Management Studio](change-a-server-s-registration-sql-server-management-studio.md)
