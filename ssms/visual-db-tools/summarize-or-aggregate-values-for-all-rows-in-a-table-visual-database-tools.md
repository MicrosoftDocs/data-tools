---
title: Summarize or Aggregate Values for All Rows in a Table
description: "Summarize or Aggregate Values for All Rows in a Table (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "summarizing query results"
  - "aggregate functions [SQL Server], summarizing query results"
---
# Summarize or aggregate values for all rows in a table (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

## Aggregate function

Using an aggregate function, you can create a summary for all the values in a table. For example, you can create a query such as the following to display the total price for all books in the `titles` table:

```sql
SELECT SUM(price)
FROM titles;
```

Create multiple aggregations in the same query by using aggregate functions with more than one column. For example, you can create a query that calculates the total of the `price` column and the average of the `discount` column.

You can aggregate the same column in different ways (such as totaling, counting, and averaging) in the same query. For example, the following query averages and summarizes the `price` column from the `titles` table:

```sql
SELECT AVG(price),
       SUM(price)
FROM titles;
```

If you add a search condition, you can aggregate the subset of rows that meet that condition.

> [!NOTE]  
> You can also count all the rows in the table or the ones that meet a specific condition. For details, see [Count rows in a table (Visual Database Tools)](count-rows-in-a-table-visual-database-tools.md).

When you create a single aggregation value for all rows in a table, you display only the aggregate values themselves. For example, if you're totaling the value of the `price` column of the `titles` table, you wouldn't also display individual titles, publisher names, and so on.

> [!NOTE]  
> If you're subtotaling - that is, creating groups - you can display column values for each group. For details, see [Group Rows in Query Results (Visual Database Tools)](group-rows-in-query-results-visual-database-tools.md).

## Aggregate values for all rows

1. Be sure the table you want to aggregate is already present in the Diagram pane.

1. Right-click the background of the Diagram pane, then choose **Group By** from the shortcut menu. The [Query and View Designer Tools (Visual Database Tools)](query-and-view-designer-tools-visual-database-tools.md) adds a **Group By** column to the grid in the Criteria pane.

1. Add the column you want to aggregate to the Criteria pane. Be sure that the column is marked for output.

   The Query and View Designer automatically assigns a column alias to the column you're summarizing. You can replace this alias with a more meaningful one. For details, see [Create column aliases (Visual Database Tools)](create-column-aliases-visual-database-tools.md).

1. In the **Group By** grid column, select the appropriate aggregate function, such as: **Sum**, **Avg**, **Min**, **Max**, **Count**. If you want to aggregate only unique rows in the result set, choose an aggregate function with the `DISTINCT` options, such as **Min Distinct**. Don't choose **Group By**, **Expression**, or **Where**, because those options don't apply when you're aggregating all rows.

   The Query and View Designer replaces the column name in the statement in the [SQL Pane (Visual Database Tools)](sql-pane-visual-database-tools.md) with the aggregate function that you specify. For example, the SQL statement might look like this:

   ```sql
   SELECT SUM(price)
   FROM titles;
   ```

1. If you want to create more than one aggregation in the query, repeat steps 3 and 4.

   When you add another column to the query output list or order by list, the Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid. Select the appropriate aggregate function.

1. Add search conditions, if any, to specify the subset of rows you want to summarize.

When you execute the query, the Results pane displays the aggregations that you specified.

> [!NOTE]  
> The Query and View Designer maintains aggregate functions as part of the SQL statement in the SQL pane until you explicitly turn off Group By mode. Therefore, if you modify your query by changing its type or by changing which tables or table-valued objects are present in the Diagram pane, the resulting query might include invalid aggregate functions.

## Related content

- [Sort and group query results (Visual Database Tools)](sort-and-group-query-results-visual-database-tools.md)
- [Summarize query results (Visual Database Tools)](summarize-query-results-visual-database-tools.md)
