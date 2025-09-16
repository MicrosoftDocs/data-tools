---
title: "SQL Server Options Page - Environment - Startup"
description: "Options (Environment - Startup page)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/15/2025
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
---

# Options (Environment - Startup page)

[!INCLUDE [SQL Server Azure SQL Database Azure SQL Managed Instance Synapse Analytics PDW Fabric SE Fabric DW Fabric SQL DB](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw-fabricse-fabricdw-fabricsqldb.md)]

Use the **Options** dialog box to configure SQL Server Management Studio startup actions, general window management options, and other general settings. On the **Tools** menu, select **Options**, expand the **Environment** folder, and then select **Startup**.

## UI element list

**At startup**

Select the action for SQL Server Management Studio to perform when it's started. The options are:

- **Open Object Explorer** prompts for a connection and then opens Object Explorer.

- **Open new query window** prompts for a connection and then opens SQL Query Editor.

- **Open Object Explorer and query window** prompts for a connection, then opens both Object Explorer and SQL Query Editor with that connection.

- **Open Object Explorer and Activity Monitor**

- **Open empty environment** opens SQL Server Management Studio without a SQL Query editor window and without connecting Object Explorer to a server.

**Hide system objects in Object Explorer**

Select this check box to remove the system databases, system tables, system views, and system stored procedures from tree view in Object Explorer. System functions and system data types aren't hidden. This option only applies to instances of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] and doesn't affect servers already connected in Object Explorer.

## Related content

- [Options (Environment - General Page)](options-environment-general-page.md)
