---
title: Combine Conditions When OR Has Precedence
description: "Combine conditions when OR has precedence (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "search conditions [SQL Server], combining"
  - "precedence [SQL Server], Criteria pane"
  - "search criteria [SQL Server], combining conditions"
  - "combining search conditions"
  - "OR operator"
---
# Combine conditions when OR has precedence (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

To link conditions with `OR` and give them precedence over conditions linked with `AND`, you must repeat the `AND` condition for each `OR` condition.

For example, imagine that you want to find all employees who have been with the company more than five years and have lower-level jobs or are retired. This query requires three conditions, a single condition linked to two additional conditions with `AND`:

- Employees with a hire date earlier than five years ago, and

- Employees with a job level of 100 or whose status is "R" (for retired).

The following procedure illustrates how to create this type of query in the Criteria pane.

## Combine conditions when OR has precedence

1. In the [Criteria Pane (Visual Database Tools)](criteria-pane-visual-database-tools.md), add the data columns you want to search. If you want to search the same column using two or more conditions linked with `AND`, you must add the data column name to the grid once for each value you want to search.

1. Create the conditions to be linked with `OR` by entering the first one into the **Filter** grid column and the second (and subsequent ones) into separate **Or...** columns. For example, to link conditions with `OR` that search the `job_lvl` and `status` columns, enter `= 100` in the **Filter** column for `job_lvl` and `= 'R'` in the **Or...** column for `status`.

   Entering these values in the grid produces the following `WHERE` clause in the statement in the SQL pane:

   ```sql
   WHERE (job_lvl = 100) OR (status = 'R')
   ```

1. Create the `AND` condition by entering it once for each `OR` condition. Place each entry in the same grid column as the `OR` condition it corresponds to. For example, to add an `AND` condition that searches the `hire_date` column and applies to both `OR` conditions, enter `< '1/1/91'` in both the Criteria column and the **Or...** column.

   Entering these values in the grid produces the following `WHERE` clause in the statement in the SQL pane:

   ```sql
   WHERE (job_lvl = 100) AND
     (hire_date < '01/01/91') OR
     (status = 'R') AND
     (hire_date < '01/01/91')
   ```

   > [!TIP]  
   > You can repeat an `AND` condition by adding it once, and then using the **Cut** and **Paste** commands from the **Edit** menu to repeat it for other `OR` conditions.

The `WHERE` clause created by the Query and View Designer is equivalent to the following `WHERE` clause, which uses parentheses to specify the precedence of `OR` over `AND`:

```sql
WHERE (job_lvl = 100 OR status = 'R') AND
   (hire_date < '01/01/91')
```

> [!NOTE]  
> If you enter the search conditions in the format shown immediately above in the [SQL Pane (Visual Database Tools)](sql-pane-visual-database-tools.md), but then make a change to the query in the Diagram or Criteria panes, the Query and View Designer recreates the SQL statement to match the form with the `AND` condition explicitly distributed to both `OR` conditions.

## Related content

- [Conventions for combining search conditions in the Criteria pane (Visual Database Tools)](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md)
- [Specify search criteria (Visual Database Tools)](specify-search-criteria-visual-database-tools.md)
