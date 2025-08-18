---
title: "Manage the Editor and View Mode"
description: "Learn how to select either of two view modes of SQL Server Management Studio: Tabbed Documents mode and Multiple Document Interface mode. Learn also about split views, word wrap, Virtual Space mode, displaying line numbers, Full Screen mode, and Auto Hide All."
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/15/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "Query Editor [SQL Server Management Studio], managing window behavior"
  - "workbench view modes [SQL Server Management Studio]"
  - "full screen mode [SQL Server Management Studio]"
  - "fonts [SQL Server Management Studio]"
  - "word wraps [SQL Server Management Studio]"
  - "virtual space mode [SQL Server Management Studio]"
  - "splitting document views"
  - "displaying line numbers"
  - "view modes [SQL Server Management Studio]"
---

# Manage the Editor and view mode

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

The Editor gives you several ways to control the view of your code.

## Change the view mode

SQL Server Management Studio features a view mode called **Tabbed Documents**, which allows you to open multiple editors and documents simultaneously and access them through tabs at the top of the Editor. You can alternatively open the [!INCLUDE [ssManStudio](../includes/ssmanstudio-md.md)] environment in Multiple Document Interface (MDI) mode, which joins windows without the tabs, and allows each window to be tiled, minimized, and so on.

### Switch between view modes

1. Select **Options** on the **Tools** menu.

1. Select **Environment**. Select **General**.

1. Select **Tabbed documents** or **MDI environment**.

   The changes don't take effect until SQL Server Management Studio is restarted.

## Split the view

An Editor window can be split into two separate parts for easier editing.

### Split a window

1. Select the splitter bar (located above the scroll bar).

1. Drag the splitter bar downward.

1. To go back to a single pane, double-click the splitter bar dividing the two panes.

The new pane contains the same document, and any changes made to one pane are reflected in the other pane as long as that pane displays the same place in the document.

## Word wrap

When you activate word wrap, the horizontal scrollbar is removed, and any lines of code that exceed the width of the Editor's window size automatically wrap to the next displayed line, rather than scrolling off the side of the window.

### Activate word wrap

1. Select **Options** on the **Tools** menu.

1. Select **Text Editor**.

1. Open the appropriate language folder (or **All Languages** to affect all languages).

1. Select **Word wrap**.

## Enable virtual space mode

In **virtual space** mode, the Editor acts as if the space past the end of each line is filled with an infinite number of spaces, allowing code lines to continue off the side of the visible screen area.

#### Enable virtual space mode

1. Select **Options** on the **Tools** menu.

1. Select **Text Editor**.

1. Open the appropriate language folder (or **All Languages** to affect all languages).

1. Select **Enable virtual space**.

When virtual space mode isn't enabled, the cursor wraps from the end of one line to the first character of the next line and vice-versa.

## Display line numbers

You can turn on line numbering in your code. Line numbers are useful for navigating code. For more information, see [Navigate Code and Text](navigate-code-and-text.md).

Turning on line numbering doesn't mean that the document prints with line numbers. For line numbers to print, you must select the **Line numbers** check box in the **Page Setup** command on the **File** menu.

### Display line numbers in code

1. Select **Options** on the **Tools** menu.
1. Select **Text Editor**.
1. Select **All Languages**.
1. Select **General**.
1. Select **Line numbers**.

To specify line numbering for only some programming languages, select **Line Numbers** in the appropriate folder.

## Enable full screen mode

You can choose to hide all tool windows and view only document windows by enabling full screen mode.

### Enable full screen mode

1. Press **Alt**+**Shift**+**Enter** to toggle full screen mode.

## Use auto hide all

### Hide all the tool windows at once

1. Select **Auto Hide All** on the **Window** menu.
