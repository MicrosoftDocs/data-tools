---
title: Remove Joins
description: "Remove Joins (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "removing joins"
  - "joins [SQL Server], removing"
  - "deleting joins"
---
# Remove Joins (Visual Database Tools)
[!INCLUDE[SQL Server](../includes/applies-to-version/sqlserver.md)]
If you do not want tables to be joined via an inner join or an outer join, you can remove the join between them. For example, you might remove a join that the [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) has been created automatically between two tables.  
  
> [!NOTE]  
> Removing a join from a query does not alter the underlying relationship in the database.  
  
If two joined tables are part of your query and you remove all join conditions between them, the resulting query becomes the product of both tables - that is, it becomes a CROSS JOIN.  
  
### To remove a join  
  
-   In the [Diagram pane](diagram-pane-visual-database-tools.md), select the join line for the join to remove, and then press the DELETE key. You can select and delete multiple join lines at one time.  
  
The Query and View Designer removes the join line and alters the statement in the [SQL pane](sql-pane-visual-database-tools.md).  
  
## See Also  
[Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md)  
[Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md)  
[Query with Joins &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md)  
  
