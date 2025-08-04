---
title: Create UNION Queries
description: "Create UNION queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "queries [SQL Server], types"
  - "UNION queries"
  - "Select query"
  - "combining query results"
  - "merged SELECT query [SQL Server]"
---
# Create UNION queries (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

The `UNION` keyword enables you to include the results of two `SELECT` statements in one resulting table. All rows returned from either `SELECT` statement are combined into the result of the `UNION` expression. For examples, see [SELECT examples](/sql/t-sql/queries/select-examples-transact-sql).

> [!NOTE]  
> The Diagram pane can only display one `SELECT` clause. Therefore, when you're working with a `UNION` query, Query Designer hides the Table Operations pane.

## Create a merged SELECT query

1. Open a query or create a new one.

1. In the SQL pane, type a valid `UNION` expression.

   The following example is a valid `UNION` expression.

   ```sql
   SELECT ProductModelID,
          Name
   FROM Production.ProductModel
   UNION
   SELECT ProductModelID,
          Name
   FROM dbo.Gloves;
   ```

1. On the **Query Designer** menu, select **Execute SQL** to run the query.

   Your `UNION` query is now formatted by Query Designer.

## Related content

- [Supported Query Types (Visual Database Tools)](supported-query-types-visual-database-tools.md)
- [Design queries and views how-to articles (Visual Database Tools)](design-queries-and-views-how-to-topics-visual-database-tools.md)
- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
- [Set Operators - UNION (Transact-SQL)](/sql/t-sql/language-elements/set-operators-union-transact-sql)
