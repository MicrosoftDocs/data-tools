---
title: Install GitHub Copilot
titleSuffix: GitHub Copilot in SQL Server Management Studio (Preview)
description: Learn how to install GitHub Copilot in SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 11/11/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand how to install GitHub Copilot in SQL Server Management Studio.
---
# Install GitHub Copilot in SQL Server Management Studio (Preview)

GitHub Copilot in SQL Server Management Studio (SSMS) is an AI assistant that can save you time by providing the help you need from within SSMS. GitHub Copilot in SSMS can answer questions about your database and environment, and help you write, fix, and refactor Transact-SQL (T-SQL).

## Prerequisites

To use GitHub Copilot in SSMS, you need:

- [!INCLUDE [ssms-22-md](../includes/ssms-22-md.md)]
- A GitHub account with [Copilot access](https://docs.github.com/copilot/get-started/what-is-github-copilot#getting-access-to-copilot)
- For information related to SSMS 22 installation, see [Install SQL Server Management Studio](../install/install.md).

## Install GitHub Copilot in SSMS using the Visual Studio Installer

1. Launch the Visual Studio Installer.

1. Select the installation of SSMS you want to modify, then select **Modify**.

1. Select **AI Assistance** on the Workloads tab. All workloads enabled when the AI Assistance workload is selected are required for GitHub Copilot in SSMS.

1. Select **Modify** to install the extension.

## Manage your GitHub Copilot state

In [!INCLUDE [ssms-22-md](../includes/ssms-22-md.md)] and later versions, a GitHub Copilot status icon in the upper-right corner of SSMS indicates whether GitHub Copilot is active, inactive, unavailable, or not installed. Using the dropdown menu from the status icon, you can easily access options that help manage or troubleshoot your Copilot state. Some options are available or grayed out depending on your Copilot state.

### GitHub Copilot is active

Copilot is in an active state and fully functional if you signed into a GitHub account with [Copilot access](https://docs.github.com/copilot/get-started/what-is-github-copilot#getting-access-to-copilot). Using the dropdown menu, you can open the Chat window, access Copilot settings, and manage your Copilot subscription.

### GitHub Copilot is inactive

If GitHub Copilot is installed but in an inactive state, it might be because:

- You aren't signed in to your GitHub account.
- The GitHub account with which you're signed in doesn't have an active Copilot subscription.
- Your active GitHub account doesn't have a Copilot subscription.

:::image type="content" source="media/badge-inactive.png" alt-text="Screenshot of inactive Copilot status.":::

#### Sign in to GitHub Copilot

To sign in to GitHub Copilot, select **Add another account** from the profiler card in the upper right corner of SSMS and sign in with a GitHub account that has an active subscription to use Copilot.

You can also select **Open Chat Window to Sign In** from the Copilot badge to open the Chat window. Within the Chat window, select **Sign up for Copilot Free** to sign up for Copilot Free, or **Sign in** if you already have a GitHub account with Copilot enabled.

Once you're successfully signed in to GitHub with an active Copilot subscription, the Copilot status icon updates to active.

:::image type="content" source="media/badge-active.png" alt-text="Screenshot of active Copilot status.":::

#### Your GitHub account doesn't have an active Copilot subscription

If you sign in with a GitHub account that doesn't have an active Copilot subscription, you aren't able to use Copilot. You need to sign in with a GitHub account with a Copilot subscription, or select **Get Copilot for Free** from the Chat window to sign up for Copilot Free.

If you add multiple GitHub accounts in Visual Studio, ensure the active account is the one with the active Copilot subscription.

If Copilot is inactive because the credentials need to be refreshed, select **Refresh your GitHub credentials** from the dropdown list on the Copilot badge and sign in again.

If your administrator disabled Copilot, contact your IT administrator to learn more.

## Copilot is unavailable

If GitHub Copilot is installed but unavailable for use, it might be due to network connectivity issues, server-side technical problems, or an expired service plan. In this state, Copilot doesn't provide its usual services until the external issues are resolved. For more information on diagnosing and resolving common errors with GitHub Copilot, see [Troubleshoot GitHub Copilot in SQL Server Management Studio (Preview)](troubleshoot.md).

When the issue is resolved and you're signed in with an active subscription, the Copilot status icon updates to active.

### Copilot not installed

If you didn't install the AI Assistance workload from the Visual Studio Installer, the GitHub status icon is still available in the SSMS. Use the Visual Studio Installer to [install the AI assistance workload](#install-github-copilot-in-ssms-using-the-visual-studio-installer), or select **Install Copilot** from the **GitHub Copilot** badge.

If you don't want to install GitHub Copilot, you can [Hide the Copilot badge](#hide-the-copilot-badge) to hide the Copilot status icon in SSMS.

## Disable Copilot

### Hide the Copilot badge

You can hide the GitHub Copilot badge in SSMS by disabling the **Hide Copilot menu badge** option in **Tools** > **Options** > **Environment** > **Visual Experience**.

### Uninstall GitHub Copilot in SSMS using the Visual Studio Installer

You can remove GitHub Copilot in SSMS from your SSMS installation using the Visual Studio Installer.

1. Launch the Visual Studio Installer.
1. Select the installation of SSMS from which you want to remove GitHub Copilot in SSMS, then select **Modify**.
1. Uncheck **AI Assistance** on the Workloads tab.
1. Select **Modify** to uninstall the workload.
1. Restart SSMS.

## Related content

- [Get started with GitHub Copilot in SQL Server Management Studio (Preview)](get-started.md)
- [Use the GitHub Copilot Chat experience in SQL Server Management Studio (Preview)](chat.md)
- [Use GitHub Copilot for free in SQL Server Management Studio (Preview)](free-plan.md)
- [Troubleshoot GitHub Copilot in SQL Server Management Studio (Preview)](troubleshoot.md)
