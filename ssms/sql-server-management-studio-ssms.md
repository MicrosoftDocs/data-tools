---
title: "SQL Server Management Studio (SSMS)"
description: Learn details about SQL Server Management Studio (SSMS) and what SSMS can do, including how to manage Analysis Services Solutions.
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/05/2026
ms.service: sql-server-management-studio
ms.topic: overview
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.ssms.viewhelp.f1"
helpviewer_keywords:
  - "SQL Server Management Studio"
  - "SQL Server Management Studio for Integration Services"
  - "SQL Server Management Studio for Reporting Services"
  - "SQL Server Management Studio for Analysis Services"
---

# What is SQL Server Management Studio (SSMS)?

[!INCLUDE [SQL Server ASDB, ASDBMI, ASDW](includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

SQL Server Management Studio (SSMS) is an integrated environment for managing any SQL infrastructure. Use SSMS to access, configure, manage, administer, and develop all components of [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)], [Azure SQL Database](/azure/azure-sql/database/sql-database-paas-overview), [Azure SQL Managed Instance](/azure/azure-sql/managed-instance/sql-managed-instance-paas-overview), [SQL Server on Azure Virtual Machines](/azure/azure-sql/virtual-machines/windows/sql-server-on-azure-vm-iaas-what-is-overview), [SQL database in Microsoft Fabric](/fabric/database/sql/overview), and [Azure Synapse Analytics](/azure/synapse-analytics/sql-data-warehouse/sql-data-warehouse-overview-what-is/).

SSMS provides a single comprehensive utility that combines a broad group of graphical tools with many rich script editors to provide access to [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)] for developers and database administrators of all skill levels. For more information, see
[Components and features in SQL Server Management Studio](components-features.md).

:::image type="icon" source="includes/media/download.svg" border="false"::: **[Install SQL Server Management Studio](install/install.md)**

:::image type="icon" source="includes/media/download.svg" border="false"::: **[Download SQL Server Enterprise Developer or Standard Developer edition](https://go.microsoft.com/fwlink/?linkid=2338332)**

:::image type="content" source="media/sql-server-management-studio-ssms/ssms.png" alt-text="Screenshot of SQL Server Management Studio.":::

## What you can do with SSMS

SSMS brings together graphical tools and rich editors to help you:

- Connect securely to SQL Server, Azure SQL, and related services. Manage objects by using **Object Explorer** and design tools.
- Query, script, and tune workloads by using the **Query Editor**, execution plans, and built-in performance tools.
- Administer business intelligence features such as Integration Services (SSIS), Analysis Services (SSAS), and Reporting Services (SSRS).

### Components and features

Explore the full set of capabilities, including AI assistance, performance tools, source control, and BI administration, in [Components and features in SQL Server Management Studio](components-features.md).

### Highlights in SSMS 22

| Feature | Description | Article |
| --- | --- | --- |
| **AI assistance (Preview)** | GitHub Copilot in SSMS adds chat and right-click code actions, plus model selection and BYOM. | [Get started with GitHub Copilot in SQL Server Management Studio (Preview)](github-copilot/get-started.md) |
| **Query Hint Recommendation (Preview)** | Assess queries and apply recommended hints. | [Query Hint Recommendation tool (Preview)](query-hint-tool/hint-tool-overview.md) |
| **Modern connection experience** | Updated dialog, Fabric browsing, and improved encryption visibility. | [Connect to a SQL Server instance](quickstarts/ssms-connect-query-sql-server.md?tabs=modern#connect-to-a-sql-server-instance) |

For full details of the latest features, see [Release notes for SQL Server Management Studio (SSMS)](release-notes-22.md).

### Administer SSIS, SSAS, and SSRS

Use SSMS to [view, configure, and administer](components-features.md#business-intelligence-administration) SQL Server Integration Services (SSIS), SQL Server Analysis Services (SSAS), and SQL Server Reporting Services (SSRS) at the server level.

For development of packages, models, or reports, use [SQL Server Data Tools (SSDT)](/sql/ssdt/sql-server-data-tools).

> [!NOTE]  
> Starting with [!INCLUDE [sssql25-md](includes/sssql25-md.md)], on-premises reporting services are consolidated under Power BI Report Server. For more information, see [Reporting Services consolidation FAQ](/sql/reporting-services/reporting-services-consolidation-faq).

## Non-English language versions

The Visual Studio Installer selects a default language pack for SSMS that matches the language of your operating system. You can change the default language at any time. For more information, see [Modify SQL Server Management Studio workloads, components, and language packs](install/modify.md).

## Support policy

The SQL Tools team follows the [Microsoft Modern Lifecycle Policy](/lifecycle/policies/modern).

For more information, see the original [Modern Lifecycle Policy announcement](/lifecycle/announcements/modern-policy) and the [Modern Policy FAQs](/lifecycle/faq/modern-policy).

For diagnostic data collection and feature usage information, see the [SQL Server privacy supplement](/sql/sql-server/sql-server-privacy) and [diagnostic data collection](sql-server-management-studio-telemetry-ssms.md).

[!INCLUDE [get-help-options](includes/paragraph-content/get-help-options.md)]

## Related content

- [Install SQL Server Management Studio](install/install.md)
- [Components and features in SQL Server Management Studio](components-features.md)
- [Modify SQL Server Management Studio workloads, components, and language packs](install/modify.md)
- [Quickstart: Connect and query a SQL Server instance using SQL Server Management Studio (SSMS)](quickstarts/ssms-connect-query-sql-server.md)
