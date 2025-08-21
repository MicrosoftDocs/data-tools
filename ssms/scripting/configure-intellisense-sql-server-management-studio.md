---
title: "Configure IntelliSense (SQL Server Management Studio)"
description: Most IntelliSense options are on by default. Learn how you can turn off an IntelliSense option and invoke it instead through a menu command or keystroke combination.
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/15/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "Options [SQL Server Management Studio], IntelliSense"
  - "modifying IntelliSense options"
  - "IntelliSense [SQL Server], modifying options"
---

# Configure IntelliSense (SQL Server Management Studio)

[!INCLUDE [sql-asdb-asdbmi](../includes/applies-to-version/sql-asdb-asdbmi.md)]

Most [!INCLUDE [msCoName](../includes/msconame-md.md)] IntelliSense options are on by default. You can turn off an IntelliSense option and instead invoke it through a menu command or keystroke combination.

> [!IMPORTANT]  
> Some changes don't take effect in your current editor session. You must open a new Transact-SQL editor session to see the change.

## Turn off statement completion options by default

> [!NOTE]  
> Azure Synapse Analytics doesn't support IntelliSense.

1. On the **Tools** menu, select **Options**.

1. Expand **Text Editor**, expand either **All Languages**, **Transact-SQL**, or **XML**, and then select **General**.

1. Clear the check boxes for the Statement completion options that you don't want, and then select **OK**.

## Modify Transact-SQL IntelliSense options

1. On the **Tools** menu, select **Options**.

1. Expand **Text Editor**, expand **Transact-SQL**, and then select **IntelliSense**.

1. Clear the check boxes for the IntelliSense options that you don't want.

1. To change the script size at which IntelliSense features are displayed, select a size from the **Maximum script size** list.

1. To change the casing applied to function names in completion lists, select a casing specification from the **Casing for built-in function names** list.

1. Select **OK**.
