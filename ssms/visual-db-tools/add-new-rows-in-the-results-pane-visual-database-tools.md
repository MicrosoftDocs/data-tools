---
title: Add New Rows in the Results Pane
description: "Add new rows in the Results pane (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "View Designer, Results pane"
  - "inserting rows"
  - "Query Designer [SQL Server], Results pane"
  - "Results pane"
  - "adding rows"
  - "row additions [SQL Server], Results pane"
---

# Add new rows in the Results pane (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can add new data either by typing it in or by pasting it from another program such as Notepad or Excel. A row to be pasted must have exactly the same number and types of columns as the table into which you're pasting. You can paste multiple rows into the Results pane at once.

For information about how to enter data see [Rules for updating results](rules-for-updating-results-visual-database-tools.md).

## Add a new data row

1. Navigate to the bottom of the Results pane, where a blank row is available for adding a new data row.

   The initial values for all columns are `NULL`.

   > [!TIP]  
   > To go directly to the first empty row use the navigation bar at the bottom of the Results pane.

1. If you're pasting rows from the Clipboard, select the new row by selecting the button to its left.

   > [!NOTE]  
   > If one or more of the rows you're pasting can't be committed to the database, you receive a message telling you which rows couldn't be committed.

1. Enter the data for the new row. If you're pasting, choose **Paste** from the **Edit** menu.

1. Leave that row to commit it to the database.

If an error occurs when you save the row the Query and View Designer displays a message and then returns you to the row you were editing. You can then:

- Resolve the error by making further edits in the row.

- Cancel the edit by pressing ESC. If you press ESC while in a cell that you changed, the changes for that cell are canceled. If you press ESC while in a cell you haven't changed, the changes for the entire row are canceled.

## Related content

- [Work with data in the Results pane (Visual Database Tools)](work-with-data-in-the-results-pane-visual-database-tools.md)
- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
