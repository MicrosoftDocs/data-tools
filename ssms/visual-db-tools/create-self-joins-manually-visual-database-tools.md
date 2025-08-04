---
title: Create Self-Joins Manually
description: "Create self-joins manually (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "self-joins"
  - "manual joins [SQL Server]"
  - "joins [SQL Server], self"
---
# Create self-joins manually (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can join a table to itself even if the table doesn't have a reflexive relationship in the database. For example, you can use a self-join to find pairs of authors living in the same city.

As with any join, a self-join requires at least two tables. The difference is that, instead of adding a second table to the query, you add a second instance of the same table. That way, you can compare a column in the first instance of the table to the same column in the second instance, which allows you to compare the values in a column to each other. The [Query and View Designer Tools (Visual Database Tools)](query-and-view-designer-tools-visual-database-tools.md) assigns an alias to the second instance of the table.

For example, if you're creating a self-join to find all pairs of authors within Berkeley, you compare the `city` column in the first instance of the table against the `city` column in the second instance. The resulting query might look like the following:

```sql
SELECT authors.au_fname,
       authors.au_lname,
       authors1.au_fname AS Expr2,
       authors1.au_lname AS Expr3
FROM authors
     INNER JOIN authors AS authors1
         ON authors.city = authors1.city
WHERE authors.city = 'Berkeley';
```

Creating a self-join often requires multiple join conditions. To understand why, consider the result of the preceding query:

```output
Cheryl Carson       Cheryl Carson
Abraham Bennet      Abraham Bennet
Cheryl Carson       Abraham Bennet
Abraham Bennet      Cheryl Carson
```

The first row is useless; it indicates that Cheryl Carson lives in the same city as Cheryl Carson. The second row is equally useless. To eliminate this useless data, you add another condition retaining only those result rows in which the two author names describe different authors. The resulting query might look like this:

```sql
SELECT authors.au_fname,
       authors.au_lname,
       authors1.au_fname AS Expr2,
       authors1.au_lname AS Expr3
FROM authors
     INNER JOIN authors AS authors1
         ON authors.city = authors1.city
        AND authors.au_id <> authors1.au_id
WHERE authors.city = 'Berkeley';
```

The result set is improved:

```output
Cheryl Carson       Abraham Bennet
Abraham Bennet      Cheryl Carson
```

But the two result rows are redundant. The first says Carson lives in the same city as Bennet, and the second says the Bennet lives in the same city as Carson. To eliminate this redundancy, you can alter the second join condition from "not equals" to "less than." The resulting query might look like this:

```sql
SELECT authors.au_fname,
       authors.au_lname,
       authors1.au_fname AS Expr2,
       authors1.au_lname AS Expr3
FROM authors
     INNER JOIN authors AS authors1
         ON authors.city = authors1.city
        AND authors.au_id < authors1.au_id
WHERE authors.city = 'Berkeley';
```

And the result set looks like this:

```output
Cheryl Carson       Abraham Bennet
```

## Create a self-join manually

1. Add to the [Diagram pane (Visual Database Tools)](diagram-pane-visual-database-tools.md) the table or table-valued object you want to work with.

1. Add the same table again, so that the Diagram pane shows the same table or table-valued object twice within the Diagram pane.

   The Query and View Designer assigns an alias to the second instance by adding a sequential number to the table name. In addition, the Query and View Designer creates a join line between the two occurrences of the table or table-valued object within the Diagram pane.

1. Right-click the join line and choose **Properties** from the shortcut menu.

1. In the Properties window select **Join Condition and Type** and select the **ellipses (...)** to the right of the property.

1. In the Join dialog box, change the comparison operator between the primary keys as required. For example, you might change the operator to less than (<).

1. Create the additional join condition (for example, authors.zip = authors1.zip) by dragging the name of the primary join column in the first occurrence of the table or table-valued object and dropping it on the corresponding column in the second occurrence.

1. Specify other options for the query such as output columns, search conditions, and sort order.

## Related content

- [Create self-joins automatically (Visual Database Tools)](create-self-joins-automatically-visual-database-tools.md)
- [Query with joins (Visual Database Tools)](query-with-joins-visual-database-tools.md)
