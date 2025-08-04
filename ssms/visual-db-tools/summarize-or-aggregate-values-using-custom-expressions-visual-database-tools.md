---
title: Summarize or Aggregate Values Using Custom Expressions
description: "Summarize or aggregate values using custom expressions (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "summarizing query results"
  - "custom expressions to aggregate values [SQL Server]"
---
# Summarize or aggregate values using custom expressions (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

In addition to using aggregate functions to aggregate data, you can create custom expressions to produce aggregate values. You can use custom expressions in place of aggregate functions anywhere in an aggregate query.

For example, in the `titles` table you might want to create a query that shows not just the average price, but what the average price would be if it were discounted.

You can't include an expression that is based on calculations involving only individual rows in the table; the expression must be based on an aggregate value, because only the aggregate values are available at the time the expression is calculated.

## Specify a custom expression for a summary value

1. Specify the groups for your query. For details, see [Group Rows in Query Results (Visual Database Tools)](group-rows-in-query-results-visual-database-tools.md).

1. Move to a blank row of the Criteria pane, and then type the expression in the **Columns** column.

   The [Query and View Designer Tools (Visual Database Tools)](query-and-view-designer-tools-visual-database-tools.md) automatically assigns a column alias to the expression to create a useful column heading in query output. For more details, see [Create column aliases (Visual Database Tools)](create-column-aliases-visual-database-tools.md).

1. In the **Group By** column for the expression, select **Expression**.

1. Run the query.

## Related content

- [Sort and group query results (Visual Database Tools)](sort-and-group-query-results-visual-database-tools.md)
- [Summarize query results (Visual Database Tools)](summarize-query-results-visual-database-tools.md)
