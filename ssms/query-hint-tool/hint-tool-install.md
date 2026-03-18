---
title: Install the Query Hint Recommendation Tool
titleSuffix: SQL Server Management Studio
description: Learn how to install the Query Hint Recommendation tool.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 03/18/2026
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand how to install the Query Hint Recommendation Tool.
---

# Install the Query Hint Recommendation tool

The Query Hint Recommendation tool allows you to identify an appropriate query hint to improve the performance of your query, directly from the query editor in SQL Server Management Studio (SSMS).

## Prerequisites

The Query Hint Recommendation tool requires a supported version of [SQL Server Management Studio](../install/install.md).

## Install the Query Hint Recommendation tool using the Visual Studio Installer

1. Launch the Visual Studio Installer.
1. Select the installation of SSMS you want to modify, then select **Modify**.
1. Select **Code Tools** on the Workloads tab. **Query Hint Recommendation Tool** appears as a selected component beneath **Installation details**.
1. Select **Modify** to install the extension.

## Uninstall the Query Hint Recommendation Tool using the Visual Studio Installer

You can remove the Query Hint Recommendation tool from your SSMS installation using the Visual Studio Installer.

1. Launch the Visual Studio Installer.
1. Select the installation of SSMS from you want to remove Query Hint Recommendation tool in SSMS, then select **Modify**.
1. Select **Code Tools** on the Workloads tab.
1. Uncheck **Query Hint Recommendation Tool** beneath **Installation details**.
1. Select **Modify** to uninstall the extension.

## Related content

- [Use the Query Hint Recommendation tool](hint-tool-use.md)
