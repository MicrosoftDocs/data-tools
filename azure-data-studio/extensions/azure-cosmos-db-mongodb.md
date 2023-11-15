---
title: Azure Cosmos DB for MongoDB RU extension (preview)
titleSuffix: Azure Data Studio
description: Connect to and query a collection using the Azure Data Studio extension for Azure Cosmos DB for MongoDB RU.
author: sandnair
ms.author: sandnair
ms.reviewer: sidandrews
ms.service: azure-data-studio
ms.custom:
  - ignite-2023
ms.topic: how-to
ms.date: 10/31/2023
# CustomerIntent: As a database developer, I want to use the extension, so that I can explore my data already in Azure Cosmos DB for MongoDB RU.
---

# Azure Cosmos DB for MongoDB RU extension for Azure Data Studio (preview)

The Azure Cosmos DB API for MongoDB RU extension enables you to manage and query your API for MongoDB RU accounts using the capabilities of Azure Data Studio.

The Azure Data Studio functionality available for Azure Cosmos DB API for MongoDB includes:

- Connection manager & query editor
- Provisioning and scaling containers
- [Integrated terminal](../integrated-terminal.md)

## Prerequisites

- An existing Azure Cosmos DB for MongoDB RU account.
  - If you don't have an Azure subscription, [create an account for free](https://azure.microsoft.com/free).
- Latest version of [Azure Data Studio](..//download-azure-data-studio.md).

## Install the extension

Start by installing the Azure Cosmos DB for MongoDB RU extension in Azure Data Studio.

1. Open the **extensions manager** in Azure Data Studio. Either select the extensions icon or select **Extensions** in the View menu.

1. Enter `Cosmos` in the search bar.

1. Select the **Azure Cosmos DB for MongoDB** extension and view its details.

1. Select **Install**.

## Connect to the MongoDB source

Use the extension for the first time to connect to your existing API for MongoDB RU account. Ensure that you have the connection credentials for the account ready before starting this section.

1. Locate the connections icon in the menu bar, and select **New Connection**.

1. In the **Connection** pane, fill out the following fields:

    | | Value |
    | --- | --- |
    | **Connection type** | `Mongo account` |
    | **Connection string/Parameters** | *Use the connection string or parameters for your existing source MongoDB instance.* |
    | **Server group** | `Default` |
    | **Name (optional)** | *Provide a unique name for this connection.* |

1. Select **Connect**.

## Related content

- [Add Azure Data Studio extension](add-extensions.md)
- [Azure Cosmos DB for MongoDB RU](/azure/cosmos-db/mongodb)
