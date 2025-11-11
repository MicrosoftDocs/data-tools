---
title: AI Models
titleSuffix: GitHub Copilot in SQL Server Management Studio (Preview)
description: Learn how to select different models in the GitHub Copilot Chat experience in SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 11/11/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand how to use GitHub Copilot Chat in SQL Server Management Studio.
---
# Get started with AI models in the GitHub Copilot Chat experience in SQL Server Management Studio (Preview)

With [!INCLUDE [ssms-22-md](../includes/ssms-22-md.md)], GitHub Copilot in SSMS uses GPT-4.1 as the default model to provide fast response times, high-quality suggestions, and improve efficiency for coding tasks.

However, you're not limited to using this model. You can also select a different model that best fits your requirements.

## Available models

Choose from a curated set of models in the model picker:

- GPT-5
- Claude Sonnet 3.5
- Claude Sonnet 4
- Claude Sonnet 4.5
- Claude Haiku 4.5
- Gemini 2.5 Pro
- GPT-4.1
- GPT-5 mini
- GPT-4o

Model selection capabilities include:

- Persistent selection: The model that you choose remains selected across chat threads.

- Ability to enable models directly: If a model is available in your plan but not yet enabled, you see a prompt in the model picker to activate it.

- Model availability depends on your Copilot subscription and the current status of each model. For Copilot Enterprise and Business, administrators must enable the Preview policy in Copilot settings before models are available in SSMS.

## Related content

- [AI model comparison](https://docs.github.com/copilot/reference/ai-models/model-comparison)
- [Requests in GitHub Copilot](https://docs.github.com/copilot/concepts/billing/copilot-requests#premium-requests)
- [GitHub Copilot billing](https://docs.github.com/copilot/concepts/billing/billing-for-individuals)
- [GitHub support](https://support.github.com/request/landing)
- [Manage Copilot usage and models in SQL Server Management Studio (Preview)](usage-models.md)
