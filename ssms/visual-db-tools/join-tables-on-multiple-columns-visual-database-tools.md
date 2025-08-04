---
title: Join Tables on Multiple Columns
description: "Join Tables on Multiple Columns (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "multiple column joins"
  - "joins [SQL Server], multiple columns"
---
# Join tables on multiple columns (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can join tables with multiple columns. That is, you can create a query that matches rows from the two tables only if they satisfy multiple conditions. If the database contains a relationship matching multiple foreign-key columns in one table to a multicolumn primary key in the other table, you can use this relationship to create a multicolumn join. For details, see [Join tables automatically (Visual Database Tools)](join-tables-automatically-visual-database-tools.md).

Even if the database contains no multi-column foreign-key relationship, you can create the join manually.

## Manually create a multicolumn join

1. Add to the [Diagram pane (Visual Database Tools)](diagram-pane-visual-database-tools.md) the tables you want to join.

1. Drag the name of the first join column in the first table window and drop it onto the related column in the second table window. You can't base a join on text, ntext, or image columns.

   > [!NOTE]  
   > In general, the join columns must be of the same (or compatible) data types. For example, if the join column in the first table is a date, you must relate it to a date column in the second table. On the other hand, if the first join column is an integer, the related join column must also be of an integer data type, but it can be a different size. However, there might be cases where implicit data type conversions can join seemingly incompatible columns.
   >
   > The [Query and View Designer Tools (Visual Database Tools)](query-and-view-designer-tools-visual-database-tools.md) don't check the data types of the columns you use to create a join, but when you execute the query, the database displays an error if the data types aren't compatible.

1. Drag the name of the second join column in the first table window and drop it onto the related column in the second table window.

1. Repeat step 3 for each additional pair of join columns in the two tables.

1. Run the query.

## Related content

- [Query with joins (Visual Database Tools)](query-with-joins-visual-database-tools.md)
