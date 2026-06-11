---
title: Admin Controls
titleSuffix: GitHub Copilot in SQL Server Management Studio
description: Learn about administrative controls for GitHub Copilot in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: erinstellato
ms.date: 06/09/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As an IT administrator, I want to understand how to manage GitHub Copilot in SQL Server Management Studio for my organization.
---
# Admin controls for GitHub Copilot in SQL Server Management Studio

SQL Server Management Studio (SSMS) 22 introduces new features that enable administrators to configure and manage GitHub Copilot more effectively within their enterprise. These features provide administrators greater control over the use of Copilot within their organization.

Admins can disable Copilot for individual accounts, disable it entirely, configure an `agentExecuteAsUser` in the database `CONSTITUTION.md` to specify a particular database user or SQL login to use when interacting with a database, and configure content exclusion to prevent certain files from being available to Copilot in SSMS.

In this article, you learn how to:

- Disable Copilot
- Configure execution context
- Configure content exclusion

## Disable Copilot

With SSMS 22.4.1 and later, administrators can disable Copilot for individual accounts or disable it entirely using the Visual Studio Administrative Templates (ADMX/ADML), and you can disable Copilot Free. Preventing unexpected access ensures that your environment remains protected.

To configure and deploy these policies, you can use [Microsoft Intune](/visualstudio/install/administrative-templates#deploying-the-policies) or the [Local Group Policy Editor](/visualstudio/ide/visual-studio-github-copilot-admin#configure-copilot-group-policy) directly on the client machine.

### Configure Copilot group policy

1. Visit the Microsoft Download Center to download the [Visual Studio Group Policy Administrative Template files (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=104405). When prompted, ensure the files are saved to `C:\Windows\PolicyDefinitions`.
1. Open the **Windows Local Group Policy Editor** and navigate to **Computer Configuration** > **Administrative Templates** > **SQL Server Management Studio** > **Copilot Settings**. Select a group policy.
1. Once you select the group policy, configure it to enable or disable Copilot as needed.
1. Restart SSMS to apply the new policy changes.

### Disable Copilot in GitHub

With SSMS 22.4.1 or later versions, administrators can disable Copilot for individual accounts or for an entire organization through [GitHub Copilot settings](https://docs.github.com/copilot/concepts/about-enterprise-accounts-for-copilot-business). For Copilot Business and Enterprise subscriptions, administrators manage access through the organization or enterprise settings on GitHub.com. Individual users can be granted or revoked access to Copilot through license assignment.

For more information, see [Managing GitHub Copilot in your organization](https://docs.github.com/copilot/how-tos/administer-copilot/manage-for-organization).

### Uninstall GitHub Copilot in SSMS

If your organization requires that GitHub Copilot isn't available in SSMS, you can remove the AI Assistance workload through the Visual Studio Installer. For detailed steps, see [Uninstall GitHub Copilot in SSMS using the Visual Studio Installer](installation-state.md#uninstall-github-copilot-in-ssms-using-the-visual-studio-installer).

You can also hide the Copilot badge in SSMS without uninstalling. For more information, see [Hide the Copilot badge](installation-state.md#hide-the-copilot-badge).

### Disable Agent mode

With SSMS 22.7 or later versions, administrators can fully disable Agent mode using [Visual Studio Administrative Templates (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=104405). With this policy setting, administrators can control which AI-assisted features are available in their organization, helping ensure usage aligns with security and compliance requirements.

Policy location in the Local Group Policy Editor: **Computer Configuration** > **Administrative Templates** > **SQL Server Management Studio** > **Copilot Settings** > **Disable Agent Mode**

## Configure the GitHub Copilot execution context for a database

With SSMS 22.7 or later versions, administrators can configure execution context that ensures Copilot-generated queries run under a dedicated, least-privileged account rather than the user's own permissions. This configuration uses a database user or SQL login, specified in the database's `CONSTITUTION.md`. For more information, see [Execution context for GitHub Copilot in SQL Server Management Studio](execution-context.md).

## Configure the MCP server allow list

With SSMS 22.7, administrators can configure an allow list of approved MCP servers through the GitHub Copilot administration dashboard. When an allow list is configured, developers in the organization can only connect to MCP servers that appear on the approved list.

### How the MCP server allow list works

- Administrators specify which MCP servers are allowed within their organization by using the [GitHub Copilot enterprise policies for MCP](https://docs.github.com/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-enterprise-policies#defining-policies-for-your-enterprise). In the enterprise or organization settings, navigate to AI Controls and select MCP in the sidebar to configure MCP server policies.

- SSMS checks the allow list when a user attempts to connect to an MCP server.

- If the server is on the allow list, the connection proceeds normally.

- If the server isn't on the allow list, SSMS blocks the connection and displays an error message indicating the organization's policy doesn't permit the server.

This feature helps organizations control which MCP servers can process sensitive data and maintain compliance with security policies.

## Configure content exclusion

Content exclusion for GitHub Copilot enables administrators to prevent certain files from being available to Copilot and keep sensitive content secure from Copilot use. You can use content exclusions to configure GitHub Copilot to ignore specific files in a [repository](https://docs.github.com/copilot/how-tos/configure-content-exclusion/exclude-content-from-copilot#configuring-content-exclusions-for-your-repository) or [organization](https://docs.github.com/copilot/how-tos/configure-content-exclusion/exclude-content-from-copilot#configuring-content-exclusions-for-your-organization).

Content exclusion is available only with a GitHub Copilot Business or a GitHub Copilot Enterprise [subscription](https://docs.github.com/copilot/get-started/plans).

With SSMS 22.4.1 or later versions, GitHub Copilot in SSMS ignores excluded content. When content is excluded, completions and chat aren't available for the affected files.

### Code completions in SSMS and content exclusions

Code completions aren't available for excluded files, and excluded content isn't included in code completion suggestions for other files.

### GitHub Copilot Chat in SSMS and content exclusions

Excluded files can't be referenced in the chat window, and excluded content isn't included in GitHub Copilot responses.

## Related content

- [Install GitHub Copilot in SQL Server Management Studio](installation-state.md)
- [Manage Copilot usage in SQL Server Management Studio](manage-usage.md)
- [Use GitHub Copilot for free in SQL Server Management Studio](free-plan.md)
- [Use GitHub Copilot Agent mode (preview) in SQL Server Management Studio](agent-mode.md)
- [GitHub Copilot Trust Center](https://copilot.github.trust.page)
- [Managing GitHub Copilot in your organization](https://docs.github.com/copilot/how-tos/administer-copilot/manage-for-organization)
- [Troubleshoot GitHub Copilot in SQL Server Management Studio](troubleshoot.md)
