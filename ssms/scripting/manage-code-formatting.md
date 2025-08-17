---
title: "Manage Code Formatting"
description: Learn about the three styles of text indenting and how to use them, and learn how to create clickable URLs.
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/15/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "indenting code [SQL Server]"
  - "displaying URLs"
  - "code formatting [SQL Server Management Studio]"
  - "collapsing text"
  - "formats [SQL Server], code formatting in SQL Server Management Studio"
  - "hiding text"
  - "formats [SQL Server]"
  - "text [SQL Server], code formats"
  - "automatic indentation"
  - "converting text to lower case"
  - "Query Editor [SQL Server Management Studio], managing code formats"
  - "URL displayed in code [SQL Server Management Studio]"
  - "converting text to upper case"
  - "text [SQL Server]"
  - "unindenting code"
---

# Manage code formatting

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

With the Editor you can format your code with indenting, hidden text, URLs, and so forth. You can also autoformat your code as you type by using smart indenting.

## Indenting

You can choose three different styles of text indenting. You can also specify how many spaces compose a single indentation or tab, and whether the Editor uses tabs or space characters when indenting.

### Choose an indenting style

1. On the **Tools** menu, select **Options**.

1. Select **Text Editor**.

1. Select the folder, and select **All Languages** to set indenting for all languages.

1. Select **Tabs**.

1. Select one of the following options:

   - **None**. The cursor goes to the beginning of the next line.
   - **Block**. The cursor aligns the next line with the previous line.
   - **Smart** (Default). The language service determines the appropriate indenting style to use.

   Some languages don't offer all three indenting options.

### Change indent tab settings

1. On the **Tools** menu, select **Options**.

1. Select **Text Editor**.

1. Select the folder for **All Languages** to set indenting for all languages.

1. Select **Tabs**.

1. To specify tab characters for tab and indent operations, select **Keep tabs**. To specify space characters, select **Insert spaces**.

   If you select **Insert Spaces**, enter the number of space characters each tab or indent represents under **Tab Size** or **Indent Size**, respectively.

### Indent code

1. Select the text you want to indent.

1. Press TAB, or select the **Indent** button on the Standard toolbar.

### Unindent code

1. Select the text you want to unindent.

1. Press **Shift**+**Tab**, or select the **Unindent** button on the Standard toolbar.

### Automatically indent all of your code

1. On the **Tools** menu, select **Options**.

1. Select **Text Editor**.

1. Select **All Languages**.

1. Select **Tabs**.

1. Select **Smart**.

> [!NOTE]  
> The **Smart** option isn't available for some languages.

### Convert white space to tabs

1. Select the text whose white space you want to convert to tabs.

1. On the **Edit** menu, point to **Advanced**, and select **Tabify Selection**.

### Convert tabs to spaces

1. Select the text whose tabs you want to convert to spaces.

1. On the **Edit** menu, point to **Advanced**, and select **Untabify Selection**.

The behavior of these commands depends on the tab settings in the **Options** dialog box. For example, if the tab setting is 4, **Tabify Selection** creates a tab for every 4 contiguous spaces, and **Untabify Selection** creates 4 spaces for every tab.

## Convert text to upper and lower case

You can use commands to convert text to all uppercase or lower case.

### Switch text to upper or lower case

1. Select the text you want to convert.

1. To convert text to uppercase, press **Ctrl**+**Shift**+**U**, or select **Make Uppercase** on the **Advanced** submenu of the **Edit** menu.

1. To convert text to lowercase, press **Ctrl**+**Shift**+**L**, or select **Make Lowercase** on the **Advanced** submenu of the **Edit** menu.

> [!NOTE]  
> For a complete list of keyboard shortcut keys, see [SQL Server Management Studio keyboard shortcuts](../sql-server-management-studio-keyboard-shortcuts.md).

## Display and link to URLs

You can create and display selectable URLs in your code. By default, the URLs:

- Are underlined.

- Change the mouse pointer to a hand when you move over them.

- Open the URL when selected, if the URL is valid.

### Display a selectable URL

1. On the **Tools** menu, select **Options**.

1. Select **Text Editor**.

1. To change the option for only one language, select that language folder and then select **General**. To change the option for all languages, select **All Languages** and then select **General**.

1. Select **Enable single-click URL navigation**.
