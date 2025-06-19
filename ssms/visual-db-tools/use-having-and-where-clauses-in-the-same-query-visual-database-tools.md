---
title: Use HAVING and WHERE Clauses in the Same Query
description: "Use HAVING and WHERE clauses in the same query (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: randolphwest
ms.date: 10/16/2023
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "search criteria [SQL Server], excluding rows"
  - "search criteria [SQL Server], WHERE clause"
  - "search conditions [SQL Server], HAVING clause"
  - "row excluded in search [SQL Server]"
  - "search criteria [SQL Server], HAVING clause"
  - "HAVING clause, search criteria"
  - "search conditions [SQL Server], WHERE clause"
  - "WHERE clause, search criteria"
  - "excluding rows"
---
# Use HAVING and WHERE clauses in the same query (Visual Database Tools)

[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

In some instances, you might want to exclude individual rows from groups (using a `WHERE` clause) before applying a condition to groups as a whole (using a `HAVING` clause).

A `HAVING` clause is like a `WHERE` clause, but applies only to groups as a whole (that is, to the rows in the result set representing groups), whereas the `WHERE` clause applies to individual rows. A query can contain both a `WHERE` clause and a `HAVING` clause. In that case:

- The `WHERE` clause is applied first to the individual rows in the tables or table-valued objects in the **Diagram** pane. Only the rows that meet the conditions in the `WHERE` clause are grouped.

- The `HAVING` clause is then applied to the rows in the result set. Only the groups that meet the `HAVING` conditions appear in the query output. You can apply a `HAVING` clause only to columns that also appear in the GROUP BY clause or in an aggregate function.

## Specify a WHERE and HAVING clause on two joined tables

> [!NOTE]  
> The database used in this article is the `pubs` database, available from [Northwind and pubs sample databases for Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs) on GitHub.

For example, imagine that you're joining the `titles` and `publishers` tables to create a query showing the average book price for a set of publishers. You want to see the average price for only a specific set of publishers - perhaps only the publishers in the state of California. And even then, you want to see the average price only if it's over $10.00.

You can establish the first condition by including a `WHERE` clause, which discards any publishers that aren't in California, before calculating average prices. The second condition requires a `HAVING` clause, because the condition is based on the results of grouping and summarizing the data. The resulting SQL statement might look like this:

```sql
SELECT titles.pub_id, AVG(titles.price)
FROM titles INNER JOIN publishers
   ON titles.pub_id = publishers.pub_id
WHERE publishers.state = 'CA'
GROUP BY titles.pub_id
HAVING AVG(price) > 10;
```

In the Visual Database Tools of [!INCLUDE [ssManStudioFull](../includes/ssmanstudiofull-md.md)], you can create both `HAVING` and `WHERE` clauses in the **Criteria** pane. By default, if you specify a search condition for a column, the condition becomes part of the `HAVING` clause. However, you can change the condition to be a `WHERE` clause.

You can create a `WHERE` clause and `HAVING` clause involving the same column. To do so, you must add the column twice to the **Criteria** pane, then specify one instance as part of the `HAVING` clause and the other instance as part of the `WHERE` clause.

### Specify a WHERE condition in an aggregate query

1. Specify the groups for your query. For details, see [Group Rows in Query Results (Visual Database Tools)](group-rows-in-query-results-visual-database-tools.md).

1. If it's not already in the **Criteria** pane, add the column on which you want to base the `WHERE` condition.

1. Clear the **Output** column unless the data column is part of the GROUP BY clause or included in an aggregate function.

1. In the **Filter** column, specify the `WHERE` condition. The Query and View Designer adds the condition to the `HAVING` clause of the SQL statement.

   > [!NOTE]  
   > The query shown in the example for this procedure joins two tables, `titles` and `publishers`.

   At this point in the query, the SQL statement contains a `HAVING` clause:

   ```sql
   SELECT titles.pub_id, AVG(titles.price)
   FROM titles INNER JOIN publishers
       ON titles.pub_id = publishers.pub_id
   GROUP BY titles.pub_id
   HAVING publishers.state = 'CA'
   ```

1. In the **Group By** column, select **Where** from the list of group and summary options. The Query and View Designer removes the condition from the `HAVING` clause in the SQL statement and adds it to the `WHERE` clause.

   The SQL statement changes to include a `WHERE` clause instead:

   ```sql
   SELECT titles.pub_id, AVG(titles.price)
   FROM titles INNER JOIN publishers
       ON titles.pub_id = publishers.pub_id
   WHERE publishers.state = 'CA'
   GROUP BY titles.pub_id;
   ```

## Related content

- [SELECT - HAVING (Transact-SQL)](/sql/t-sql/queries/select-having-transact-sql)
- [Sort and Group Query Results (Visual Database Tools)](sort-and-group-query-results-visual-database-tools.md)
- [Summarize Query Results (Visual Database Tools)](summarize-query-results-visual-database-tools.md)
