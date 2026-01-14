---
title: Navigate in the Query and View Designer
description: "Navigate in the Query and View Designer (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "View Designer, navigating"
  - "shortcuts [SQL Server]"
  - "Query Designer [SQL Server], navigating"
  - "keyboard shortcuts [Visual Database Tools]"
---
# Navigate in the Query and View Designer (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can work in the Query and View Designer using the keyboard or the mouse. Refer to the following tables for specific methods.

## Any Pane

| To | Press | Select |
| --- | --- | --- |
| Move among the Query and View Designer panes | **F6**, **Shift**+**F6** | Anywhere in the target pane |

> [!TIP]  
> You can use the shortcut keys **Ctrl**+**Tab** to change focus to other panes in addition to the Query and View Designer panes.

## Diagram Pane

| To | Press | Select |
| --- | --- | --- |
| Move among tables, other table-structured objects (and to join lines, if available) | **Tab**, or **Shift**+**Tab** | The table, table-structured object, or join line to move to |
| Move between columns in a table or table-structured object | Arrow keys | The column to go to |
| Choose the selected data column for output | SPACEBAR or PLUS key | The check box next to the name of the column |
| Remove the selected data column from the query output | SPACEBAR or MINUS key | The check box next to the name of the column |
| Remove the selected table, table-structured object, or join line from the query | `DELETE` | Right-click, and then choose **Remove** |

> [!NOTE]  
> If multiple items are selected, pressing this key affects all selected items. Select multiple items by holding down the **Ctrl** key while selecting them.

For more information, see [Diagram pane (Visual Database Tools)](diagram-pane-visual-database-tools.md).

## Criteria Pane

| To | Press | Select |
| --- | --- | --- |
| Move among cells | Arrow keys or **Tab** or **Shift**+**Tab** | The target cell |
| Move to the last row in a selected column | **Ctrl**+**Down Arrow** | |
| Move to the first row in a selected column | **Ctrl**+**Up Arrow** | |
| Move to the top left cell in the visible portion of grid | **Ctrl**+**Home** | |
| Move to the bottom right cell | **Ctrl**+**End** | |
| Move in a dropdown list | **Up Arrow** or **Down Arrow** | The button in the cell |
| Select an entire grid column | **Ctrl**+**Space** | The column header |
| Toggle between edit mode and cell selection mode | **F2** | |
| Copy selected text in cell to the Clipboard (in edit mode) | **Ctrl**+**C** | |
| Cut selected text in cell and place it on the Clipboard (in edit mode) | **Ctrl**+**X** | |
| Paste text from the Clipboard (in edit mode) | **Ctrl**+**V** | |
| Toggle between insert and overstrike mode while editing in a cell | **Insert** | |
| Toggle the check box in the Output column | **Space** | The check box |
| Clear the selected contents of a cell | **Delete** | |
| Clear all values for a selected grid column | **Delete** | |
| Insert row between existing rows | **Insert** after you select grid row | |
| Add an **Or ...** column | **Insert** after you select any **Or ...** column | |

> [!NOTE]  
> If multiple items are selected, pressing this key affects all selected items.

For more information, see [Criteria Pane (Visual Database Tools)](criteria-pane-visual-database-tools.md).

## SQL Pane

You can use the standard Windows editing keys when working in the SQL pane, such as **Ctrl** + Arrow keys to move between words, and the **Cut**, **Copy**, and **Paste** commands on the **Edit** menu.

> [!NOTE]  
> You can only insert text; there's no overstrike mode.

For more information, see [SQL Pane (Visual Database Tools)](sql-pane-visual-database-tools.md).

## Results Pane

| To | Press | Select |
| --- | --- | --- |
| Move between cells | Arrow keys or **Tab** or **Shift**+**Tab** | The target cell |
| Move to first or last cell in current row | **Home** or **End** | |
| Move to the first row in the current column | **Ctrl**+**Up Arrow** | |
| Move to the top left cell | **Ctrl**+**Home** | |
| Move to the bottom cell in the first column | **Ctrl**+**Down Arrow** | |
| Select to first character in a cell | **Shift**+**Home** | |
| Select to last character in a cell | **Shift**+**End** | |
| Toggle between edit mode and cell selection mode | **F2** | |
| Toggle between insert and overstrike mode while editing in a cell | **Insert** | |
| Delete a row from the table | **Delete** | |
| Undo changes for the current cell | **Esc** in cell that has changed | |
| Undo changes for the current row | **Esc** in any cell that hasn't changed | |
| Enter null into a cell | **Ctrl**+**0** | |
| Copy selected columns or rows to the Clipboard | **Ctrl**+**C** | |
| Copy selected text in cell to the Clipboard (in edit mode) | **Ctrl**+**C** | |
| Cut selected text in cell to the Clipboard (in edit mode) | **Ctrl**+**X** | |
| Paste text from the Clipboard (in edit mode) | **Ctrl**+**V** | |

> [!NOTE]  
> If multiple items are selected, pressing this key affects all selected items.

For more information, see [Results pane (Visual Database Tools)](results-pane-visual-database-tools.md).

## Related content

- [Design queries and views how-to articles (Visual Database Tools)](design-queries-and-views-how-to-topics-visual-database-tools.md)
