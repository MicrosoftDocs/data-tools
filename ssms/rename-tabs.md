---
title: Rename Tabs in SQL Server Management Studio
description: Learn how to customize tab names in SQL Server Management Studio (SSMS) by renaming them.
author: mbarickman
ms.author: mbarickman
ms.reviewer: randolphwest
ms.date: 06/24/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---
# Rename tabs

[!INCLUDE [sql-asdb-asdbmi-asa](includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

In this article, you learn how to customize `.sql` tab names in [!INCLUDE [ssms-21-md](includes/ssms-21-md.md)] and later versions.

## Rename a tab

To rename a tab, right-click any unsaved `.sql` tab and select **Rename tab**. Enter your custom name and select **OK**. You can continue to rename the tab as long as the `.sql` file remains unsaved.

> [!NOTE]  
> Special characters such as `\`, `/`, `:`, `*`, `?`, `"`, `<`, and `>` aren't allowed.

## Save your .sql file

When you save a renamed tab, the custom name automatically populates the **File Name** field in the **Save File As...** dialog. Once a file is saved, the tab displays the file name and the **Rename** feature is no longer available. To change the file name and corresponding tab name, go to **File** > **Save As...** and rename the file.

## Related content

- [Customize (Toolbars page)](menu-help/customize-toolbars-page.md)
- [Customize menus and shortcut keys](customize-menus-and-shortcut-keys.md)
- [Workaround to move tabs](troubleshoot/workaround-move-tabs.md)
