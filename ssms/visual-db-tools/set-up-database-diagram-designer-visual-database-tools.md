---
title: Set up Database Diagram Designer
description: "Set up Database Diagram Designer (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
f1_keywords:
  - "vdt.diagnostic.InstallSqlDiagramSupport"
helpviewer_keywords:
  - "Database Diagram Designer"
  - "database diagrams [SQL Server], Database Diagram Designer"
  - "diagrams [SQL Server], Database Diagram Designer"
---
# Set up Database Diagram Designer (Visual Database Tools)

[!INCLUDE [SQL Server Azure SQL Database PDW](../includes/applies-to-version/sql-asdb-asdbmi-pdw.md)]

To use Database Diagram Designer, it must first be set up by a member of the **db_owner** role to control access to diagrams.

## Set up database diagramming

1. From Object Explorer, expand a database node.

1. Expand the Database Diagrams node under the database connection.

1. Select **Yes** when prompted if you want to set up database diagramming.

   > [!NOTE]  
   > This step creates the database diagram table, system stored procedures, and a system function on the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] database.

1. Visual Studio creates the following objects on the instance of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)]:

   - `sysdiagrams` table
   - `sp_alterdiagram` stored procedure
   - `sp_creatediagram` stored procedure
   - `sp_dropdiagram` stored procedure
   - `sp_renamediagram` stored procedure
   - `fn_diagramobjects` function
   - `sp_helpdiagrams` stored procedure
   - `sp_helpdiagramsdefinition` stored procedure
   - `sp_upgraddiagrams` stored procedure

## Related content

- [Understand database diagram ownership (Visual Database Tools)](understand-database-diagram-ownership-visual-database-tools.md)
- [Upgrade database diagrams from previous editions (Visual Database Tools)](upgrade-database-diagrams-from-previous-editions-visual-database-tools.md)
- [ALTER AUTHORIZATION (Transact-SQL)](/sql/t-sql/statements/alter-authorization-transact-sql)
