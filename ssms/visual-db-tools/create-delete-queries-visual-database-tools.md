---
title: Create Delete Queries
description: "Create Delete queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "row removal [SQL Server], Delete query"
  - "Delete query"
  - "queries [SQL Server], types"
  - "removing rows"
  - "removing data"
  - "data deletions [SQL Server]"
  - "deleting rows"
  - "deleting data"
---
# Create Delete queries (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can delete all rows in a table by using a Delete query.

> [!NOTE]  
> Deleting all rows from a table clears the data in the table but doesn't delete the table itself. To delete a table from a database, right-click the table in Object Explorer and select **Delete**.

When you create a Delete query, the Criteria pane changes to reflect the options available for deleting rows. Because you don't display data in a Delete query, the Output, Sort By, and Sort Order columns are removed. In addition, the check boxes next to the column names in the rectangle representing the table or table-valued object are removed because you can't specify individual columns to delete.

If the Query and View Designer can't delete one or more of the rows, none of them are deleted and you receive a message telling you which rows contain information that can't be deleted from the database.

> [!CAUTION]  
> You can't undo the action of executing a Delete query. As a precaution, back up your data before executing a Delete query.

## Create a Delete query

1. Add the table to delete rows from to the Diagram pane.

1. From the **Query Designer** menu, point to **Change Type**, and then select **Delete**. **Note** If more than one table is displayed in the Diagram pane when you start the Delete query, the Query and View Designer displays the Delete Table dialog box to prompt you for the name of the table to delete rows from.

When you execute the Delete query, no results are reported in the [Results pane (Visual Database Tools)](results-pane-visual-database-tools.md). Instead, a message appears indicating how many rows were deleted.

## Related content

- [Supported Query Types (Visual Database Tools)](supported-query-types-visual-database-tools.md)
- [Design queries and views how-to articles (Visual Database Tools)](design-queries-and-views-how-to-topics-visual-database-tools.md)
