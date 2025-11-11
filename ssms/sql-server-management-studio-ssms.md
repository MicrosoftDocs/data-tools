---
title: "SQL Server Management Studio (SSMS)"
description: Learn details about SQL Server Management Studio (SSMS) and what SSMS can do, including how to manage Analysis Services Solutions.
author: rwestMSFT
ms.author: randolphwest
ms.date: 05/19/2025
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

SQL Server Management Studio (SSMS) is an integrated environment for managing any SQL infrastructure. Use SSMS to access, configure, manage, administer, and develop all components of [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)], [Azure SQL Database](/azure/azure-sql/database/sql-database-paas-overview), [Azure SQL Managed Instance](/azure/azure-sql/managed-instance/sql-managed-instance-paas-overview), [SQL Server on Azure VM](/azure/azure-sql/virtual-machines/windows/sql-server-on-azure-vm-iaas-what-is-overview), and [Azure Synapse Analytics](/azure/synapse-analytics/sql-data-warehouse/sql-data-warehouse-overview-what-is/). SSMS provides a single comprehensive utility that combines a broad group of graphical tools with many rich script editors to provide access to [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)] for developers and database administrators of all skill levels.

- [**Install SQL Server Management Studio**](install/install.md)
- [**Download SQL Server Developer edition**](https://my.visualstudio.com/Downloads?q=SQL%20Server%20Developer)
- [**Download Visual Studio**](https://www.visualstudio.com/downloads/)

:::image type="content" source="media/sql-server-management-studio-ssms/ssms.png" alt-text="Screenshot of SQL Server Management Studio.":::

## SQL Server Management Studio components

| Description | Component |
| --- | --- |
| Use **Object Explorer** to view and manage all objects in one or more instances of [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)]. | [Object Explorer](object/object-explorer.md) |
| Use **Template Explorer** to build and manage files of boilerplate text that you use to speed the development of queries and scripts. | [Template Explorer](template/template-explorer.md) |
| Use the deprecated **Solution Explorer** to build projects to manage administration items such as scripts and queries. | [Solution Explorer](solution/solution-explorer.md) |
| Use the visual design tools included in SSMS to build queries, tables, and diagram databases. | [Visual Database Tools](visual-db-tools/visual-database-tools.md) |
| Use the SSMS language editors to interactively build and debug queries and scripts. | [Query and text editors](f1-help/database-engine-query-editor-sql-server-management-studio.md) |

## SQL Server Management Studio for business intelligence

Use SSMS to access, configure, manage, and administer Analysis Services, Integration Services, and Reporting Services. Although all three business intelligence technologies rely on SSMS, the administrative tasks associated with each are slightly different.

> [!NOTE]  
> To create and modify Analysis Services, Integration Services solutions, and Reporting Services, use SQL Server Data Tools (SSDT), not SSMS. [SQL Server Data Tools (SSDT)](/sql/ssdt/sql-server-data-tools) is a development environment that is based on [Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/).

### Manage Analysis Services solutions

SQL Server Management Studio (SSMS) enables you to manage Analysis Services objects, such as performing back-ups and processing objects.

SSMS provides an Analysis Services Script project in which you can develop and save scripts written in **Multidimensional Expressions (MDX)**, **Data Analysis Expressions (DAX)**, **Data Mining Extensions (DMX)**, and **XML for Analysis (XMLA)**.

These scripts are used to perform management tasks or recreate objects such as databases and instances on Analysis Services cubes. For example, you can develop an XMLA script in an Analysis Services Script project to create new objects directly on an existing instance. These projects can be saved as part of a solution and integrated with source code control.

> [!NOTE]  
> While DAX was originally designed for tabular data models, it can also be used to query multidimensional models in SQL Server Analysis Services. SSMS can do DAX and MDX, but there are some considerations to keep in mind regarding the model you're working with and the type of queries you intend to run.

For more information about the Analysis Services Scripts Project in SSMS, see [Analysis Services Scripts Project](/analysis-services/instances/analysis-services-scripts-project-in-sql-server-management-studio).

### Manage Integration Services solutions

SQL Server Management Studio (SSMS) can be used to manage and monitor running SSIS packages. You can organize packages into folders, run, import, export, and upgrade Integration Services packages. However, since SSIS 2012, the storage of packages has changed. They're no longer stored in the server's `msdb` database of the default instance but are now managed through the SSIS Catalog database (`SSISDB`). This means that you can no longer manage packages in the same way as you did in previous versions of SSIS. You can still use SSMS to manage the SSIS Catalog database, but you must use the Integration Services Catalogs node in Object Explorer.

The latest version of SSMS provides an integrated environment for managing any SQL infrastructure. It also allows users to run SSIS packages stored in the SSIS Catalog from Object Explorer in SSMS.

The [Import and Export Wizard](/sql/integration-services/import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard) within SSMS can be used to create SSIS packages, which is a good starting point for learning about SSIS. However, you must use [SQL Server Data Tools (SSDT)](/sql/ssdt/sql-server-data-tools) to create and manage your packages for more complex packages.

### Manage Reporting Services projects

SQL Server Management Studio (SSMS) enables Reporting Services features, administers the server and databases, and manages roles and jobs. You can manage shared schedules using the Shared Schedules folder and manage report server databases (`ReportServer`, `ReportServerTempDB`). When moving a report server database to a new SQL Server instance, you must create an RSExecRole in the `master` system database.

For more information on these tasks, you can refer to the articles on Reporting Services in SSMS, administering a Report Server database, and creating the **RSExecRole**:

- [Reporting Services in SQL Server Management Studio (SSRS)](/sql/reporting-services/tools/reporting-services-in-sql-server-management-studio-ssrs)
- [Administer a report server database (SSRS native mode)](/sql/reporting-services/report-server/administer-a-report-server-database-ssrs-native-mode)
- [Create the RSExecRole](/sql/reporting-services/security/create-the-rsexecrole)

You also manage the server by enabling and configuring various features, setting server defaults, and managing roles and jobs.

For more information about these tasks, see the following articles:

- [Set report server properties (Management Studio)](/sql/reporting-services/tools/set-report-server-properties-management-studio)
- [Create, delete, or modify a role (Management Studio)](/sql/reporting-services/security/role-definitions-create-delete-or-modify)
- [Enable and disable client-side printing for Reporting Services](/sql/reporting-services/report-server/enable-and-disable-client-side-printing-for-reporting-services)

SSMS provides an integrated environment for managing any SQL infrastructure, including SSRS. In the web portal, you can enable features, set server defaults, manage running jobs, view custom reports, and create and manage shared schedules.

> [!NOTE]  
> While SSMS offers various management capabilities for SSRS, it's not a replacement for Report Manager online or the Report Services Configuration Manager. You should stay updated with the latest versions and documentation to ensure effective management of SSRS within SSMS. If you have any specific questions or need further assistance, feel free to ask.

## Non-English language versions

The Visual Studio Installer selects a default language pack for SSMS that matches the language of your operating system. You can change the default language at any time. For more information, see [Modify SQL Server Management Studio workloads, components, and language packs](install/modify.md).

## Support policy

Starting with SSMS 17.0, the SQL Tools team has adopted the [Microsoft Modern Lifecycle Policy](/lifecycle/policies/modern).

Read the original [Modern Lifecycle Policy announcement](/lifecycle/announcements/modern-policy). For more information, see [Modern Policy FAQs](/lifecycle/faq/modern-policy).

For diagnostic data collection and feature usage information, see the [SQL Server privacy supplement](/sql/sql-server/sql-server-privacy) and [diagnostic data collection](sql-server-management-studio-telemetry-ssms.md).

[!INCLUDE [get-help-options](includes/paragraph-content/get-help-options.md)]

## Related content

- [Modify SQL Server Management Studio workloads, components, and language packs](install/modify.md)
- [Quickstart: Connect and query a SQL Server instance using SQL Server Management Studio (SSMS)](quickstarts/ssms-connect-query-sql-server.md)
- [Tutorial: Write Transact-SQL statements](/sql/t-sql/tutorial-writing-transact-sql-statements)
