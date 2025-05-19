---
title: "Install Copilot in SSMS"
titleSuffix: Copilot in SQL Server Management Studio
description: Learn how to install Copilot in SQL Server Management Studio.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 05/19/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - ce-skilling-ai-copilot
# CustomerIntent: As a database administrator or database developer, I want to understand how to install Copilot in SQL Server Management Studio.
---

# Install Copilot in SQL Server Management Studio

Copilot in SQL Server Management Studio (SSMS) is your AI assistant that can answer questions about your database and environment, and help with writing and fixing Transact-SQL (T-SQL).

## Prerequisites

To use Copilot in SSMS, you need:

- [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)]
- An endpoint and deployment in [Azure OpenAI Service](/azure/ai-services/openai/overview)

[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] is the GA version of SQL Server Management Studio (SSMS). For information related to SSMS 21 installation, see [Install SQL Server Management Studio 21](../install/install.md).

## Install Copilot in SSMS using the Visual Studio Installer

1. Launch the Visual Studio Installer.
1. Select the installation of SSMS you want to modify, then select **Modify**.
1. Select **AI Assistance** on the Workloads tab. **Copilot in SSMS** appears as a selected component beneath **Installation details**.
1. Select **Modify** to install the extension.

## Configure Copilot

To set up Copilot in SSMS, you must configure the Azure OpenAI resource. This resource can be configured with or without an API key. If an API key isn't used, then authentication to Azure occurs with the user's Microsoft Entra ID. Use of Azure authentication is recommended as the more secure option. For more information related to configuring Azure OpenAI resources, see [Use Azure OpenAI with Copilot in SSMS](use-azure-openai-with-copilot-in-ssms.md).

1. Open SQL Server Management Studio.

1. Select the **Copilot** button on the SQL Editor toolbar, go to **View** > **Copilot**, or type **Ctrl** + **Alt** + **C** to open the dialog to initially configure Copilot in SSMS.

1. Within the **Welcome to Copilot in SQL Server Management Studio** dialog, enter the values for **Azure OpenAI Endpoint**, **Azure OpenAI Deployment**, and **Azure OpenAI API Key** that were provided to you. Depending on the configuration of the Azure OpenAI resource you're using, **Azure OpenAI API Key** might not be required.

1. When complete, select **Launch Copilot**.

1. If Copilot doesn't use an API key, you're prompted to authenticate to Azure. If Copilot appears to be waiting for a response, check your browser to confirm it isn't waiting for Azure authentication to complete.

## Uninstall Copilot in SSMS using the Visual Studio Installer

You can remove Copilot in SSMS from your SSMS installation using the Visual Studio Installer.

1. Launch the Visual Studio Installer.
1. Select the installation of SSMS from you want to remove Copilot in SSMS, then select **Modify**.
1. Uncheck **AI Assistance** on the Workloads tab.
1. Select **Modify** to uninstall the extension.
1. Restart SSMS.

## Related content

- [What is Azure OpenAI Service?](/azure/ai-services/openai/overview)
- [Use Azure OpenAI with Copilot in SSMS](use-azure-openai-with-copilot-in-ssms.md)
- [Use the chat window for Copilot in SQL Server Management Studio](copilot-in-ssms-chat.md)
- [Code assistance for Copilot in SQL Server Management Studio](copilot-in-ssms-code-assistance.md)
