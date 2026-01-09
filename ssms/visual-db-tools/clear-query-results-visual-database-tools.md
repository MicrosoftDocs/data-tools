---
title: Clear Query Results
description: "Clear query results (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "result sets [SQL Server], queries"
  - "results [SQL Server], query"
  - "queries [SQL Server], results"
  - "Results pane"
  - "clearing query results"
---
# Clear query results (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

After running a query in the **Query and View Designer**, you can clear the Results pane. This procedure applies to queries created by using the **Open View** or **Open Table** options from Object Explorer. In SQL Server Management Studio, after running a query in the Query Editor, the Results pane can't be cleared except by closing the Query Editor window or running another query.

> [!NOTE]  
> This doesn't undo the changes you've made to the database. For more information about how the Results pane works see [Work with data in the Results pane](work-with-data-in-the-results-pane-visual-database-tools.md).

## Clear query results of a view

Right-click in the [Results pane](results-pane-visual-database-tools.md), point to **Pane**, and then select **Clear Results**.

If a query is being executed when you clear the Results pane, the Query and View Designer stops the query.

## Related content

- [Run queries (Visual Database Tools)](run-queries-visual-database-tools.md)
- [Stop a query (Visual Database Tools)](stop-a-query-visual-database-tools.md)
- [Work with data in the Results pane (Visual Database Tools)](work-with-data-in-the-results-pane-visual-database-tools.md)
