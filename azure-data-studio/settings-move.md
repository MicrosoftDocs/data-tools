---
title: Move user settings
description: Learn how to move user settings.
author: dlevy-msft
ms.author: dlevy
ms.reviewer: maghan, randolphwest
ms.date: 10/17/2023
ms.service: azure-data-studio
ms.topic: how-to
---

# Move user settings

If you're updating SQL Operations Studio to Azure Data Studio and want to keep your settings, keyboard shortcuts, or code snippets, complete the following steps:

> [!NOTE]  
> If you've already installed Azure Data Studio or you've never installed or customized SQL Operations Studio, you can ignore this section.

1. On the left pane, select **Manage** (gear icon) and then select **Settings.**

   :::image type="content" source="./media/download/open-settings.png" alt-text="Screenshot of the Azure Data Studio Manage icon and Settings command.":::

1. At the top, right-click the **User Settings** tab, and then select **Reveal in Explorer**.

   :::image type="content" source="./media/download/reveal-in-explorer.png" alt-text="Screenshot of the Reveal in Explorer command in the User Settings tab.":::

1. Copy all files in this folder and save them in an easy-to-find location on your local drive, such as your *Documents* folder.

   :::image type="content" source="./media/download/copy-settings.png" alt-text="Screenshot of the settings.json file in the Windows Explorer folder structure.":::

1. In your updated version of Azure Data Studio, follow steps 1 and 2 and then, for step 3, paste the contents you saved into the folder. You can also manually copy over the settings, key bindings, or snippets in their respective locations.

1. If you're overriding your current installation, before you do so, delete the old installation directory to avoid errors connecting to your Azure account for the resource explorer.

## Related content

- [Modify User and Workspace settings](settings.md)
- [User and Workspace settings](settings-list.md)
