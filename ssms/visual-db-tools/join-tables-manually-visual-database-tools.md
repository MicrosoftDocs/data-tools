---
title: Join Tables Manually
description: "Join tables manually (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "manual joins [SQL Server]"
  - "joins [SQL Server], manual"
  - "joins [SQL Server], creating"
---
# Join tables manually (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

When you add two (or more) tables to a query, the [Query and View Designer Tools (Visual Database Tools)](query-and-view-designer-tools-visual-database-tools.md) attempts to join them based on common data or on information stored in the database about how tables are related. For details, see [Join tables automatically (Visual Database Tools)](join-tables-automatically-visual-database-tools.md). However, if the Query and View Designer hasn't joined the tables automatically, or if you want to create additional join conditions between tables, you can join tables manually.

You can create joins based on comparisons between any two columns, not just columns that contain the same information. For example, if your database contains two tables, `titles` and `roysched`, you can compare values in the `ytd_sales` column of the `titles` table against the `lorange` and `hirange` columns in the `roysched` table. Creating this join would allow you to find titles for which the year-to-date sales fall between the low and high ranges for the royalty payments.

> [!TIP]  
> Joins work fastest if the columns in the join condition have been indexed. In some cases, joining on unindexed columns can result in a slow query.

## Manually join tables or table-structured objects

1. Add to the [Diagram pane (Visual Database Tools)](diagram-pane-visual-database-tools.md) the objects you want to join.

1. Drag the name of the join column in the first table or table-structured object and drop it onto the related column in the second table or table-structured object. You can't base a join on **text**, **ntext**, or i**mage** columns.

   > [!NOTE]  
   > The join columns must be of the same (or compatible) data types. For example, if the join column in the first table is a date, you must relate it to a date column in the second table. On the other hand, if the first join column is an integer, the related join column must also be of an integer data type, but it can be a different size. The Query and View Designer doesn't check the data types of the columns you use to create a join, but when you execute the query, the database displays an error if the data types aren't compatible.

1. If necessary, change the join operator; by default, the operator is an equal sign (`=`). For details, see [Modify join operators (Visual Database Tools)](modify-join-operators-visual-database-tools.md).

The Query and View Designer adds an `INNER JOIN` clause to the SQL statement in the [SQL Pane (Visual Database Tools)](sql-pane-visual-database-tools.md). You can change the type to an outer join. For details see [Create outer joins (Visual Database Tools)](create-outer-joins-visual-database-tools.md).

## Related content

- [Query with joins (Visual Database Tools)](query-with-joins-visual-database-tools.md)
