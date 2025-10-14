---
title: Troubleshoot GitHub Copilot
titleSuffix: GitHub Copilot in SQL Server Management Studio (Preview)
description: Learn how to troubleshoot GitHub Copilot in SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 10/14/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand how to troubleshoot issues with GitHub Copilot in SQL Server Management Studio.
---
# Troubleshoot GitHub Copilot in SQL Server Management Studio (Preview)

This troubleshooting guide includes steps for resolving issues with GitHub Copilot in SQL Server Management Studio (SSMS) 22 (Preview) or later. Some issues related to GitHub Copilot might require assistance from an administrator or your network team.

GitHub Copilot is a separate subscription managed by GitHub. For questions regarding GitHub Copilot subscriptions and support, see [Individual subscriptions](https://docs.github.com/copilot/how-tos/manage-your-account/get-started-with-a-copilot-plan) or [Business subscriptions](https://docs.github.com/copilot/how-tos/administer-copilot/manage-for-organization/manage-plan/subscribe).

## GitHub Copilot authentication

If you experience authentication issues after installing the AI Assistance workload in the Visual Studio Installer, see [Troubleshooting common issues with GitHub Copilot](https://docs.github.com/copilot/how-tos/troubleshoot-copilot/troubleshoot-common-issues).

## GitHub Copilot is offline

If the GitHub Copilot badge in the upper-right corner of SSMS displays the message **Copilot is temporarily unreachable**, it means GitHub Copilot is currently offline.

GitHub Copilot might be offline due to one of the following reasons:

- Network issues
- Copilot service being unavailable
- Credentials requiring a refresh
- Copilot being disabled

If you're running into an issue not in this list, report your problem to us.

### Network issues

If your network is down, GitHub Copilot might not be able to connect.

**Action:** Ensure you have a stable internet connection. For more information, see [Troubleshooting network errors for GitHub Copilot](https://docs.github.com/copilot/how-tos/troubleshoot-copilot/troubleshoot-network-errors).

### Copilot service is unavailable

The GitHub Copilot service might be temporarily down.

**Action:** Wait for the service to come back online. You can check the status on [GitHub Status](https://www.githubstatus.com/).

### Refresh your credentials

Occasionally, you might need to refresh your credentials due to expected timeouts.

**Action:** Select **Refresh your credentials** from the Copilot badge in the upper right corner of your SSMS environment to reauthenticate your GitHub account and sign in again.

> [!NOTE]  
> If you don't see the option to refresh your credentials for the GitHub account in the All Accounts window, you can resolve this issue by removing and then adding your GitHub account again. For more information, see the [Developer Community ticket](https://developercommunity.visualstudio.com/t/Copilot-badge-refresh-credentials-not-wo/10667230?q=refresh+credentials) related to this issue.

### Copilot is disabled

Your administrator can [disable GitHub Copilot](/visualstudio/ide/visual-studio-github-copilot-admin) for an individual or any Copilot license.

**Action:** Contact your IT department to confirm whether your administrator disabled Copilot.

## Send feedback

- Report a problem to us from SSMS (**Help** > **Send Feedback** > **Report a Problem...**) or the Visual Studio Installer. The built-in feedback tool from both applications allows you to easily add diagnostic information that helps the SSMS team troubleshoot and fix issues.

- Suggest a feature, track product issues, and find answers in the [SSMS Developer Community](https://aka.ms/ssms-feedback).

## Related content

- [Install GitHub Copilot in SQL Server Management Studio (Preview)](installation-state.md)
- [Use GitHub Copilot for free in SQL Server Management Studio (Preview)](free-plan.md)
