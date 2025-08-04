---
title: Create Outer Joins
description: "Create Outer Joins (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "outer joins"
  - "joins [SQL Server], outer"
---
# Create outer joins (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

By default, the [Query and View Designer Tools (Visual Database Tools)](query-and-view-designer-tools-visual-database-tools.md) creates an inner join between tables. Inner joins eliminate the rows that don't match with a row from the other table. Outer joins, however, return all rows from at least one of the tables or views mentioned in the `FROM` clause, as long as those rows meet any `WHERE` or `HAVING` search conditions. If you want to include data rows in the result set that don't have a match in the joined table, you can create an outer join.

When you create an outer join, the order in which tables appear in the SQL statement (as reflected in the SQL pane) is significant. The first table you add becomes the "left" table and the second table becomes the "right" table. (The actual order in which the tables appear in the [Diagram pane (Visual Database Tools)](diagram-pane-visual-database-tools.md) isn't significant.) When you specify a left or right outer join, you're referring to the order in which the tables were added to the query and to the order in which they appear in the SQL statement in the [SQL Pane (Visual Database Tools)](sql-pane-visual-database-tools.md).

## Create an outer join

1. Create the join, either automatically or manually. For details, see [Join tables automatically (Visual Database Tools)](join-tables-automatically-visual-database-tools.md) or [Join tables manually (Visual Database Tools)](join-tables-manually-visual-database-tools.md).

1. Select the join line in the Diagram pane, and then from the **Query Designer** menu, choose **Select All Rows from \<tablename\>**, selecting the command that includes the table whose extra rows you want to include.

   - Choose the first table to create a left outer join.
   - Choose the second table to create a right outer join.
   - Choose both tables to create a full outer join.

When you specify an outer join, the Query and View Designer modifies the join line to indicate an outer join.

In addition, the Query and View Designer modifies the SQL statement in the SQL pane to reflect the change in join type, as shown in the following statement:

```sql
SELECT employee.job_id,
       employee.emp_id,
       employee.fname,
       employee.minit,
       jobs.job_desc
FROM employee
     LEFT OUTER JOIN jobs
         ON employee.job_id = jobs.job_id;
```

Because an outer join includes unmatched rows, you can use it to find rows that violate foreign key constraints. To do so, you create an outer join and then add a search condition to find rows in which the primary key column of the rightmost table is null. For example, the following outer join finds rows in the `employee` table that don't have corresponding rows in the `jobs` table:

```sql
SELECT employee.emp_id,
       employee.job_id
FROM employee
     LEFT OUTER JOIN jobs
         ON employee.job_id = jobs.job_id
WHERE (jobs.job_id IS NULL);
```

## Related content

- [Query with joins (Visual Database Tools)](query-with-joins-visual-database-tools.md)
