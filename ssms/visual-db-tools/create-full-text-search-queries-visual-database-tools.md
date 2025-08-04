---
title: Create Full-Text Search Queries
description: "Create Full-Text Search queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "CONTAINS predicate (Transact-SQL)"
  - "queries [full-text search], creating"
  - "full-text queries [SQL Server], creating"
---
# Create Full-Text Search queries (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

Full-text searches use the `CONTAINS` predicate to locate rows that have specified text in a given column. Full-Text searches are only possible on columns that have active full-text indexes. If you attempt to use the `CONTAINS` clause on a column that doesn't have a currently active full-text index, you receive an error. For more information on full-text indexes and the `CONTAINS` clause, see [Full-Text Search](/sql/relational-databases/search/full-text-search) and [CONTAINS](/sql/t-sql/queries/contains-transact-sql).

## Create a full-text search query

1. Open a query from Solution Explorer or create a new one.

1. In the `WHERE` clause of your query, use the `CONTAINS` function to search a full-text column.

## Related content

- [Supported Query Types (Visual Database Tools)](supported-query-types-visual-database-tools.md)
- [Design queries and views how-to articles (Visual Database Tools)](design-queries-and-views-how-to-topics-visual-database-tools.md)
- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
