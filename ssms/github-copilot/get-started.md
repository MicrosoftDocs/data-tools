---
title: Get Started
titleSuffix: GitHub Copilot in SQL Server Management Studio (Preview)
description: Learn how to get started using GitHub Copilot in SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 10/14/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand how to get started with GitHub Copilot in SQL Server Management Studio.
---
# Get started with GitHub Copilot in SQL Server Management Studio (Preview)

Welcome to GitHub Copilot, your AI companion in SQL Server Management Studio (SSMS).

GitHub Copilot helps you write Transact-SQL (T-SQL) faster and with greater accuracy by suggesting new queries, updates to existing queries, answering questions, and assisting with administrator tasks, all directly in your SSMS environment.

In this article, you learn how to use GitHub Copilot and make the most of its features in SSMS.

## Open GitHub Copilot

Use of GitHub Copilot requires SSMS 22 Preview 3 or a later version. You should update to the latest version of SSMS to access the latest updates and features.

1. Open SSMS 22 and connect to a server or database in the query editor window.

1. Select the **GitHub Copilot** badge in the upper right corner of SSMS, and select **Open Chat Window to Sign In**.

   :::image type="content" source="media/sign-in.png" alt-text="Screenshot of GitHub Copilot badge options.":::

1. If GitHub Copilot isn't installed, select **Install Copilot** from the **GitHub Copilot** badge, or open the Visual Studio Installer and modify your SSMS installation to add the **AI Assistance** workload. For more information, see [Install GitHub Copilot in SQL Server Management Studio (Preview)](installation-state.md).

1. In the Chat window, sign in with your existing GitHub account or select **Sign up for Copilot Free**. Follow the prompts in your browser to complete the sign-in or sign-up process.

1. Once the process is complete, return to SSMS to start using Copilot.

## Use GitHub Copilot

Once you're signed in, use the Chat window to interact with your database using natural language. You can ask general questions about SQL, questions specific to a database, or get assistance writing or editing T-SQL.

If you're not connected to a database in a query editor window, the context in the Chat window is the general Copilot. It can answer general SQL questions, but without a query editor connection it can't answer database specific questions.

Open a query editor window and connect to a database. Within the Chat window, the database connection in the active editor window provides context for the prompt. GitHub Copilot in SSMS has knowledge of both the context (SQL version) and database (schema aware) from the database connection, so responses are tailored to your environment. As you navigate between open query editors, the context in the Chat window changes appropriately.

## Support

Support for GitHub Copilot Chat is provided by [GitHub](https://support.github.com).

To learn more about Copilot's security, privacy, compliance, and transparency, see the [GitHub Copilot Trust Center FAQ](https://copilot.github.trust.page/faq).

## Related content

- [Get started with GitHub Copilot in SQL Server Management Studio (Preview)](get-started.md)
- [Use GitHub Copilot for free in SQL Server Management Studio (Preview)](free-plan.md)
- [Troubleshoot GitHub Copilot in SQL Server Management Studio (Preview)](troubleshoot.md)
