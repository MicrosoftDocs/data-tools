---
title: Manage Usage
titleSuffix: GitHub Copilot in SQL Server Management Studio
description: Learn how to manage model use in the GitHub Copilot Chat experience in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: erinstellato
ms.date: 04/14/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand how to use GitHub Copilot Chat in SQL Server Management Studio.
---
# Manage Copilot usage in SQL Server Management Studio

GitHub Copilot includes built-in tools to help you track usage, manage your plan, and understand how model selection affects [request consumption](https://docs.github.com/copilot/concepts/billing/copilot-requests).

## View Copilot usage

To track your Copilot usage:

1. Select the Copilot badge in the top-right corner of SQL Server Management Studio (SSMS).

1. To view the Copilot Usage dialog, select **Copilot Usage**.

1. The dialog shows current use and the number of remaining requests. Select **Get more requests** to manage your Copilot spend on [GitHub](https://github.com/settings/billing/budgets).

> [!NOTE]  
> GitHub manages billing and subscriptions. For more information, see your [GitHub settings](https://github.com/settings/billing/summary).

## Understand model selection

GitHub Copilot supports multiple AI models, and each model consumes requests at different rates based on assigned [multipliers](https://docs.github.com/copilot/concepts/billing/copilot-requests#model-multipliers).

To view or change your current model:

1. Open the chat window from the Copilot badge, or select **View** > **GitHub Copilot Chat**.
1. To select a model, use the model picker dropdown list above the input field.

When your [premium request quota](https://docs.github.com/copilot/get-started/plans#comparing-copilot-plans) runs out, Copilot automatically falls back to a base model so you can continue working without interruption.

> [!TIP]  
> Visit your [Copilot settings on GitHub](https://github.com/settings/copilot/features) to explore model options and subscription details.

## Related content

- [AI models for GitHub Copilot in SQL Server Management Studio](ai-models.md)
- [AI model comparison](https://docs.github.com/copilot/reference/ai-models/model-comparison)
- [Hosting of models for GitHub Copilot Chat](https://docs.github.com/copilot/reference/ai-models/model-hosting)
- [Requests in GitHub Copilot](https://docs.github.com/copilot/concepts/billing/copilot-requests#premium-requests)
- [GitHub Copilot billing](https://docs.github.com/copilot/concepts/billing/billing-for-individuals)
- [GitHub support](https://support.github.com/request/landing)
- [Get started with GitHub Copilot in SQL Server Management Studio](get-started.md)
