---
title: Count Rows in a Table
description: "Count rows in a table (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "totals [SQL Server], row counts"
  - "row counts [SQL Server]"
  - "column values [SQL Server]"
  - "number of rows"
  - "number of values"
  - "counting rows"
---
# Count rows in a table (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can count rows in a table to determine:

- The total number of rows in a table, for example, a count of all the books in a `titles` table.

- The number of rows in a table that meet a specific condition, for example, the number of books by one publisher in a `titles` table.

- The number of values in a particular column.

When you count values in a column, nulls aren't included in the count. For example, you might count the number of books in a `titles` table that have values in the `advance` column. By default, the count includes all values, not just unique values.

The procedures for all three types of counts are similar.

## Count all the rows in a table

1. Be sure the table you want to summarize is already present in the Diagram pane.

1. Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu. The [Query and View Designer Tools (Visual Database Tools)](query-and-view-designer-tools-visual-database-tools.md) adds a **Group By** column to the grid in the Criteria pane.

1. Select **&#42; (All Columns)** in the rectangle representing the table or table-valued object.

   The Query and View Designer automatically fills the term **Count** into the **Group By** column in the Criteria pane and assigns a column alias to the column you're summarizing. You can replace this automatically generated alias with a more meaningful one. For more details, see [Create column aliases (Visual Database Tools)](create-column-aliases-visual-database-tools.md).

1. Run the query.

## Count all the rows that meet a condition

1. Be sure the table you want to summarize is already present in the Diagram pane.

1. Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu. The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.

1. Select **&#42;(All Columns)** in the rectangle representing the table or table-structured object.

   The Query and View Designer automatically fills the term **Count** into the **Group By** column in the Criteria pane and assigns a column alias to the column you're summarizing. To create a more useful column heading in query output, see [Create column aliases (Visual Database Tools)](create-column-aliases-visual-database-tools.md).

1. Add the data column that you want to search, and then clear the check box in the **Output** column.

   The Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.

1. Change **Group By** in the **Group By** column to **Where**.

1. In the **Filter** column for the data column to search, enter the search condition.

1. Run the query.

## Count the values in a column

1. Be sure the table you want to summarize is already present in the Diagram pane.

1. Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu. The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.

1. Add the column that you want to count to the Criteria pane.

   The Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.

1. Change **Group By** in the **Group By** column to **Count**.

   > [!NOTE]  
   > To count only unique values, choose **Count Distinct**.

1. Run the query.

## Related content

- [Sort and group query results (Visual Database Tools)](sort-and-group-query-results-visual-database-tools.md)
- [Summarize query results (Visual Database Tools)](summarize-query-results-visual-database-tools.md)
