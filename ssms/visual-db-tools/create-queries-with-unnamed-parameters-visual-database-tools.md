---
title: Create Queries with Unnamed Parameters
description: "Create queries with unnamed parameters (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "unnamed parameters"
  - "parameters [SQL Server], unnamed"
---
# Create queries with unnamed parameters (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can create a query with an unnamed parameter by specifying a question mark (?) as a placeholder for a literal value. Query and View Designer gives it a temporary name. You can specify as many unnamed parameters in the query as you need.

When you run the query in the Query and View Designer, the Query Parameters Dialog Box is displayed with the temporary name.

## Specify an unnamed parameter

1. Add the columns or expressions that you want to search to the [Criteria Pane (Visual Database Tools)](criteria-pane-visual-database-tools.md). If you don't want the search columns or expressions to appear in the query output, remove them as output columns.

1. Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter a question mark (?).

   By default, the Query and View Designer adds the "=" operator. However, you can edit the cell to substitute ">", "<", or any other SQL comparison operator.

## Related content

- [Query with parameters (Visual Database Tools)](query-with-parameters-visual-database-tools.md)
