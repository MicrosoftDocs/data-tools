---
title: Create Column Aliases
description: "Create column aliases (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "columns [SQL Server], aliases"
  - "aliases [SQL Server], columns"
---
# Create column aliases (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can create aliases for column names to make it easier to work with column names, calculations, and summary values. For example, you can create a column alias to:

- Create a column name, such as "Total Amount," for an expression such as `(quantity * unit_price)` or for an aggregate function.

- Create a shortened form of a column name, such as `"d_id"` for `"discounts.stor_id."`

After you have defined a column alias, you can use the alias in a Select query to specify query output.

## Create a column alias

1. In the **Criteria Pane**, locate the row containing the data column for which you want to create an alias, and if necessary, mark it for output. If the data column isn't already in the grid, add it.

1. In the **Alias** column for that row, enter the alias. The alias must follow all naming conventions for SQL. If the alias name you enter contains spaces, the Query and View Designer automatically puts delimiters around it.

## Related content

- [Add columns to queries (Visual Database Tools)](add-columns-to-queries-visual-database-tools.md)
- [Sort and group query results (Visual Database Tools)](sort-and-group-query-results-visual-database-tools.md)
- [Summarize query results (Visual Database Tools)](summarize-query-results-visual-database-tools.md)
- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
