---
title: AI Models
titleSuffix: GitHub Copilot in SQL Server Management Studio (Preview)
description: Learn how to select different models in the GitHub Copilot Chat experience in SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 01/21/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to make models available for GitHub Copilot in SQL Server Management Studio.
---
# Get started with AI models in the GitHub Copilot Chat experience in SQL Server Management Studio (Preview)

With [!INCLUDE [ssms-22-md](../includes/ssms-22-md.md)], GitHub Copilot in SSMS selects a default model to provide fast response times, high-quality suggestions, and improve efficiency for coding tasks. The default model varies based on your subscription.

However, you're not limited to using this model. You can also select a different model that best fits your requirements.

## Available models

Choose from a curated set of models in the model picker, such as:

- GPT-5
- GPT-5 mini
- GPT-5.1
- GPT-5.1 Codex
- GPT-5.1 Codex mini
- GPT-5.1 Codex max
- GPT-4.1
- GPT-4o
- Claude Sonnet 4
- Claude Sonnet 4.5
- Claude opus 4.5
- Claude Haiku 4.5
- Gemini 2.5 Pro

Model availability depends on your Copilot subscription and the current status of each model. For Copilot Enterprise and Business, administrators must enable the Preview policy in Copilot settings before models are available in SSMS.

## Bring your own model (BYOM)

You can add your own language model to Copilot Chat by providing API keys from providers such as Azure, OpenAI, Anthropic, and more. This option allows you to configure and access a custom set of models.

### Benefits

When you use your own model, you can:

- Expand model selection beyond built-in options, including new or experimental models.
- Pick models that meet your infrastructure, security, or performance needs.
- Control and monitor API usage directly with a specific provider.
- Easily switch between built-in and custom models.

### Add a custom model

You can add a custom model from the GitHub Copilot chat window.

1. In the chat view, go to the model picker dropdown list and select **Manage Models**.

1. Select your provider from the dropdown list. The following providers are currently supported:
   1. OpenAI
   1. Anthropic
   1. Google
   1. xAI
   1. Azure
   1. Foundry Local

1. Enter your API key value.

1. Select the appropriate item, or enter the necessary information, based on your API key.

1. Confirm that the custom model appears in the model picker.

1. Send a prompt in a chat; Copilot Chat uses the custom model.

### Add a custom model for Azure

To add a model that is provisioned in Azure OpenAI, you need the deployment and endpoint information.

1. In the chat view, go to the model picker dropdown list and select **Manage Models**.

1. Select Azure from the provider dropdown list.

1. Enter your API key value.

1. Enter the required information for your Azure OpenAI resource.
   1. The **Display Name** defines how the model appears in the model picker dropdown list in the chat view.
   1. The **Model ID** is the name of the deployment.
   1. The **Resource Endpoint** is the URL for the endpoint (for example, `https://ghcp-ssms-endpoint.openai.azure.com/`)

1. Select **Add** to add the model.

1. Select **Save** to close the dialog.

For more information on model deployment in Azure OpenAI, see [Create and deploy an Azure OpenAI in Azure AI Foundry Models resource](/azure/ai-services/openai/how-to/create-resource).

### Edit a custom model

You can edit selected settings for a model from the GitHub Copilot chat window.

1. In the chat view, go to the model picker dropdown list and select **Manage Models**.
1. In the **Bring Your Own Model** dialog, hover over the display name of the model you want to modify.
1. To expand the model details, select the chevron to the right of the model's display name.
1. Make the necessary changes to the options, and select **Save** to apply the changes.

### Delete a custom model

You can delete a model from the list of custom models in the GitHub Copilot chat window.

1. In the chat view, go to the model picker dropdown list and select **Manage Models**.
1. In the **Bring Your Own Model** dialog, hover over the display name of the model you want to modify.
1. To expand the model details, select the chevron to the right of the model's display name.
1. Select **Delete model** to remove the model.

### Limitations and considerations

- Support for custom models is limited to the Copilot Chat experience.

- Model capabilities depend on the provider, and only models that support tool calling should be used with GitHub Copilot in SSMS.

- Services like embeddings, intent detection, and repository indexing might continue to use the Copilot API.

- When you use a custom model, output is returned directly from the provider and might bypass the filtering for responsible AI in GitHub Copilot.

- Support for custom models *isn't* available for Copilot Business or Enterprise users.

## Related content

- [AI model comparison](https://docs.github.com/copilot/reference/ai-models/model-comparison)
- [Hosting of models for GitHub Copilot Chat](https://docs.github.com/copilot/reference/ai-models/model-hosting)
- [Requests in GitHub Copilot](https://docs.github.com/copilot/concepts/billing/copilot-requests#premium-requests)
- [GitHub Copilot billing](https://docs.github.com/copilot/concepts/billing/billing-for-individuals)
- [GitHub support](https://support.github.com/request/landing)
- [Manage Copilot usage and models in SQL Server Management Studio (Preview)](usage-models.md)
