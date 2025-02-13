---
title: "Associate File Extensions to a Code Editor"
description: Learn how to associate a file extension to a specific code editor so that when you double-click a file with the extension it's opened by the associated editor.
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/26/2024
ms.service: sql-server-management-studio
ms.topic: conceptual
helpviewer_keywords:
  - "file extensions [SQL Server]"
  - "associating file extensions [SQL Server]"
  - "Query Editor [SQL Server Management Studio], associating file extensions"
ai-usage: ai-assisted
---

# Associate file extensions to a code editor

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

Associating file extensions to a specific code editor allows you to open a file with the appropriate SQL Server Management Studio code editor when you double-click a file in Windows Explorer. The extensions commonly used by [!INCLUDE [ssManStudio](../includes/ssmanstudio-md.md)], such as .sql and .mdx, are associated during installation. New file extensions must also be associated to [!INCLUDE [ssManStudio](../includes/ssmanstudio-md.md)] in the file system. You can use this feature to open files created with other editors, or to open files you have renamed, such as backups of .sql files that were renamed .bak.

There are two steps in the process. First associate the extension with [!INCLUDE [ssManStudio](../includes/ssmanstudio-md.md)], and then associate the extension with a specific code editor.

## To associate a new file extension with SQL Server Management Studio

1. **Open Windows Settings**: Select the Start menu and select **Settings**.

1. **Navigate to Default Apps**: In the **Settings** window, select **Apps**, then select **Default apps**.

1. **Choose Default Apps by File Type**: Scroll down and Select **Choose default apps by file type**.

1. **Find Your File Extension**: Locate the file extension you want to associate (for example, .sql).

1. **Set SSMS as Default**: Select the current default app and select SQL Server Management Studio from the list.

1. **Configure within SSMS**: Open SSMS, go to **Tools** > **Options**, and under **Text Editor**, specify the editor for the new extension if necessary.

## To associate a new file extension with a code editor in SQL Server Management Studio

1. In SQL Server Management Studio, from the **Tools** menu, select **Options**.

1. In the **Options** dialog box, select **Text Editor**, and then select **File Extension**.

1. In the **Extension** box, type your new file extension.

1. In the **Editor** box, select the code editor that you wish to use to open this file type, select **Add**, and then select **OK**.

## Related content

- [Ssms Utility](../ssms-utility.md)
