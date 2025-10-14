---
title: Use GitHub Copilot for Free
titleSuffix: GitHub Copilot in SQL Server Management Studio (Preview)
description: Learn how to use GitHub Copilot for free in SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 10/14/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand how to use GitHub Copilot for free in SQL Server Management Studio.
---
# Use GitHub Copilot for free in SQL Server Management Studio (Preview)

GitHub Copilot Free enables you to experience AI-powered assistance in SQL Server Management Studio (SSMS) by providing limited access to Copilot features including Chat.

## Prerequisites

To get started with Copilot Free in SSMS, you need:

- [!INCLUDE [ssms-22-md](../includes/ssms-22-md.md)]
- [GitHub Copilot in SQL Server Management Studio (Preview)](installation-state.md)

[!INCLUDE [ssms-22-md](../includes/ssms-22-md.md)] is the preview version of SQL Server Management Studio (SSMS). For information related to SSMS 22 installation, see [Install SQL Server Management Studio Preview](../install/install-preview.md).

## Get started with Copilot Free in SSMS

With [!INCLUDE [ssms-22-md](../includes/ssms-22-md.md)], you can sign up for Copilot Free from the Copilot Chat window.

1. Select **Open Chat Window to Sign In** from the Copilot badge, or use <kbd>Ctrl</kbd>+<kbd>\\</kbd>, <kbd>Ctrl</kbd>+<kbd>C</kbd> to open the Chat window.

1. Select **Sign up for Copilot Free** or **Sign up with Google**.

1. If you have an existing GitHub account, sign in when prompted. If not, follow the steps to create a new GitHub account.

1. Once finished, you're redirected back to SSMS.

## Copilot Free usage limits in SSMS

Copilot Free provides a limited number of chat responses for free per month. When you reach your monthly usage limit for chat, you get a notification and notice a change in Copilot functionality.

You can check your free tier status anytime by selecting **Copilot Free Status** from the Copilot badge dropdown list in the top-right corner of SSMS. You can also check the current status of your Copilot Free account on the GitHub account settings page.

### Usage limit reached

When you reach the usage limits, your Copilot experience in SSMS might be affected.

| Usage limit reached | Result |
| --- | --- |
| **Chat** | User no longer receives chat responses when sending prompts. The Copilot badge stays green, indicating active status. |

When you reach usage limits for Copilot Free, you can wait for them to reset at the end of the monthly cycle or upgrade to Copilot Pro to continue using Copilot.

## Frequently asked questions

### Who can access Copilot Free?

Copilot Free isn't available if you have an Enterprise Managed Users (EMU) account, access to a Copilot license through an organization, an existing Copilot Pro subscription or trial, or free access to Copilot Pro as a student, teacher, or open-source maintainer. For the latest information, see [About GitHub Copilot Free](https://aka.ms/ghdocscopilotfreepage).

### Can I block suggestions matching public code with Copilot Free?

Yes. You can configure these settings from the [GitHub Copilot Settings](https://github.com/settings/copilot/features) page.

### What Copilot features are included in Copilot Free?

Copilot Free includes Copilot Chat. Learn more at [About GitHub Copilot Free](https://aka.ms/ghdocscopilotfreepage).

### What are the Copilot Free limits for Chat?

For more information, see [About GitHub Copilot Free](https://aka.ms/ghdocscopilotfreepage).

## Related content

- [Get started with GitHub Copilot in SQL Server Management Studio (Preview)](get-started.md)
- [Use the GitHub Copilot Chat experience in SQL Server Management Studio (Preview)](chat.md)
