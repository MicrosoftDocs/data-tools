---
title: Preview Features in Azure Data Studio
description: Learn more about Azure Data Studio preview features and how to enable and use them.
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest, maghan
ms.date: 02/06/2025
ms.service: azure-data-studio
ms.topic: how-to
ms.collection:
  - data-tools
---

# Preview features in Azure Data Studio

[!INCLUDE [azure-data-studio-deprecation](includes/azure-data-studio-deprecation.md)]

In Azure Data Studio, new features and improvements are often first released as preview features before they're made generally available (GA). The amount of time a feature remains in preview can vary based on user feedback, quality checks, and long-term road maps. By enabling preview features, you get full access to Azure Data Studio features and the chance to provide early feedback.

## How do I enable preview features?

### On first launch

If you're a new user, you can opt into preview features when you launch Azure Data Studio for the first time. On startup, a toast notification appears in the bottom-right corner of the screen that gives you the option to enable or disable preview features. Select **Yes (recommended)** to enable preview features.

:::image type="content" source="media/getting-started/preview-toast-notification.png" alt-text="Screenshot of preview toast notification on first launch.":::

### In Settings

You can enable or disable preview features at any time in Settings.

1. Select the **Gear** icon in the bottom-left corner and then select **Settings** from the context menu.

   :::image type="content" source="media/settings/open-settings-menu.png" alt-text="Screenshot of gear icon to access Settings in ADS.":::

1. Once the Settings tab is open, type "enable preview features" in the search bar.

1. To enable preview features, check the checkbox for **Enable unreleased preview features** under **Workbench: Enable Preview Features**. To disable preview features, clear the checkbox.

   :::image type="content" source="media/settings/preview-features-settings.png" alt-text="Screenshot of enabling preview features setting in ADS.":::

## List of preview features in Azure Data Studio

### General features in preview

- Attach Database
- Backup / Restore
- Create Database
- Database Properties
- Delete Database
- Detach Database
- User Management
- Server Properties
- SQLCMD mode in Query Editor

### First-party extensions in preview

- Azure Cosmos DB API for MongoDB
- Azure Cosmos DB Migration for MongoDB
- Azure Monitor Logs
- Azure PostgreSQL migration
- Central Management Servers
- Data Migration for Oracle
- Database Administration Tool Extensions for Windows
- Kusto
- SQL Managed Instance Dashboard
- Oracle
- PostgreSQL
- SandDance for Azure Data Studio
- Server Reports
- SQL Assessment
- SQL Server Agent
- SQL Server Profiler
- whoisactive

## Next steps

- [User Settings](settings-list.md)
