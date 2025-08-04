---
title: Delete Rows in the Results Pane
description: "Delete rows in the Results pane (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "View Designer, Results pane"
  - "removing rows"
  - "row removal [SQL Server], Visual Database Tools Results pane"
  - "row deletions [SQL Server], Visual Database Tools Results pane"
  - "Query Designer [SQL Server], Results pane"
  - "deleting rows"
  - "Results pane"
---
# Delete rows in the Results pane (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

Delete rows in the Results pane if you want to delete records in the database. If you want to delete all of the rows, you can use a Delete query. For more information, see [Create Delete queries](create-delete-queries-visual-database-tools.md). If you only want to remove rows from the Results pane, change the criteria for the query. For more information, see [Specify search criteria](specify-search-criteria-visual-database-tools.md).

## Delete a row or rows

1. Select the box to the left of the row or rows you want to delete in the Results pane.

1. Press `DELETE`.

1. In the message box asking for confirmation, select **Yes**.

> [!CAUTION]  
> Rows you delete in this way are permanently removed from the database and can't be recalled.

> [!NOTE]  
> If any of the selected rows can't be deleted from the database, none of them are deleted, and you receive a message telling you which rows can't be deleted.

## Related content

- [Create Delete queries (Visual Database Tools)](create-delete-queries-visual-database-tools.md)
- [Specify search criteria (Visual Database Tools)](specify-search-criteria-visual-database-tools.md)
