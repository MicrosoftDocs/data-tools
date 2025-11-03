---
title: Customize Menus and Shortcut Keys
description: Customize menus and shortcut keys with keyboard accelerators.
author: rwestMSFT
ms.author: randolphwest
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Management Studio [SQL Server], shortcuts"
  - "keyboard shortcuts [SQL Server Management Studio]"
  - "menu shortcuts [SQL Server Management Studio]"
  - "shortcuts [SQL Server Management Studio], customizing"
  - "hot keys [SQL Server Management Studio]"
  - "keyboard shortcuts [SQL Server Management Studio], customizing"
  - "customizing shortcut keys [SQL Server]"
  - "customizing menus [SQL Server]"
  - "accelerator keys"
---

# Customize menus and shortcut keys

[!INCLUDE [SQL Server Azure SQL Database Azure SQL Managed Instance Synapse Analytics PDW Fabric SE Fabric DW Fabric SQL DB](includes/applies-to-version/sql-asdb-asdbmi-asa-pdw-fabricse-fabricdw-fabricsqldb.md)]

A keyboard accelerator allows you to select a menu command or button by pressing **Alt**+*\<single letter>*. For example, to open the **Edit** menu, press **Alt**+**E**. You can rearrange and modify toolbar buttons, menus, and menu commands by using the **Customize** dialog box. Instructions are provided for changing the settings using the mouse and using only the keyboard.

Keyboard accelerators for stored procedures using the Ctrl key can be created from the **Keyboard** page of the **Tools**/**Options** dialog box.

> [!NOTE]  
> Select **Collapse All** at the top of this page to show only the headings.

## Open the Keyboard Accelerator dialog box using the mouse

1. On the **Tools** menu, select **Customize**.

1. Make sure the toolbar you want to change is visible.

   1. In the **Customize** dialog box, select the **Toolbars** tab.

   1. Select the check box for the toolbar you want to display.

1. In the **Customize** dialog box, select the **Commands** tab.

## Change a toolbar buttons accelerator key using the mouse

1. Select the button on the toolbar.

1. In the **Customize** dialog box, on the **Commands** tab, select **Modify Selection**.

1. In the **Name** box on the shortcut menu, type a name for the toolbar button with an ampersand (&) before the letter that you want as the keyboard accelerator.

1. Press **Enter**.

1. In the **Customize** dialog box, select **Close**.

## Change a menu commands accelerator key using the mouse

1. Select the menu name on the menu bar or toolbar.

1. Select the menu command.

1. In the **Customize** dialog box, select **Modify Selection**.

1. In the **Name** box on the shortcut menu, type a name for the menu command with an ampersand (&) before the letter that you want as the keyboard accelerator.

1. Press **Enter**.

1. In the **Customize** dialog box, select **Close**.

## Open the keyboard accelerator dialog box using the keyboard

1. Press **Alt**+**T**, and then type **C**, to open the **Customize** dialog box.

1. Make sure the toolbar you want to change is visible.

   1. In the **Customize** dialog box, press **Alt**+**B** to show the **Toolbars** tab.

   1. Use the arrow keys to select the toolbar you want to display, then **Space** to select the check box.

1. In the **Customize** dialog box, press **Alt**+**C** to display the **Commands** tab.

## Change a toolbar buttons accelerator key using the keyboard

1. Press **Alt**+**R** to display the **Rearrange Commands** dialog box.

1. In the **Rearrange Commands** dialog box, use the arrow keys to select **Toolbar**.

1. Tab to the **Toolbar** list, and use the arrow keys to select the toolbar that contains the button you want to change, and then press **Enter**.

1. Tab to the **Controls** list, and use the arrow keys to select the button you want to change.

1. Press **Alt**+**M**, to select **Modify Selection**.

1. Tab to the **Name** box on the shortcut menu, type a name for the toolbar button with an ampersand (&) before the letter that you want as the keyboard accelerator.

1. Press **Enter**.

1. Tab to the **Close** button, and then press **Enter**.

## Change a menu commands accelerator key using the keyboard

1. Press **Alt**+**R** to display the **Rearrange Commands** dialog box.

1. Tab to **Menu Bar** and then use the arrow keys to select the menu you want in the **Menu Bar** list, and then press **Enter**.

1. Tab to the **Controls** list, and use the arrow keys to select the button you want to change.

1. Press **Alt**+**M**, to select **Modify Selection**.

1. Tab to the **Name** box on the shortcut menu, and type a name for the toolbar button with an ampersand (&) before the letter that you want as the keyboard accelerator.

1. Press **Enter**.

1. In the **Customize** dialog box, select **Close**.

## Create a keyboard accelerator for a stored procedure

1. On the **Tools** menu, select **Options**.

1. On the **Keyboard** page, select an unused keyboard combination in the **Shortcut** list.

1. In the **Stored Procedure** box, type the stored procedure name, and then select **OK**.

## Add a new item to the menu

1. On the **Tools** menu, select **Options**.

1. In the **Customize** dialog box, on the **Commands** tab, select **New Menu**.

1. On the **Commands** box, drag **New Menu** to the menu bar and drop it where you want the new menu to appear.

1. On the menu, right-click **New Menu**, and in the **Name** box, type a name for the new menu.

1. In the **Customize** dialog box, select category such as **File**, and select a command such as **Open File**. Drag the command to the new menu. As you point to the new menu, the menu expands. Drop the command onto the expanded menu.

1. In the **Customize** dialog box, select **Close**.

> [!NOTE]  
> Some commands are available only when SQL Server Management Studio is displaying relevant content. If no commands on the menu are available, the menu item isn't available.

## Related content

- [What is SQL Server Management Studio (SSMS)?](sql-server-management-studio-ssms.md)
