---
title: Specify Multiple Search Conditions for One Column
description: "Specify multiple search conditions for one column (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "search criteria [SQL Server], multiple conditions"
  - "multiple search conditions"
  - "search conditions [SQL Server], multiple"
  - "OR operator"
  - "AND, Criteria pane"
---
# Specify multiple search conditions for one column (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

In some instances, you might want to apply a number of search conditions to the same data column. For example, you might want to:

- Search for several different names in an `employee` table or for employees who are in different salary ranges. This type of search requires an `OR` condition.

- Search for a book title that both starts with the word "The" and contains the word "Cook." This type of search requires an `AND` condition.

> [!NOTE]  
> The information in this article applies to search conditions in both the `WHERE` and `HAVING` clauses of a query. The examples focus on creating `WHERE` clauses, but the principles apply to both types of search conditions.

To search for alternative values in the same data column, you specify an `OR` condition. To search for values that meet several conditions, you specify an `AND` condition.

## Specify an OR condition

Using an `OR` condition enables you to specify several alternative values to search for in a column. This option expands the scope of the search and can return more rows than searching for a single value.

> [!TIP]  
> You can often use the IN operator instead to search for multiple values in the same data column.

1. In the [Criteria Pane (Visual Database Tools)](criteria-pane-visual-database-tools.md), add the column to search.

1. In the **Filter** column for the data column you just added, specify the first condition.

1. In the **Or...** column for the same data column, specify the second condition.

The Query and View Designer creates a `WHERE` clause that contains an `OR` condition such as the following:

```sql
SELECT fname,
       lname
FROM employees
WHERE (salary < 30000)
      OR (salary > 100000);
```

## Specify an AND condition

Using an `AND` condition enables you to specify that values in a column must meet two (or more) conditions for the row to be included in the result set. This option narrows the scope of the search and usually returns fewer rows than searching for a single value.

> [!TIP]  
> If you're searching for a range of values, you can use the `BETWEEN` operator instead of linking two conditions with `AND`.

1. In the Criteria pane, add the column to search.

1. In the **Filter** column for the data column you just added, specify the first condition.

1. Add the same data column to the Criteria pane again, placing it in an empty row of the grid.

1. In the **Filter** column for the second instance of the data column, specify the second condition.

The Query Designer creates a `WHERE` clause that contains an `AND` condition such as the following:

```sql
SELECT title_id,
       title
FROM titles
WHERE (title LIKE '%Cook%')
      AND (title LIKE '%Recipe%');
```

## Related content

- [Conventions for combining search conditions in the Criteria pane (Visual Database Tools)](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md)
- [Specify search criteria (Visual Database Tools)](specify-search-criteria-visual-database-tools.md)
