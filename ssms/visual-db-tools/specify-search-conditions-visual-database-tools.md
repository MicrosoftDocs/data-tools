---
title: Specify Search Conditions
description: "Specify search conditions (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "choosing search criteria"
  - "search conditions [SQL Server], specifying"
  - "search criteria [SQL Server], specifying conditions"
---
# Specify search conditions (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can specify the data rows that appear in your query by specifying search conditions. For example, if you're querying an `employee` table, you can specify that you want to find only the employees who work in a particular region.

You specify search conditions using an expression. Most commonly the expression consists of an operator and a search value. For example, to find employees in a particular sales region, you might specify the following search criterion for the `region` column:

```sql
='UK'
```

> [!NOTE]  
> If you're working with multiple tables, the Query and View Designer examines each search condition to determine whether the comparison you're making results in a join. If so, the Query and View Designer automatically converts the search condition into a join. For more information, see [Join tables automatically (Visual Database Tools)](join-tables-automatically-visual-database-tools.md).

## Specify search conditions

1. If you haven't done so already, add the columns or expressions that you want to use within your search condition to the Criteria pane.

   If you're creating a Select query and don't want the search columns or expressions to appear in the query output, clear the **Output** column for each search column or expression to remove them as output columns.

1. Locate the row containing the data column or expression to search, and then in the **Filter** column, enter a search condition.

   > [!NOTE]  
   > If you don't enter an operator, the Query and View Designer automatically inserts the equality operator "=".

The Query and View Designer updates the SQL statement in the [SQL Pane (Visual Database Tools)](sql-pane-visual-database-tools.md) by adding or modifying the `WHERE` clause.

## Related content

- [Rules for entering search values (Visual Database Tools)](rules-for-entering-search-values-visual-database-tools.md)
- [Specify search criteria (Visual Database Tools)](specify-search-criteria-visual-database-tools.md)
