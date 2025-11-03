---
title: Complete Transact-SQL Snippets
description: A Transact-SQL snippet is a code template. Learn how to customize its use by inserting content at its replacement points, and by adding syntax elements to the template.
author: rwestMSFT
ms.author: randolphwest
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "IntelliSense [SQL Server], completing snippets"
  - "snippets [Transact-SQL], completing"
  - "Transact-SQL snippets, completing"
---
# Complete Transact-SQL snippets

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

Once a [!INCLUDE [tsql](../includes/tsql-md.md)] code snippet is inserted into a script, you edit the contents of the snippet to build a complete [!INCLUDE [tsql](../includes/tsql-md.md)] statement.

## Complete snippets

When you add a [!INCLUDE [tsql](../includes/tsql-md.md)] snippet to your script, the inserted snippet statement has one or more replacement points, which are highlighted. If you rest your mouse pointer on a replacement point, a tooltip appears with a description of the syntax element you can specify. The [!INCLUDE [ssDE](../includes/ssde-md.md)] Query Editor recognizes the snippet as separate from the surrounding script until you close the source file. The replacement points remain active until you close the source file.

You can also add additional syntax elements to the template code inserted by a snippet. For example, the Create Table snippet template generates two column definitions; you must add additional column definitions to create a table with more than two columns.

#### Complete the snippet statement

1. Use the **Tab** key to move from one replacement point to the next. Use **Shift**+**Tab** to move to the previous replacement point.

1. Select **Ctrl**+**Space** to invoke IntelliSense.

1. Select an item from the list, or type a replacement of your choice.

## Related content

- [Insert Transact-SQL Snippets](insert-transact-sql-snippets.md)
- [Insert Surround-with Transact-SQL snippets](insert-surround-with-transact-sql-snippets.md)
