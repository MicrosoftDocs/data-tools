---
title: Work with Tables in Database Diagram
description: Learn how to modify and create database tables using Table Designer or Database Diagram Designer.
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "database diagrams [SQL Server], tables"
  - "Table Designer, database diagrams"
  - "tables [SQL Server], database diagrams"
  - "database diagrams [SQL Server], Table Designer"
---

# Work with tables in database diagrams (Visual Database Tools)

[!INCLUDE [SQL Server Azure SQL Database PDW](../includes/applies-to-version/sql-asdb-asdbmi-pdw.md)]

You can modify and create database tables in either Table Designer or Database Diagram Designer.

> [!NOTE]  
> If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO). When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table. You can't drop published objects, therefore the schema change fails.

## In this section

- [Add tables to diagrams (Visual Database Tools)](add-tables-to-diagrams-visual-database-tools.md)
- [Add related tables to diagrams (Visual Database Tools)](add-related-tables-to-diagrams-visual-database-tools.md)
- [Save selected tables on a diagram (Visual Database Tools)](save-selected-tables-on-a-diagram-visual-database-tools.md)
- [Copy tables from one database diagram to another (Visual Database Tools)](copy-tables-from-one-database-diagrams-to-another-visual-database-tools.md)
- [Remove tables from database diagrams (Visual Database Tools)](remove-tables-from-database-diagrams-visual-database-tools.md)
- [Map many-to-many relationships (Visual Database Tools)](map-many-to-many-relationships-visual-database-tools.md)
- [Draw reflexive relationships (Visual Database Tools)](draw-reflexive-relationships-visual-database-tools.md)
