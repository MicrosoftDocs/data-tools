---
title: Create and customize keyboard shortcuts
description: Learn how to view, edit, and create keyboard shortcuts in Azure Data Studio, using a capability based on the one in Visual Studio Code.
author: "markingmyname"
ms.author: "maghan"
ms.reviewer: erinstellato, maghan
ms.date: 05/14/2024
ms.service: azure-data-studio
ms.topic: how-to
ms.custom:
  - updatefrequency5
---

# Keyboard shortcuts in Azure Data Studio

This article provides the steps to quickly view, edit, and create keyboard shortcuts in Azure Data Studio.

Because Azure Data Studio inherits its key binding functionality from Visual Studio Code, detailed information about advanced customizations, using different keyboard layouts, etc., is in the [Key Bindings for Visual Studio Code](https://code.visualstudio.com/docs/getstarted/keybindings) article. Some key binding features might not be available (for example, Keymap extensions aren't supported in Azure Data Studio).

## Open the Keyboard Shortcuts editor

To view all currently defined keyboard shortcuts:

Open the **Keyboard Shortcuts** editor from the **File** menu: **File** > **Preferences** > **Keyboard Shortcuts** (**Azure Data Studio** > **Preferences** > **Keyboard Shortcuts** on Mac).

In addition to displaying current key bindings, the **Keyboard Shortcuts** editor lists the available commands that don't have keyboard shortcuts defined. The **Keyboard Shortcuts** editor enables you to easily change, remove, reset, and define new key bindings.

## Edit existing keyboard shortcuts

To change the key binding for an existing keyboard shortcut:

1. Locate the keyboard shortcut you want to change by using the search box or scrolling through the list.
   > [!TIP]  
   > Search by key, by command, by source, etc. to return all relevant keyboard shortcuts.

1. Right-click the desired entry and select **Change Key binding**

   :::image type="content" source="media/keyboard-shortcuts/change-keybinding.png" alt-text="Screenshot of edit keyboard shortcut in Azure Data Studio." lightbox="media/keyboard-shortcuts/change-keybinding.png":::

1. Press the desired combination of keys, then press **Enter** to save it.

   :::image type="content" source="media/keyboard-shortcuts/save-keybinding.png" alt-text="Screenshot of save keyboard shortcut in Azure Data Studio." lightbox="media/keyboard-shortcuts/save-keybinding.png":::

## Create new keyboard shortcuts

To create new keyboard shortcuts:

1. Right-click a command that doesn't have any key binding and select **Add Key binding**.

   :::image type="content" source="media/keyboard-shortcuts/add-keybinding.png" alt-text="Screenshot of Create keyboard shortcut in Azure Data Studio." lightbox="media/keyboard-shortcuts/add-keybinding.png":::

1. Press the desired combination of keys, then press **Enter** to save it.

## Reset keyboard shortcuts to default

1. Open Azure Data Studio: Launch Azure Data Studio on your computer.

1. Access Keyboard Shortcuts: Go to the menu bar and select on "File." From the dropdown list menu, select "Preferences" and then select on "Keyboard Shortcuts." Alternatively, you can use the keyboard shortcut Ctrl + K Ctrl + S to directly access the Keyboard Shortcuts editor.

1. Reset to Default: In the Keyboard Shortcuts editor, you'll see a search bar at the top. If you've made customizations and want to reset everything to default, simply select on the three dots (ellipsis) icon at the top-right corner of the editor. From the dropdown list menu, select "Reset Keybinding to Default." Confirm the action if prompted.

1. Save Changes (if required): If you're prompted to save changes before resetting, make sure to do so if you want to retain any customizations you've made before proceeding with the reset.

1. Restart Azure Data Studio (if required): In some cases, Azure Data Studio might require a restart for the changes to take effect. If prompted or if you notice any inconsistencies, close and reopen Azure Data Studio.

## Related content

- [Key Bindings for Visual Studio Code](https://code.visualstudio.com/docs/getstarted/keybindings)
- [Keyboard Shortcuts Reference](https://code.visualstudio.com/docs/getstarted/keybindings#_keyboard-shortcuts-reference)
