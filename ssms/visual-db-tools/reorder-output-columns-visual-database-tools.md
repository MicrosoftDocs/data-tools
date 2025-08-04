---
title: Reorder Output Columns
description: "Reorder output columns (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "reordering output columns [SQL Server]"
  - "output columns [SQL Server]"
---
# Reorder output columns (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

The order in which you add data columns to a Select query determines the order in which they appear in the results. The first column you add to the query appears leftmost in the results, the second column next, and so on.

If you're creating Update or Insert queries, the order in which you add columns affects the order in which data is processed.

To control where a data column appears in the result set, or in what order it's used, you can reorder the columns.

## Reorder columns for output

1. In the [Criteria Pane (Visual Database Tools)](criteria-pane-visual-database-tools.md), select the row containing the column by selecting the row selector button to the left of the row.

1. Point to the row selector button and drag the row to a new location.

   -or-

   Edit the order of the column names in the [SQL Pane (Visual Database Tools)](sql-pane-visual-database-tools.md).

> [!TIP]  
> You can add a data row at a specific location in the Criteria pane by inserting a blank row into the Criteria pane, and then specifying the data column to insert. For details, see [Add columns to queries (Visual Database Tools)](add-columns-to-queries-visual-database-tools.md).

## Related content

- [Sort and group query results (Visual Database Tools)](sort-and-group-query-results-visual-database-tools.md)
- [Summarize query results (Visual Database Tools)](summarize-query-results-visual-database-tools.md)
- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
