---
title: Create Subqueries
description: "Create Subqueries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "search criteria [SQL Server], subqueries"
  - "nested queries"
  - "subqueries [SQL Server], SQL pane"
---
# Create subqueries (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can use the results of one query as the input for another. You can use the results of a subquery as a statement that uses the IN( ) function, the `EXISTS` operator, or the `FROM` clause.

You can create a subquery by entering it directly into the SQL pane or by copying a query and pasting it into another.

## Define a subquery in the SQL pane

1. Create the primary query.

1. In the SQL pane, select the SQL statement, and then use **Copy** to move the query to the Clipboard.

1. Start the new query, and then use **Paste** to move the first query into the new query's `WHERE` or `FROM` clause.

   For example, imagine you have two tables, `products` and `suppliers`, and you want to create a query showing all products for suppliers in Sweden. Create the first query on the `suppliers` table to find all Swedish suppliers:

   ```sql
   SELECT supplier_id
   FROM supplier
   WHERE (country = 'Sweden');
   ```

   Use the Copy command to move this query to the Clipboard. Create the second query using the `products` table, listing the information you need about products:

   ```sql
   SELECT product_id,
          supplier_id,
          product_name
   FROM products;
   ```

   In the SQL pane, add a `WHERE` clause to the second query, then paste the first query from the Clipboard. Place parentheses around the first query, so that the end result looks like this:

   ```sql
   SELECT product_id,
          supplier_id,
          product_name
   FROM products
   WHERE supplier_id IN (SELECT supplier_id
                         FROM supplier
                         WHERE (country = 'Sweden'));
   ```

## Related content

- [Supported Query Types (Visual Database Tools)](supported-query-types-visual-database-tools.md)
- [Specify search criteria (Visual Database Tools)](specify-search-criteria-visual-database-tools.md)
