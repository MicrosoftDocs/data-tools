---
title: Admin Controls
titleSuffix: GitHub Copilot in SQL Server Management Studio
description: Learn about administrative controls for GitHub Copilot in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: erinstellato
ms.date: 04/14/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As an IT administrator, I want to understand how to manage GitHub Copilot in SQL Server Management Studio for my organization.
---
# Admin controls for GitHub Copilot in SQL Server Management Studio

Administrators can configure and manage GitHub Copilot in SQL Server Management Studio (SSMS) to align with organizational security and compliance requirements. These controls help ensure that Copilot usage follows your organization's policies.

## Disable Copilot

Administrators can disable GitHub Copilot for individual accounts or for an entire organization through [GitHub Copilot settings](https://docs.github.com/copilot/how-tos/administer-copilot/manage-for-organization/manage-plan/subscribe).

For Copilot Business and Enterprise subscriptions, administrators manage access through the organization or enterprise settings on GitHub.com. Individual users can be granted or revoked access to Copilot through license assignment.

For more information, see [Managing GitHub Copilot in your organization](https://docs.github.com/copilot/how-tos/administer-copilot/manage-for-organization).

## Uninstall GitHub Copilot in SSMS

If your organization requires that GitHub Copilot isn't available in SSMS, you can remove the AI Assistance workload through the Visual Studio Installer. For detailed steps, see [Uninstall GitHub Copilot in SSMS using the Visual Studio Installer](installation-state.md#uninstall-github-copilot-in-ssms-using-the-visual-studio-installer).

You can also hide the Copilot badge in SSMS without uninstalling. For more information, see [Hide the Copilot badge](installation-state.md#hide-the-copilot-badge).

## Manage model availability

For Copilot Enterprise and Business subscriptions, administrators must enable the Preview policy in [Copilot settings on GitHub.com](https://github.com/settings/copilot) before preview models are available in SSMS.

For more information about available models, see [AI models for GitHub Copilot in SQL Server Management Studio](ai-models.md).

## Block suggestions matching public code

Administrators and individual users can configure GitHub Copilot to block code suggestions that match publicly available code. This setting is managed through the [GitHub Copilot settings](https://github.com/settings/copilot/features) page.

## Interaction data and model training

Starting **April 24, 2026**, interaction data from Copilot Free, Pro, and Pro+ users is used to train and improve GitHub Copilot's AI models unless they opt out. Interaction data includes inputs sent to Copilot, accepted or modified outputs, code context, and feedback on suggestions.

> [!IMPORTANT]  
> **Copilot Business and Copilot Enterprise users are not affected by this change.** Interaction data from Business, Enterprise, or enterprise-owned repositories isn't used for model training.

Users can opt out of data collection for model training in their [GitHub Copilot settings](https://github.com/settings/copilot) under **Privacy**. If a user previously opted out, their preference is preserved.

For more information, see the [GitHub blog post on interaction data usage policy updates](https://github.blog/news-insights/company-news/updates-to-github-copilot-interaction-data-usage-policy/).

## Enterprise deployment

For enterprise environments, SSMS supports offline installation layouts for deployment through System Center Configuration Manager (SCCM), Intune, or other management tools. Administrators can control which workloads (including AI Assistance) are included in the deployment.

For more information, see [Create an offline installation of SQL Server Management Studio](../install/create-offline.md).

## Related content

- [Install GitHub Copilot in SQL Server Management Studio](installation-state.md)
- [Manage Copilot usage in SQL Server Management Studio](manage-usage.md)
- [Use GitHub Copilot for free in SQL Server Management Studio](free-plan.md)
- [GitHub Copilot Trust Center](https://copilot.github.trust.page)
- [Managing GitHub Copilot in your organization](https://docs.github.com/copilot/how-tos/administer-copilot/manage-for-organization)
- [Troubleshoot GitHub Copilot in SQL Server Management Studio](troubleshoot.md)
