---
title: "SQL Server Management Studio (SSMS)"
description: Learn details about SQL Server Management Studio (SSMS) and what SSMS can do, including how to manage Analysis Services Solutions.
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/17/2025
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

SQL Server Management Studio (SSMS) is an integrated environment for managing any SQL infrastructure. Use SSMS to access, configure, manage, administer, and develop all components of [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)], [Azure SQL Database](/azure/azure-sql/database/sql-database-paas-overview), [Azure SQL Managed Instance](/azure/azure-sql/managed-instance/sql-managed-instance-paas-overview), [SQL Server on Azure Virtual Machines](/azure/azure-sql/virtual-machines/windows/sql-server-on-azure-vm-iaas-what-is-overview), [SQL database in Microsoft Fabric](/fabric/database/sql/overview), and [Azure Synapse Analytics](/azure/synapse-analytics/sql-data-warehouse/sql-data-warehouse-overview-what-is/). SSMS provides a single comprehensive utility that combines a broad group of graphical tools with many rich script editors to provide access to [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)] for developers and database administrators of all skill levels.

- **[Install SQL Server Management Studio](install/install.md)**
- **[Download SQL Server Enterprise Developer or Standard Developer edition](https://go.microsoft.com/fwlink/?linkid=2338332)**

:::image type="content" source="media/sql-server-management-studio-ssms/ssms.png" alt-text="Screenshot of SQL Server Management Studio.":::

## SSMS components

| Description | Component |
| --- | --- |
| Use **Object Explorer** to view and manage all objects in one or more instances of [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)]. | [Object Explorer](object/object-explorer.md) |
| Use **Template Explorer** to build and manage files of boilerplate text that you use to speed the development of queries and scripts. | [Template Explorer](template/template-explorer.md) |
| Use the deprecated **Solution Explorer** to build projects to manage administration items such as scripts and queries. | [Solution Explorer](solution/solution-explorer.md) |
| Use the visual design tools included in SSMS to build queries, tables, and diagram databases. | [Visual Database Tools](visual-db-tools/visual-database-tools.md) |
| Use the SSMS language editors to interactively build and debug queries and scripts. | [Query and text editors](f1-help/database-engine-query-editor-sql-server-management-studio.md) |

## SSMS for business intelligence

Use SSMS to access, configure, manage, and administer Analysis Services, Integration Services, and Reporting Services. Although all three business intelligence technologies rely on SSMS, the administrative tasks associated with each are slightly different.

> [!NOTE]  
> To create and modify Analysis Services, Integration Services solutions, and Reporting Services, use SQL Server Data Tools (SSDT), not SSMS. [SQL Server Data Tools (SSDT)](/sql/ssdt/sql-server-data-tools) is a development environment that is based on [Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/).

### Manage Analysis Services solutions

SQL Server Management Studio (SSMS) enables you to manage Analysis Services objects, such as performing back-ups and processing objects.

SSMS provides an Analysis Services Script project in which you can develop and save scripts written in **Multidimensional Expressions (MDX)**, **Data Analysis Expressions (DAX)**, **Data Mining Extensions (DMX)**, and **XML for Analysis (XMLA)**.

Use these scripts to perform management tasks, or recreate objects such as databases and instances on Analysis Services cubes. For example, you can develop an XMLA script in an Analysis Services Script project to create new objects directly on an existing instance. You can save these projects as part of a solution and integrate them with source code control.

> [!NOTE]  
> SSMS supports DAX and MDX, but you should consider the model you're working with and the type of queries you intend to run.

For more information about the Analysis Services Scripts Project in SSMS, see [Analysis Services Scripts Project](/analysis-services/instances/analysis-services-scripts-project-in-sql-server-management-studio).

### Manage Integration Services solutions

SSMS can manage, run, and monitor SQL Server Integration Services (SSIS) packages stored in the `SSISDB` database. You can import, export, and upgrade packages, and organize them into folders. You can access the SSIS catalog from Object Explorer.

The [Import and Export Wizard](/sql/integration-services/import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard) in SSMS can generate basic SSIS packages, and serves as a good starting point for learning about SSIS. For designing and maintaining more complex solutions, use [SQL Server Data Tools (SSDT)](/sql/ssdt/sql-server-data-tools).

### Manage Reporting Services projects

**Applies to**: [!INCLUDE [sssql22-md](includes/sssql22-md.md)] and earlier versions

SSMS provides an integrated environment for administering SQL Server Reporting Services (SSRS) in [!INCLUDE [sssql22-md](includes/sssql22-md.md)] and earlier versions. You can manage the report server itself, its databases (`ReportServer` and `ReportServerTempDB`), roles, jobs, and shared schedules. The **Shared Schedules** folder provides direct access to scheduling tasks.

> [!NOTE]  
> Starting in [!INCLUDE [sssql25-md](includes/sssql25-md.md)], on-premises reporting services is consolidated under [Power BI Report Server](/power-bi/report-server/get-started). For more information, see [Reporting Services consolidation FAQ](/sql/reporting-services/reporting-services-consolidation-faq).

SSMS also supports server-level operations, letting you enable and configure SSRS features, define defaults, and maintain roles and jobs.

If you migrate a report server database to a SQL Server instance, remember to create the **RSExecRole** in the `master` system database.

While SSMS delivers a solid set of tools for managing SSRS on [!INCLUDE [sssql22-md](includes/sssql22-md.md)] and earlier versions, it doesn't replace Report Manager or the Reporting Services Configuration Manager.

For more information on related SSRS tasks, see:

- [Set report server properties (Management Studio)](/sql/reporting-services/tools/set-report-server-properties-management-studio)
- [Create, delete, or modify a role (Management Studio)](/sql/reporting-services/security/role-definitions-create-delete-or-modify)
- [Enable and disable client-side printing for Reporting Services](/sql/reporting-services/report-server/enable-and-disable-client-side-printing-for-reporting-services)
- [Reporting Services in SQL Server Management Studio (SSRS)](/sql/reporting-services/tools/reporting-services-in-sql-server-management-studio-ssrs)
- [Administer a report server database (SSRS native mode)](/sql/reporting-services/report-server/administer-a-report-server-database-ssrs-native-mode)
- [Create the RSExecRole](/sql/reporting-services/security/create-the-rsexecrole)

## Non-English language versions

The Visual Studio Installer selects a default language pack for SSMS that matches the language of your operating system. You can change the default language at any time. For more information, see [Modify SQL Server Management Studio workloads, components, and language packs](install/modify.md).

## Support policy

The SQL Tools team has adopted the [Microsoft Modern Lifecycle Policy](/lifecycle/policies/modern).

Read the original [Modern Lifecycle Policy announcement](/lifecycle/announcements/modern-policy). For more information, see [Modern Policy FAQs](/lifecycle/faq/modern-policy).

For diagnostic data collection and feature usage information, see the [SQL Server privacy supplement](/sql/sql-server/sql-server-privacy) and [diagnostic data collection](sql-server-management-studio-telemetry-ssms.md).

[!INCLUDE [get-help-options](includes/paragraph-content/get-help-options.md)]

## Related content

- [Modify SQL Server Management Studio workloads, components, and language packs](install/modify.md)
- [Quickstart: Connect and query a SQL Server instance using SQL Server Management Studio (SSMS)](quickstarts/ssms-connect-query-sql-server.md)
- [Tutorial: Write Transact-SQL statements](/sql/t-sql/tutorial-writing-transact-sql-statements)
