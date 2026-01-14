---
title: Remove Columns from Queries
description: "Remove columns from queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "removing columns"
  - "queries [SQL Server], columns"
  - "deleting columns"
  - "dropping columns"
---
# Remove columns from queries (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

If you no longer want to use a column in a query, you can remove it. If you do, the Query and View Designer removes references to the column in the select list, the sort specification, the search criteria, **SQL Pane**, and any grouping specifications.

> [!NOTE]  
> If you want to remove a column from just the output of a Select query, you can do so without removing it from the query altogether. For details, see [Remove columns from query results](remove-columns-from-query-results-visual-database-tools.md).

## Remove a column from the query

- In the **Criteria Pane**, select the grid row containing the column you want to remove and then press `DELETE`.

  -or-

- Remove all references to the column in the [SQL Pane](sql-pane-visual-database-tools.md).

## Related content

- [Add columns to queries (Visual Database Tools)](add-columns-to-queries-visual-database-tools.md)
- [Sort and group query results (Visual Database Tools)](sort-and-group-query-results-visual-database-tools.md)
- [Summarize query results (Visual Database Tools)](summarize-query-results-visual-database-tools.md)
- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
