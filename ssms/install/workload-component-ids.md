---
title: Workload and Component IDs for SQL Server Management Studio
description: List the workload and component IDs that can be used when creating an offline installation of SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan
ms.date: 06/25/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
---
# Workload and component IDs for SQL Server Management Studio

This table lists the available workload and component IDs for you can use when installing [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] by using a command line.

This article is laid out as follows:

- Each workload has its own section, followed by the workload ID and a table of the components that are available for the workload.

- By default, the required components are installed when you install the workload.

- If you choose to, you can also install the Recommended and Optional components.

For more information about how to use these IDs, see [Use command-line parameters to install SQL Server Management Studio](command-line-parameters.md).

## SQL Server Management Studio core editor (included with SSMS 21)

**ID:** Microsoft.VisualStudio.Component.CoreEditor

**Description:** The SQL Server Management Studio (SSMS) core experience, including the Query Editor, Object Explorer, and database management, troubleshooting, and high availability and disaster recovery configuration.

### Components included by this workload

| Component ID | Name | Dependency type |
| --- | --- | --- |
| Microsoft.VisualStudio.Component.CoreEditor | Visual Studio core editor | Required |
| Microsoft.VisualCpp.Redist.14.Latest | C++ 2022 Redistributable Update | Required |
| Microsoft.VisualStudio.Component.MSODBC.SQL | SQL Server ODBC Driver | Required |
| msoledbsql | SQL Server ODBC Driver | Required |

## AI Assistance

**ID:** Microsoft.SqlServer.Workload.SSMS.AI

**Description:** AI-powered assistants to help you write queries and manager your databases more efficiently.

### Components included by this workload

| Component ID | Name | Dependency type |
| --- | --- | --- |
| Microsoft.SSMS.Component.Copilot | Copilot in SQL Server Management Studio (SSMS) | Required |

## Business Intelligence

**ID:** Microsoft.SqlServer.Workload.SSMS.BI

**Description:** Empower your business end-to-end, transforming data into insights, analytics into action, and reports into results.

### Components included by this workload

| Component ID | Name | Dependency type |
| --- | --- | --- |
| Microsoft.SSMS.Component.AS | Analysis Services management capabilities | Required |
| Microsoft.SSMS.Component.IS | Integration Services management capabilities | Required |
| Microsoft.SSMS.Component.RS | Reporting Services management capabilities | Required |

## Code tools

**ID:** Microsoft.SqlServer.Workload.SSMS.CodeTools

**Description:** Tools to fit when and where you work while improving collaboration.

### Components included by this workload

| Component ID | Name | Dependency type |
| --- | --- | --- |
| Microsoft.Component.HelpViewer | Microsoft documentation available as offline content | Optional |
| Microsoft.VisualStudio.Component.TeamExplorer.MinGit | Git integration | Required |

## Hybrid and Migration

**ID:** Microsoft.SqlServer.Workload.SSMS.HybridAndMigration

**Description:** Assess database upgrade readiness, and move your data with ease.

### Components included by this workload

| Component ID | Name | Dependency type |
| --- | --- | --- |
| Microsoft.SSMS.Component.MigrationAssistant | Assessment and Migration Assistant | Required |

For more information about how to use this list, see [Create an offline installation of SQL Server Management Studio](create-offline.md).

## Support or troubleshooting

Sometimes, things can go wrong. If your SQL Server Management Studio installation fails, see [Troubleshoot installation and upgrade issues for SQL Server Management Studio](troubleshoot.md) for step-by-step guidance.

## Related content

- [Create an offline installation of SQL Server Management Studio](create-offline.md)
- [Use command-line parameters to install SQL Server Management Studio](command-line-parameters.md)
