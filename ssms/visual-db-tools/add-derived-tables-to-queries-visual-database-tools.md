---
title: Add Derived Tables to Queries
description: "Add Derived Tables to Queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "queries [Visual Database Tools]"
  - "joins [SQL Server], derived tables"
  - "table joins [SQL Server]"
  - "derived tables"
---

# Add derived tables to queries (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

Derived tables are result sets used as table sources in a query. You can add a derived table to a query in the **Diagram Pane**.

## Add a derived table to a query

1. Open an existing query or create a new query.

1. Right-click the **Diagram Pane** and choose **Add New Derived Table**.

   A new table with a name in the format <derivedtbl_N> is added, and the derived table's `SELECT` statement is added to the query's `FROM` clause.

## Related content

- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
- [Create queries (Visual Database Tools)](create-queries-visual-database-tools.md)
- [Open queries (Visual Database Tools)](open-queries-visual-database-tools.md)
- [SELECT (Transact-SQL)](/sql/t-sql/queries/select-transact-sql)
