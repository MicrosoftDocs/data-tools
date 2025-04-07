---
title: Work with Tables in Database Diagram
description: "Work with Tables in Database Diagram (Visual Database Tools). Learn how to modify and create database tables using Table Designer or Database Diagram Designer."
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: conceptual
ms.collection:
  - data-tools
helpviewer_keywords:
  - "database diagrams [SQL Server], tables"
  - "Table Designer, database diagrams"
  - "tables [SQL Server], database diagrams"
  - "database diagrams [SQL Server], Table Designer"
---

# Work with Tables in Database Diagram (Visual Database Tools)

[!INCLUDE[SQL Server Azure SQL Database PDW](../includes/applies-to-version/sql-asdb-asdbmi-pdw.md)]

You can modify and create database tables in either Table Designer or Database Diagram Designer.  
  
> [!NOTE]  
> If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO). When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table. You cannot drop published objects, therefore the schema change will fail.  
  
## In This Section

[Add Tables to Diagrams &#40;Visual Database Tools&#41;](add-tables-to-diagrams-visual-database-tools.md)  
  
[Add Related Tables to Diagrams &#40;Visual Database Tools&#41;](add-related-tables-to-diagrams-visual-database-tools.md)  
  
[Save Selected Tables on a Diagram &#40;Visual Database Tools&#41;](save-selected-tables-on-a-diagram-visual-database-tools.md)  
  
[Copy Tables from One Database Diagrams to Another &#40;Visual Database Tools&#41;](copy-tables-from-one-database-diagrams-to-another-visual-database-tools.md)  
  
[Remove Tables from Database Diagrams &#40;Visual Database Tools&#41;](remove-tables-from-database-diagrams-visual-database-tools.md)  
  
[Map Many-to-Many Relationships &#40;Visual Database Tools&#41;](map-many-to-many-relationships-visual-database-tools.md)  
  
[Draw Reflexive Relationships &#40;Visual Database Tools&#41;](draw-reflexive-relationships-visual-database-tools.md)
