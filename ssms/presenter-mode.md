---
title: Presenter Mode in SQL Server Management Studio
description: Using presenter mode in SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 04/16/2025
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
---

# Presenter mode in SQL Server Management Studio

SQL Server Management Studio (SSMS) includes the ability to enable a presentation mode which quickly changes the font and font size for improved visibility when demonstrating features and functionality.

## Use presenter mode

Presenter mode is enabled or disabled from **View > Presenter Mode > Toggle Presenter Mode**, or with the **Ctrl+Shift+F5** keyboard command.

> [!NOTE]  
> The keyboard command to enable or disable presenter mode can't be customized.

Presenter mode can also be enabled or disabled from the **Search menu**, which is available on the main SSMS toolbar. Within the **Feature Search** window, enter any portion of the command `Toggle Presenter Mode` to enable or disable presenter mode.

## Edit presenter mode settings

The font family and font size for presenter mode can be changed from **View > Presenter Mode > Edit Presenter Mode Settings**, or using the **Search menu** and entering any portion of the command `Edit Presenter Mode Settings` in the **Feature Search** window. The settings are edited in an XML file, and the font and size for both the environment and text editor can be changed.

To reset the presenter mode settings to their default values, select **View > Presenter Mode > Restore Default Font Settings**, or use the **Search menu** and enter any portion of the command `Restore Default Font Settings` in the **Feature Search** window.

## Related content

- [The SQL Server Management Studio Environment](the-sql-server-management-studio-environment.md)
