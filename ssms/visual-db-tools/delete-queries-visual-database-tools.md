---
title: Delete Queries
description: "Delete queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "dropping queues"
  - "deleting queries"
  - "removing queries"
  - "queries [SQL Server], deleting"
---
# Delete queries (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can delete a query, removing it from the project and permanently deleting it from the file system. Queries deleted using the following procedure aren't sent to the Recycle Bin and can't be recovered.

## Permanently delete a query

1. From the **View** menu, choose Solution Explorer.

1. In Solution Explorer, select the query you want to permanently delete.

1. Right-click the query and from the shortcut menu, select **Remove**.

1. In the **Microsoft SQL Server Management Studio** dialog box, select **Delete**.

> [!NOTE]  
> If you want to remove the query from the project without deleting it, select **Remove**. Then you can right-click the query folder and choose **Add Item** to find and add the query back later.

## Related content

- [Clear query results (Visual Database Tools)](clear-query-results-visual-database-tools.md)
- [Discard changes made to queries (Visual Database Tools)](discard-changes-made-to-queries-visual-database-tools.md)
- [Design queries and views how-to articles (Visual Database Tools)](design-queries-and-views-how-to-topics-visual-database-tools.md)
- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
