---
title: Remove Columns from Query Results
description: "Remove columns from query results (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "columns [SQL Server], deleting"
  - "result sets [SQL Server], queries"
  - "removing columns"
  - "results [SQL Server], query"
  - "deleting columns"
  - "queries [SQL Server], results"
---
# Remove columns from query results (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

If you're using a column in a Select query but don't want to display it in the result set (that is, you don't want it in the query's select list), you can remove it from output. After you remove the column from the query's output, you can still use it in search conditions or as a sorting field.

> [!NOTE]  
> If you want to remove a column from the query altogether, see [Remove columns from queries (Visual Database Tools)](remove-columns-from-queries-visual-database-tools.md).

## Remove a column from the query output

- In the **Criteria Pane**, clear the check box in the **Output** column for the data column you want to remove. (If you want to add the column back to the query output, you can check the **Output** column again.)

  -or-

- Remove the column from the output list in the [SQL Pane (Visual Database Tools)](sql-pane-visual-database-tools.md).

## Related content

- [Add columns to queries (Visual Database Tools)](add-columns-to-queries-visual-database-tools.md)
- [Remove columns from queries (Visual Database Tools)](remove-columns-from-queries-visual-database-tools.md)
- [Sort and group query results (Visual Database Tools)](sort-and-group-query-results-visual-database-tools.md)
- [Summarize query results (Visual Database Tools)](summarize-query-results-visual-database-tools.md)
- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
