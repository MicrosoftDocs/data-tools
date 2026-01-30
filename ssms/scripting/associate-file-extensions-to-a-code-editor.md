---
title: "Associate File Extensions with a Code Editor"
description: Learn how to associate a file extension to a specific code editor, so that the file is opened by the associated editor.
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/30/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "file extensions [SQL Server]"
  - "associating file extensions [SQL Server]"
  - "Query Editor [SQL Server Management Studio], associating file extensions"
ai-usage: ai-assisted
---

# Associate file extensions with a code editor

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

When you associate file extensions with a specific code editor, you can open a file by double-clicking it in File Explorer and it opens in the appropriate [!INCLUDE [ssManStudio](../includes/ssmanstudio-md.md)] (SSMS) code editor.

The SSMS installation process associates common extensions it uses, such as `.sql` and `.mdx`. To associate new file extensions with SSMS, you must do so in the file system. Use this feature to open files created with other editors or to open files you renamed, such as backups of `.sql` files that you renamed `.bak`.

The process has two steps. First, associate the extension with SSMS. Then, associate the extension with a specific code editor.

## Associate a new file extension with SQL Server Management Studio

1. **Open Windows Settings**: Select the Start menu and select **Settings**.

1. **Navigate to Default Apps**: In the **Settings** window, select **Apps**, and then select **Default apps**.

1. **Choose Default Apps by File Type**: Scroll down and select **Choose default apps by file type**.

1. **Find Your File Extension**: Locate the file extension you want to associate (for example, `.sql`).

1. **Set SSMS as Default**: Select the current default app and select SQL Server Management Studio from the list.

1. **Configure within SSMS**: Open SSMS, go to **Tools** > **Options**, and under **Text Editor**, specify the editor for the new extension if necessary.

## Associate a new file extension with a code editor in SQL Server Management Studio

1. In SQL Server Management Studio, from the **Tools** menu, select **Options**.

1. In the **Options** dialog box, select **Text Editor**, and then select **File Extension**.

1. In the **Extension** box, type your new file extension.

1. In the **Editor** box, select the code editor that you want to use to open this file type, select **Add**, and then select **OK**.

## Related content

- [Open SQL Server Management Studio from a command prompt](../ssms-utility.md)
