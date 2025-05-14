---
title: Workload and Component IDs for SQL Server Management Studio
description: List the workload and component IDs that can be used when creating an offline installation of SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan
ms.date: 05/19/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
---
# Workload and component IDs for SQL Server Management Studio

This table lists the available component IDs for you can use when installing [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] by using a command line.

| Version | ID | Description |
| --- | --- | --- |
| SQL Server Management Studio 21 | Microsoft.Component.HelpViewer | Microsoft documentation available as offline content |
| SQL Server Management Studio 21 | Microsoft.SSMS.Component.AS | Analysis Services management capabilitiees |
| SQL Server Management Studio 21 | Microsoft.SSMS.Component.Copilot | Copilot in SQL Server Management Studio (SSMS) |
| SQL Server Management Studio 21 | Microsoft.SSMS.Component.RS | Reporting Services management capabilitiees |
| SQL Server Management Studio 21 | Microsoft.SSMS.Component.MigrationAssistant | Assessment and Migration Assistant |
| SQL Server Management Studio 21 | Microsoft.VisualStudio.Component.TeamExplorer.MinGit | Git integration |

For more information about how to use this list, see [Create an offline installation of SQL Server Management Studio](create-offline.md).

## Support or troubleshooting

Sometimes, things can go wrong. If your SQL Server Management Studio installation fails, see [Troubleshoot installation and upgrade issues for SQL Server Management Studio](troubleshoot.md) for step-by-step guidance.

## Related content

- [Create an offline installation of SQL Server Management Studio](create-offline.md)
- [Use command-line parameters to install SQL Server Management Studio](command-line-parameters.md)
