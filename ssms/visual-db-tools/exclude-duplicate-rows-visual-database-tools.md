---
title: Exclude Duplicate Rows
description: "Exclude duplicate rows (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "search criteria [SQL Server], excluding rows"
  - "row duplicates [SQL Server]"
  - "duplicate rows"
  - "row excluded in search [SQL Server]"
  - "result sets [SQL Server], duplicate values"
  - "excluding rows"
---
# Exclude duplicate rows (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

If you want to see only unique values in a result set, you can specify that you want to exclude duplicates from the result set.

## Exclude duplicate rows from the result set

1. Right-click the background of the Diagram pane, then choose **Properties** from the shortcut menu.

1. In the Property window, select **Distinct values** and set the value to **Yes**.

   The Query and View Designer inserts the keyword `DISTINCT` in front of the list of display columns in the SQL statement.

   > [!NOTE]  
   > If you use the `DISTINCT` keyword you might not be able to modify the result set in the results pane.

## Related content

- [Specify search criteria (Visual Database Tools)](specify-search-criteria-visual-database-tools.md)
- [Sort and group query results (Visual Database Tools)](sort-and-group-query-results-visual-database-tools.md)
