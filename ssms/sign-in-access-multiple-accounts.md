---
title: Access Multiple Accounts in SQL Server Management Studio
description: Learn how access multiple accounts in SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, mbarickman
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---
# Access multiple accounts in SQL Server Management Studio

In this article, you learn how to access multiple accounts in SQL Server Management Studio (SSMS). After you sign in to SSMS with a Microsoft or an organizational account, you can see the resources accessible from your accounts in places such as the **Azure Storage** dialog or the **Add Azure firewall rule** dialog.

## Access your Azure account via the Azure Storage dialog

1. Open Object Explorer using **View** > **Object Explorer**.
1. From the **Connect** dropdown list, select **Azure Storage**.
1. In the **Connect to a Microsoft subscription** dialog, select the **Change User** button.
1. In the **Select a Microsoft account** dialog, use the dropdown list to select a different account, or do add a new account.
1. Once you choose an account, select **OK**.

   The available values for **Select Storage Account** and **Select Blob Container** updates are based on the account selected.

## Related content

- [Sign in or switch user accounts in SQL Server Management Studio](sign-in.md)
