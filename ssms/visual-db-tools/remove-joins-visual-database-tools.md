---
title: Remove Joins
description: "Remove joins (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "removing joins"
  - "joins [SQL Server], removing"
  - "deleting joins"
---
# Remove joins (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

If you don't want tables to be joined via an inner join or an outer join, you can remove the join between them. For example, you might remove a join that the [Query and View Designer Tools (Visual Database Tools)](query-and-view-designer-tools-visual-database-tools.md) has been created automatically between two tables.

> [!NOTE]  
> Removing a join from a query doesn't alter the underlying relationship in the database.

If two joined tables are part of your query and you remove all join conditions between them, the resulting query becomes the product of both tables - that is, it becomes a `CROSS JOIN`.

## Remove a join

- In the [Diagram pane (Visual Database Tools)](diagram-pane-visual-database-tools.md), select the join line for the join to remove, and then press the `DELETE` key. You can select and delete multiple join lines at one time.

The Query and View Designer removes the join line and alters the statement in the [SQL Pane (Visual Database Tools)](sql-pane-visual-database-tools.md).

## Related content

- [Join tables automatically (Visual Database Tools)](join-tables-automatically-visual-database-tools.md)
- [Join tables manually (Visual Database Tools)](join-tables-manually-visual-database-tools.md)
- [Query with joins (Visual Database Tools)](query-with-joins-visual-database-tools.md)
