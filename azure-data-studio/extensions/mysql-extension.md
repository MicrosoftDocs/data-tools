---
title: MySQL Extension
description: Learn how to install the MySQL extension for Azure Data Studio. It enables you to connect to, query, and develop for MySQL databases hosted on-premises, on VMs, on other clouds or on Azure Database for MySQL - Flexible Server.
author: croblesm
ms.author: roblescarlos
ms.reviewer: shaithal, randolphwest, maghan
ms.date: 02/06/2025
ms.service: azure-data-studio
ms.topic: conceptual
ms.collection:
  - data-tools
---

# MySQL extension

[!INCLUDE [azure-data-studio-deprecation](../includes/azure-data-studio-deprecation.md)]

With the MySQL extension for Azure Data Studio, you can now connect to, query and manage MySQL databases along with your other databases, taking advantage of the modern editor experience and capabilities in Azure Data Studio, such as IntelliSense, code snippets, source control integration, native Jupyter Notebooks, an integrated terminal, and more.

> [!NOTE]  
> [!INCLUDE [azure-active-directory-microsoft-entra-id](../includes/azure-active-directory-microsoft-entra-id.md)]

The Azure Data Studio functionality available for MySQL includes:

- Connection manager, allowing you to connect to any MySQL server hosted on-premises, on virtual machines, on managed MySQL in other clouds, and on Azure Database for MySQL – Flexible Server.
- Option to choose your preferred authentication method (MySQL native authentication and Microsoft Entra authentication)
- Searchable object explorer view for database objects, with auto-completion
- Query authoring and editing with Intellisense, syntax highlighting and code snippets
- Ability to query results and save to csv, JSON, xml, or Excel
- [Integrated terminal for Bash, PowerShell, and cmd.exe](../integrated-terminal.md)
- [Source control integration with Git](../source-control.md)
- [Customizable dashboards and insight widgets](../insight-widgets.md)
- [Customizable keyboard shortcuts](../keyboard-shortcuts.md), multi-tab support, color theme options, etc.
- [Server groups](../server-groups.md) for organizing connections

## Install the MySQL extension

If you don't already have Azure Data Studio installed, see its [install instructions](../download-azure-data-studio.md).

1. Select the extensions icon from the sidebar in Azure Data Studio.

    :::image type="content" source="media/mysql-extension/extensions-icon.png" alt-text="Screenshot of the extension's icon.":::

2. Search for the **MySQL** extension and select it.

3. Select **Install**. Once installed, select **Reload** to activate the extension in Azure Data Studio.

    :::image type="content" source="media/mysql-extension/mysql-ads-extension.png" alt-text="Screenshot of the extension overview page.":::

## Next steps

Learn how to [connect and query MySQL using Azure Data Studio](../quickstart-mysql.md).
