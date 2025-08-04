---
title: Sort in Ascending or Descending Order
description: "Sort in ascending or descending order (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "descending sorts"
  - "ascending sorts"
---
# Sort in ascending or descending order (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can sort query results in ascending or descending order on one or more of the columns in the result set by using the **ASC** or **DESC** keywords with the `ORDER BY` clause.

> [!NOTE]  
> The sort order is determined in part by the column's collation sequence. You can change the collation sequence in the Collation dialog box.

The following procedure assumes that you have a query open in Query and View Designer that uses the `ORDER BY` clause to sort one or more columns.

## Specify or change the order in which results are sorted

1. In the [Criteria Pane (Visual Database Tools)](criteria-pane-visual-database-tools.md), select the **Sort Type** field for the column that you want to reorder.

1. Choose **Ascending** or **Descending** to specify the sort order for the column.

As you work in the Criteria pane, your query's `UNION` clause changes to match your most recent actions.

> [!NOTE]  
> When sorting results by more than one column, specify the order in which columns are searched relative to each other by using the Sort Order column. For more information, see [Sort multiple columns in queries (Visual Database Tools)](sort-multiple-columns-in-queries-visual-database-tools.md).

## Related content

- [Sort and group query results (Visual Database Tools)](sort-and-group-query-results-visual-database-tools.md)
- [Summarize query results (Visual Database Tools)](summarize-query-results-visual-database-tools.md)
- [Design queries and views how-to articles (Visual Database Tools)](design-queries-and-views-how-to-topics-visual-database-tools.md)
