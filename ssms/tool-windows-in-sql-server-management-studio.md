---
title: Tool Windows in SQL Server Management Studio
description: Tool windows in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.date: 07/08/2025
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Management Studio [SQL Server], tool windows"
  - "tool windows [SQL Server Management Studio]"
---
# Tool windows in SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

SQL Server Management Studio (SSMS) provides many powerful tool windows for selected phases of development and administration. Some tools can be used on any [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] component, and others are only available for certain components. The following table identifies the tool windows in SSMS.

| Tool | Purpose |
| --- | --- |
| [Object Explorer](object/object-explorer.md) | Browse servers, create and locate objects, manage data sources, and view logs. This tool is accessed from the **View** menu. |
| [Registered Servers](register-servers/register-servers.md) | Store and organize server information for your local instance of SSMS, or connect to a Central Management Server to access a centralized list of servers in the environment. |
| [Solution Explorer](solution/solution-explorer.md) | Store and organize scripts and related connection information in projects called [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] Scripts. You can store several [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] Scripts as Solutions and use source control to manage scripts as they evolve over time. This tool is accessed from the **View** menu. |
| [Template Explorer](template/template-explorer.md) | Create queries based on existing templates. You can also create your custom queries or alter the existing templates to fit your scenarios. This tool is accessed from the **View** menu. |
| [User Assistance](user-assistance-in-sql-server-management-studio.md) | Show a list of related Help articles as you select a component or type code. |

The tools in SQL Server Management Studio work together.

For example, you can:

- Register a server from Object Explorer.
- Open a Query Editor window connected to a specific database from Object Explorer.

## Related content

- [What is SQL Server Management Studio (SSMS)?](sql-server-management-studio-ssms.md)
