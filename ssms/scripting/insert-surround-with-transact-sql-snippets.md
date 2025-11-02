---
title: Insert Surround-With Transact-SQL Snippets
description: Learn how to insert a surround-with snippet to serve as a starting point for placing statements in code blocks.
author: rwestMSFT
ms.author: randolphwest
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "snippets [Transact-SQL], surround with"
  - "IntelliSense [SQL Server], surround with snippets"
  - "Transact-SQL snippets, surround with"
---
# Insert surround-with Transact-SQL snippets

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

A surround-with snippet is a template you can use as a starting point when enclosing a set of [!INCLUDE [tsql](../includes/tsql-md.md)] statements in a `BEGIN`, `IF`, or `WHILE` block.

## Insert surround-with snippets

Surround-with snippets can be launched in one of three ways:

- A keyboard shortcut
- The **Edit** menu
- The context menu

After inserting the snippet, you must change the replacement text to form a valid [!INCLUDE [tsql](../includes/tsql-md.md)] statement. For more information, see [Complete Transact-SQL Snippets](complete-transact-sql-snippets.md).

1. In the [!INCLUDE [ssDE](../includes/ssde-md.md)] Query Editor window, select the set of statements to be included in the block.

1. Use one of these three methods to display the list of surround-with snippets:

   - Type **Ctrl**+**K**, **Ctrl**+**S**.
   - From the **Edit** menu, point to **IntelliSense**, and then select the **Surround With** command.
   - Right-click the selected text, and then select the **Surround With** command from the context menu.

1. Select the name of the snippet (`BEGIN`, `IF`, or `WHILE`) from the list either by using the mouse, or by typing the name of the snippet and pressing **Tab** or **Enter**.

## Related content

- [Insert Transact-SQL Snippets](insert-transact-sql-snippets.md)
