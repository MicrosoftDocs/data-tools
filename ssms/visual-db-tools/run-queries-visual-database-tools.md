---
title: Run Queries
description: "Run queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "queries [SQL Server], executing"
  - "executing queries [SQL Server]"
---
# Run queries (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

When you have finished designing your query, you can run it.

## Execute a query

1. Open or create the query you want to run.

1. Right-click anywhere in the query window, and select **Execute SQL** from the shortcut menu.

   -or-

   Press CTRL+R.

If you're creating a Select query, the results of the query appear in the Results pane.

The Query and View Designer returns results to your computer in batches (incrementally) so that you can begin viewing results as soon as possible, and so that you can perform other tasks while the query is underway.

If you're creating an Update, Insert From, Insert Into, Delete, or Make Table query, the Query and View Designer displays a message indicating how many rows were affected by the query.

## Related content

- [Work with data in the Results pane (Visual Database Tools)](work-with-data-in-the-results-pane-visual-database-tools.md)
- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
