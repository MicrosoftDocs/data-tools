---
title: Azure OpenAI Configuration
titleSuffix: Copilot in SQL Server Management Studio
description: Learn about configuring Azure OpenAI to use with Copilot in SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 12/01/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
f1_keywords:
  - "sql13.swb.copilot.configure.f1"
# CustomerIntent: As a database administrator or database developer, I want to understand how to configure Azure OpenAI to use with Copilot in SQL Server Management Studio.
---
# Use Azure OpenAI with Copilot in SSMS

Copilot in SQL Server Management Studio (SSMS) uses an endpoint and deployment in Azure OpenAI. This article provides the steps to create the necessary Azure OpenAI resources. For more information, see [Create and deploy an Azure OpenAI in Azure AI Foundry Models resource](/azure/ai-services/openai/how-to/create-resource).

Access to deployments can be provided using Microsoft Entra authentication, or API Keys. Microsoft Entra authentication is recommended as a more secure option.

The cost of Copilot in SSMS depends on your use of the provisioned Azure OpenAI resources, as well as the model selected. It will be billed to the Azure subscription that hosts the resources. For more information, see [Azure OpenAI Service pricing overview](https://azure.microsoft.com/pricing/details/cognitive-services/openai-service/).

## Create the endpoint

Endpoint creation is done in the Azure portal.

1. Sign in to the Azure portal.

1. Go to **Services**.

1. Select **Azure AI services**, which is listed under **AI + Machine Learning**.

1. Within *Azure AI services**, select **Azure OpenAI account**.

1. Select **+ Create** to create a new Azure OpenAI service.

1. On the **Basics** page, complete all the required details.

   1. The **Name** is used in the endpoint URL.
   1. The only option currently available for **Pricing tier** is **Standard S0**.

1. Select **Next**.

1. On the **Network** page, select **All Networks** unless you're using a Virtual Private Network (VPN). SQL Server Management Studio (SSMS) must be able to reach the endpoint for Copilot in SSMS to work.

   1. If you use a VPN, under **Type**, check the **Selected networks, configure network security for your Azure AI services resource** option and then choose the appropriate virtual network and subnets.

   1. Add the appropriate IP ranges for a firewall rule.

1. Select **Next**.

1. On the **Tags** page, set any tags your organization uses. Tags aren't required for Copilot in SSMS, but should be set according to your company policy. For example, your company might require all resources to use an Owner tag.

1. Select **Next**.

1. On the **Review + submit page** review the information and then select **Create**.

1. The message **Deployment is in progress** appears, and then the message **Your deployment is complete** when it's provisioned.

1. Select **Go to resource**.

1. Within the resource, expand **Resource Management**, then select **Keys and Endpoint**.

1. Take note of the value for **Endpoint** on the **Keys and Endpoint** page because it will be used when you configure Copilot in SSMS.

   > [!NOTE]  
   > During the initial configuration of Copilot in SSMS, enter **Endpoint** in the **Azure OpenAI Endpoint** dialog.

1. If you're using API key access, then either Key 1 or Key 2 can be used when you configure Copilot in SSMS. API key access is optional; Microsoft Entra authentication is recommended as a more secure option.

   > [!NOTE]  
   > During the initial configuration of Copilot in SSMS, enter Key 1 or Key 2 in the **Azure OpenAI API Key** dialog if using API key access.

## Use Microsoft Entra ID for access

If you would like to use Microsoft Entra to authenticate to Azure OpenAI for Copilot in SSMS, the following steps are required.

1. Within the endpoint resource, select **Access Control (IAM)**.

1. From the **Access Control** page, select **+ Add** to add a role assignment.

1. On the **Role** page, within the list of Job function roles, find **Cognitive Services OpenAI User** and select it, then select **Next**.

1. On the **Members** page, add the appropriate members by entering a user, a group, service principal, or managed identity.

1. Use **+Select members** to open the **Select members** pane.

1. Select the appropriate ID from the list, then **Select**.

1. Select **Review + assign**, and on the **Review + assign** page, review the members, and then select **Review + assign** again to assign the members to the deployment.

1. A notification that the role has been added appears.

1. Repeat steps 2 through 8 for the **Cognitive Services OpenAI Contributor**. All members, whether a user, group, service principal, or managed identity, must be added to both roles.

The **Cognitive Services OpenAI Contributor** role has read/write permissions and the ability to modify the endpoint. Alternatively, you can assign the **Cognitive Services OpenAI Contributor** role to the individual who manages the endpoint (it should be assigned to at least one person), and only assign the **Cognitive Services OpenAI User** role to other members. The **Cognitive Services OpenAI User** role is lower privilege and provides read-only access to the endpoint.

## Create the deployment

The final step required is creating the deployment.

1. Within the endpoint resource, go to the **Overview** page.

1. Select **Explore Azure AI Foundry portal**, which launches a separate portal.

1. A warning that you're leaving the Azure portal appears. Select **Continue**.

1. Within the Azure AI Foundry portal, select **Deployments** under **Shared resources**.

1. Select **+ Deploy model**, then select **Deploy base model**.

1. Within the **Select a model** pane, select the **gpt-4o (Chat completion)** model, then select **Confirm**.

   > [!NOTE]  
   > `gpt-4o` is the only model supported for preview.

1. On the **Deploy model** page, select **Customize**.

1. Within the customization dialog, enter a value for **Deployment name**.

1. Take note of the value for **Deployment name** because it will be used when you configure Copilot in SSMS.

   > [!NOTE]  
   > During the initial configuration of Copilot in SSMS, enter **Deployment name** in the **Azure OpenAI Deployment** dialog.

1. Set the **Deployment type**. Each deployment type includes a description about performance versus data residency. A deployment with 'standard' in the name is recommended for preview. If data residency isn't a concern, then Global Standard offers the best performance. Data Zone Standard provides a balanced trade-off, and Standard optimizes for a specific region at the potential cost of extra latency.

1. The **Model version** should be `2024-11-20`, and the resource location should be set by default (inherited from the endpoint you already created).

1. Set the **Tokens per Minute Rate Limit** to the maximum value available. It can be modified in the Azure AI Foundry portal at any time, should you decide to lower the cap. The lower the value, the fewer the questions per minute that Copilot can answer. For more information, see [Azure OpenAI in Azure AI Foundry Models quotas and limits](/azure/ai-services/openai/quotas-limits).

1. Leave **Content filter** at the default value of **DefaultV2**, unless your company has its own policies around AI content filters.

1. Select **Create resource and deploy**.

1. When deployment is complete, the details page appears. Within the **Get Started** section, you can find the endpoint and deployment in the code for **Run a basic code sample**:

   :::image type="content" source="media/use-azure-openai-with-copilot-in-ssms/copilot-ssms-deployment-endpoint.png" alt-text="Screenshot of code sample that includes the endpoint and deployment." lightbox="media/use-azure-openai-with-copilot-in-ssms/copilot-ssms-deployment-endpoint.png":::

1. Use the following values and endpoint when configuring Copilot in SSMS:

   :::image type="content" source="media/use-azure-openai-with-copilot-in-ssms/copilot-ssms-setup.png" alt-text="Screenshot of initial dialog for Copilot in SSMS configuration." lightbox="media/use-azure-openai-with-copilot-in-ssms/copilot-ssms-setup.png":::

1. If you need to edit any deployment settings, such as **Rate limit (Tokens per minute)**, access the details page for the deployment.

## Monitor cost

The cost of Copilot in SSMS varies based on use and follows a pay-as-you-go billing model. Because the cost isn't a fixed, recurring value, we recommend monitoring the resource spend on a regular basis to mitigate surprises in billing. For more information, see [Plan to manage costs for Azure OpenAI in Azure AI Foundry Models](/azure/ai-services/openai/how-to/manage-costs).

## Related content

- [Troubleshooting issues with Copilot in SQL Server Management Studio](copilot-in-ssms-troubleshooting.md)
- [What is Azure OpenAI in Azure AI Foundry Models?](/azure/ai-services/openai/overview)
- [Use the chat window for Copilot in SQL Server Management Studio](copilot-in-ssms-chat.md)
- [Code assistance for Copilot in SQL Server Management Studio](copilot-in-ssms-code-assistance.md)
