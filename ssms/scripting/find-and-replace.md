---
title: "Find and Replace"
description: Learn how to use the Find and Replace dialog box to find and replace text.
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/15/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "Find and Replace dialog box"
---
# Find and Replace

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

Use the **Find and Replace** dialog box to locate text within a file and optionally replace it. Versions of the **Find and Replace** dialog box with slightly different options can appear, depending on how the dialog box was opened. On the **Edit** menu, point to **Find and Replace**, and then select **Quick Find** to open the dialog box with find options, but without replace options. On the **Edit** menu, point to **Find and Replace**, and then select **Quick Replace** to open the dialog box with both find options and replace options.

Toolbar buttons and shortcut keys are also available to open the **Find and Replace** dialog box.

## Find what

These controls enable you to specify the string or expression to be matched.

#### Find what

Type the text to search for. The dialog box attempts to fill in a probable search text, using text selected with the cursor before opening the dialog box, or nearby text, or previously searched-for text. You can reuse one of the last 20 search strings by selecting it from this dropdown list.

#### [string with wildcards]

If you want to use wildcards such as asterisks (`*`) and question marks (`?`) in your search string, select the **Use** check box under **Find Options** and then select **Wildcards**.

#### [regular expression]

To cause the search engine to interpret your search string as a regular expression, select the **Use** check box under **Find Options** and then select **Regular expressions**.

#### Expression Builder

This triangular button next to the **Find what** box becomes available when the **Use** check box is selected in **Find Options**. Select this button to display a list of wildcards or regular expressions, depending upon the **Use** option selected. Choosing any item from this list adds it to the string specified in the **Find what** box.

## Replace with

These controls enable you to specify what is inserted in the place of the matched string or expression.

#### Replace with

To replace instances of the string specified in the **Find what** box with another string, enter the replacement string in this field. To delete instances of the string specified in the **Find what** box, leave this field blank. Select the dropdown list to display the last 20 items entered. To include regular expressions in the string specified in the **Replace with** box, select the **Use** check box and then select **Regular Expressions**.

#### Expression Builder

This triangular button next to the **Replace with** box becomes available when the **Use** check box is selected in **Find Options**. Select this button to display a list of wildcards or regular expressions, depending upon the **Use** option selected. Selecting any item in this list adds it to the string specified in the **Replace with** box.

#### Replace

Select this button to replace the current instance of the string specified in the **Find what** box with the string specified in the **Replace with** box, and find the next instance within the scope specified in **Look in**.

#### Replace all

Select this button to replace all instances of the string specified in the **Find what** box with the string specified in the **Replace with** box, in all files within the scope specified in the **Look in** box.

> [!CAUTION]  
> Make sure that **Look in** is set to include only those files that you want to modify.

A reminder is displayed that includes a **Keep modified files open** option. To retain the **Undo** option, you must select this option. **Undo** is only available in files that remain open for editing after they're modified.

#### Skip File

Becomes available when the value specified for **Look in** includes multiple files. Select this button if you don't want to search or modify the current file. The search continues in the next file on the list in **Look in**.

## Look In

#### Look in

Select the location to look for the text specified in **Find what**. Options are **Current Document**, which searches the document window that had focus when the dialog box was opened, and **All Open Documents**, which searches all document windows that are currently open in SQL Server Management Studio.

## Find options

You can expand or collapse the **Find Options** section. The following options can be selected or cleared.

#### Match case

When this check box is selected, the Find Results windows only display instances of the string specified in **Find what** that are matched both by content and by case. For example, a search for `"MyObject"` with the **Match case** check box selected returns `"MyObject"`, but not `"myobject"` or `"MYOBJECT"`.

#### Match whole word

When selected, the Find Results windows only display instances of the string specified in **Find what** that are matched in complete words. For example, a search for `"MyObject"` returns `"MyObject"`, but not `"CMyObject"` or `"MyObjectC"`.

#### Search up

Search from the cursor location toward the beginning of the document.

#### Search hidden text

Locate instances of the text that are concealed and collapsed text.

#### Use

Indicates how to interpret special characters entered in the **Find what** or **Replace with** text boxes. The options include **Wildcards** and **Regular Expressions**.

#### Regular Expressions

Special notations define patterns of text to match. For a list, see [How to search text with regular expressions](search-text-with-regular-expressions.md).

#### Wildcards

Special characters such as asterisks (`*`) and question marks (`?`) represent one or more characters. For a list, see [How to search text with regular expressions](search-text-with-regular-expressions.md).

#### Find Next

Begins searching for the text in the **Find what** box.

#### Replace

Select this button to replace the current instance of the string specified in **Find what** with the string specified in **Replace with**, and find the next instance within the scope specified in **Look in**.

#### Replace All

Choose this button to replace all instances of the string specified in **Find what** with the string specified in **Replace with**, in all files within the scope specified in **Look in**.

> [!CAUTION]  
> Make sure that **Look in** is set to include only those files that you want to modify.

## Find and Replace views

The tabs at the top of the Find and Replace window include **View** menus. These menus enable you to choose a set of fields to display in the active pane. You can leave the **Find and Replace** window docked in a convenient location, and then change from tab to tab and view to view, to perform any type of find or replace operation.

#### Quick Find

This toolbar tab changes the dialog box to a **Quick Find** dialog box.

#### Find in Files

This toolbar tab changes the dialog box to a **Find in Files** dialog box.

#### Quick Replace

This toolbar tab changes the dialog box to a **Quick Replace** dialog box

#### Replace in Files

This toolbar tab changes the dialog box to a **Replace in Files** dialog box

## Related content

- [SQL Server Management Studio keyboard shortcuts](../sql-server-management-studio-keyboard-shortcuts.md)
