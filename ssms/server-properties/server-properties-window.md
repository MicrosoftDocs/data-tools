---
title: Server Properties Window
titleSuffix: SQL Server Management Studio
description: View and modify properties of a connected SQL Server instance by using the Server Properties window in SQL Server Management Studio.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mbarickman
ms.date: 09/03/2026
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
helpviewer_keywords:
  - "viewing server properties"
  - "Server Properties window [SQL Server Management Studio]"
  - "modifying server properties"
ai-usage: ai-assisted
---
# Server Properties window in SQL Server Management Studio

[!INCLUDE [sql-asdbmi](../includes/applies-to-version/sql-asdbmi.md)]

Use the **Server Properties** window in [!INCLUDE [ssmanstudiofull-md](../includes/ssmanstudiofull-md.md)] to view and modify configuration options for a connected [!INCLUDE [ssdenoversion-md](../includes/ssdenoversion-md.md)] instance.

## Open the Server Properties window

In **Object Explorer**, right-click a server and select **Properties**.

## Configured and running values

On pages where you can modify server configuration options, you might see the following display options:

| Option | Description |
| --- | --- |
| **Configured values** | Shows the configured values for the options on the page. If you change these values, select **Running values** to see whether the changes took effect. If they didn't, the [!INCLUDE [ssde-md](../includes/ssde-md.md)] instance must be restarted first. |
| **Running values** | Shows the currently running values for the options on the page. These values are read-only. |

## Server property pages

The **Server Properties** window contains the following pages:

| Page | Description |
| --- | --- |
| [General](general-page.md) | Read-only information about the server instance, such as name, version, operating system, and collation. |
| [Memory](memory-page.md) | Minimum and maximum server memory, index creation memory, and minimum memory per query. |
| [Processors](processors-page.md) | Processor and I/O affinity settings, and maximum worker threads. |
| [Security](security-page.md) | Server authentication mode, login auditing, server proxy account, and other security options. |
| [Connections](connections-page.md) | Maximum concurrent connections, default connection options, and remote server connections. |
| [Database Settings](database-settings-page.md) | Default index fill factor, backup options, recovery interval, and default file locations. |
| [Advanced](advanced-page.md) | Miscellaneous settings, containment, FILESTREAM, network, and parallelism options. |
| [Permissions](permissions-page.md) | Server-level permissions for logins and roles. |

For more information about how to modify server properties with Transact-SQL (T-SQL) or SQL Server Configuration Manager, see [View or change server properties (SQL Server)](/sql/database-engine/configure-windows/view-or-change-server-properties-sql-server).

## Related content

- [Property pages in SQL Server Management Studio](../property-pages-in-sql-server-management-studio.md)
- [General user interface elements](../general-user-interface-elements.md)
- [Properties window (SSMS)](../properties-window-management-studio.md)
