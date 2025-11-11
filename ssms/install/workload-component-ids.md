---
title: Workload and Component IDs for SQL Server Management Studio
description: List the workload and component IDs that can be used when creating an offline installation of SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 11/11/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
---
# Workload and component IDs for SQL Server Management Studio

Installing SQL Server Management Studio (SSMS) using a command line requires workload and component IDs. These IDs allow you to select what to install, modify, or uninstall. Uninstalling SSMS entirely requires channel IDs.

This article is laid out as follows:

- The first section includes the channel ID for each release of SSMS.

- Each workload has its own section, followed by the workload ID and a table of the components that are available for the workload.

- By default, the required components are installed when you install the workload.

- If you choose to, you can also install the Recommended and Optional components.

For more information about how to use these IDs, see [Use command-line parameters to install SQL Server Management Studio](command-line-parameters.md).

## SQL Server Management Studio channel ID

In SSMS 21 and later versions, every Preview and GA release has its own unique channel ID.

| Channel and version | ID | Status |
| --- | --- | --- |
| SSMS 21 Preview | SSMS.21.SSMS.Preview | No longer available. |
| SSMS 21 GA | SSMS.21.SSMS.Release | Prior generally available release. |
| SSMS 22 Preview | SSMS.22.SSMS.Preview | Prior preview release. |
| SSMS 22 GA | SSMS.22.SSMS.Release | Current generally available release. |

## SQL Server Management Studio core editor (included with SSMS)

**ID:** Microsoft.VisualStudio.Component.CoreEditor

**Description:** The SQL Server Management Studio (SSMS) core experience. This component includes the Query Editor and Object Explorer, as well as database management, troubleshooting, and high availability and disaster recovery configuration.

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

| Component ID | Name | Dependency type | Available version |
| --- | --- | --- | --- |
| Microsoft.SSMS.Component.Copilot | Copilot in SQL Server Management Studio (SSMS) | Recommended | SSMS 21 |
| Microsoft.SSMS.ComponentGroup.Copilot | GitHub Copilot in SQL Server Management Studio (SSMS) | Recommended | SSMS 22 (Preview) |

## Business Intelligence

**ID:** Microsoft.SqlServer.Workload.SSMS.BI

**Description:** Empower your business end-to-end, transforming data into insights, analytics into action, and reports into results.

### Components included by this workload

| Component ID | Name | Dependency type |
| --- | --- | --- |
| Microsoft.SSMS.Component.AS | Analysis Services management capabilities | Recommended |
| Microsoft.SSMS.Component.IS | Integration Services management capabilities | Recommended |
| Microsoft.SSMS.Component.RS | Reporting Services management capabilities | Recommended |

## Code tools

**ID:** Microsoft.SqlServer.Workload.SSMS.CodeTools

**Description:** Tools to fit when and where you work while improving code.

### Components included by this workload

| Component ID | Name | Dependency type |
| --- | --- | --- |
| Microsoft.Component.HelpViewer | Microsoft documentation available as offline content | Optional |
| Microsoft.VisualStudio.Component.TeamExplorer.MinGit | Git integration | Recommended |
| Microsoft.SSMS.Component.QueryHintTool | Query Hint Recommendations Tool | Recommended |

## Hybrid and Migration

**ID:** Microsoft.SqlServer.Workload.SSMS.HybridAndMigration

**Description:** Assess database upgrade readiness, and move your data with ease.

### Components included by this workload

| Component ID | Name | Dependency type |
| --- | --- | --- |
| Microsoft.SSMS.Component.MigrationAssistant | Assessment and Migration Assistant | Recommended |

For more information about how to use this information, see [Create an offline installation of SQL Server Management Studio](create-offline.md).

## Support or troubleshooting

Sometimes, things can go wrong. If your SQL Server Management Studio installation fails, see [Troubleshoot installation and upgrade issues for SQL Server Management Studio](troubleshoot.md) for step-by-step guidance.

## Related content

- [Create an offline installation of SQL Server Management Studio](create-offline.md)
- [Use command-line parameters to install SQL Server Management Studio](command-line-parameters.md)
