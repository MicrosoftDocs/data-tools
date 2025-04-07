---
title: Deploy Azure SQL Database via Notebook
description: This tutorial shows how you can create an Azure SQL Database.
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest, maghan
ms.date: 02/06/2025
ms.service: azure-data-studio
ms.topic: tutorial
ms.collection:
  - data-tools
ms.custom:
  - intro-deployment
  - updatefrequency5
---

# Create an Azure SQL Database using Azure Data Studio

[!INCLUDE [azure-data-studio-deprecation](includes/azure-data-studio-deprecation.md)]

You can create an Azure SQL Database using Azure Data Studio through the deployment wizard and notebooks.

## Prerequisites

- [Azure Data Studio](download-azure-data-studio.md) is installed
- An active Azure account and subscription. If you don't have one, [create a free account](https://azure.microsoft.com/free/).

## Use the deployment wizard

Follow these steps to use the deployment wizard to guide you through the required settings in a simple UI experience.

First, find, and select Azure SQL Database in the deployment wizard.

1. In Azure Data Studio, select the **Connections** viewlet on the left-side navigation.

1. Select the **...** button at the top of the Connections panel and choose **New Deployment...**

1. In the deployment wizard, select the **Azure SQL Database** tile and check the terms acceptance checkbox

1. In the Resource type dropdown list, select what you would like to create - either a database, database server, or elastic pool. We recommend creating a database if you don't have any SQL databases in Azure.

1. Select **Create in Azure portal** if you want to create a server or pool, or select **Select** if you want to create a database.

If you choose to create a database, follow the steps below.

1. Sign in to your Azure account if you haven't already. You can refresh your connection if you have issues on this wizard page.

1. Select your desired subscription and server. Then select **Next**.

1. Enter a database name.

1. Enter a firewall rule name and the IP range of your local client machine running Azure Data Studio. This allows you to connect to the server and database from ADS right after they have been created.

1. Select **Next**.

1. Review your entered parameters and then select **Script to Notebook**.

Once the Notebook opens, you can review the content, and code and make changes if you like. In particular, you can change the compute and storage settings from the default if you have specific performance or cost preferences. However, any changes you make to the Notebook could cause validation errors.

The last step is to select **Run all** to run all cells in the Notebook. Once this is completed, you should have an entirely created and running SQL Database that you can connect to and query from ADS.

## Next step

> [!div class="nextstepaction"]
> [Connect and query](quickstart-sql-database.md)
