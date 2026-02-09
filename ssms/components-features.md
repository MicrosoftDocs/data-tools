---
title: "Components and Features"
titleSuffix: SQL Server Management Studio
description: Discover capabilities and where to start with each component in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.date: 02/06/2026
ms.service: sql-server-management-studio
ms.topic: overview
ms.collection:
  - data-tools
---
# Components and features in SQL Server Management Studio

[!INCLUDE [SQL Server ASDB, ASDBMI, ASDW](includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

This article describes the components and features available in [!INCLUDE [ssmanstudiofull-md](includes/ssmanstudiofull-md.md)] (SSMS).

## Feature overview

| Component or feature | Description | Article |
| --- | --- | --- |
| **GitHub Copilot in SSMS (Preview)** | Chat, code actions (Document, Explain, Fix, Optimize), walkthrough, model selection, and Bring Your Own Model (BYOM). | [Get started with GitHub Copilot in SQL Server Management Studio (Preview)](github-copilot/get-started.md) |
| **Query Hint Recommendation Tool (Preview)** | Analyze statements and apply recommended hints. Installed via **Visual Studio Installer** > **Individual Components** > **Code Tools**. | [Query Hint Recommendation tool (Preview)](query-hint-tool/hint-tool-overview.md) |
| **Git integration** | Integration with Git for tracking, managing, and collaborating on SQL scripts. Clone and create repositories, manage branches, and view diffs inside SSMS, using the same familiar interface as Visual Studio. | [About Git in Visual Studio](/visualstudio/version-control/git-with-visual-studio) |
| **Modern connection dialog** | Browse Microsoft Fabric resources, copy and paste connection strings, and manage encryption and certificate options more easily. | [Quickstart: Connect and query a SQL Server instance](quickstarts/ssms-connect-query-sql-server.md) |
| **SQL Server migration component** | Assess, prepare, and migrate your [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)] databases. | [SQL Server migration component in SQL Server Management Studio](migrate-sql-server-component.md) |
| **Object Explorer** | View and manage all objects in one or more instances of the [!INCLUDE [ssdenoversion-md](includes/ssdenoversion-md.md)]. | [Object Explorer](object/object-explorer.md) |
| **Template Explorer** | Build and manage files of boilerplate text that you use to speed the development of queries and scripts. | [Template Explorer](template/template-explorer.md) |
| **Visual Database Tools** | Use the visual design tools included in SSMS to build queries, tables, and diagram databases. | [Visual Database Tools](visual-db-tools/visual-database-tools.md) |
| **Query Editor** | Use the SSMS language editors to interactively build queries and scripts. | [Query and text editors](f1-help/database-engine-query-editor-sql-server-management-studio.md) |

## Management, security, and productivity

This section describes management, security, developer, and productivity capabilities in SSMS.

### Database engine support

SSMS supports the following database engines:

- [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)] on Windows, Linux, and containers
  - [!INCLUDE [sssql25-md](includes/sssql25-md.md)]
  - [!INCLUDE [sssql22-md](includes/sssql22-md.md)]
  - [!INCLUDE [sssql19-md](includes/sssql19-md.md)]
  - [!INCLUDE [sssql17-md](includes/sssql17-md.md)]
  - [!INCLUDE [sssql16-md](includes/sssql16-md.md)]
  - [!INCLUDE [sssql14-md](includes/sssql14-md.md)]
- [Azure SQL Database](/azure/azure-sql/database/sql-database-paas-overview)
- [Azure SQL Managed Instance](/azure/azure-sql/managed-instance/sql-managed-instance-paas-overview)
- [SQL Server on Azure Virtual Machines](/azure/azure-sql/virtual-machines/windows/sql-server-on-azure-vm-iaas-what-is-overview)
- [SQL database in Microsoft Fabric](/fabric/database/sql/overview)
- [Azure Synapse Analytics](/azure/synapse-analytics/sql-data-warehouse/sql-data-warehouse-overview-what-is/)

### Encryption and security

SSMS supports the latest [TLS 1.3](/sql/relational-databases/security/networking/tls-1-3) and [TDS 8](/sql/relational-databases/security/networking/tds-8) encryption options.

### Indexes and data types

SSMS includes full support for JSON and vectors. You can also view JSON data in the results pane.

### Business intelligence administration

You can use SSMS to access, configure, manage, and administer Analysis Services (SSAS), Integration Services (SSIS), and Reporting Services (SSRS).

> [!NOTE]  
> To create and modify SSAS, SSIS, and SSRS solutions, use [SQL Server Data Tools (SSDT)](/sql/ssdt/sql-server-data-tools).

| Component | Details |
| --- | --- |
| **SSIS** | Manage the `SSISDB` catalog, execute packages, and use the Import/Export Wizard. |
| **SSAS** | Script projects using MDX, DAX, DMX, or XMLA, and handle object processing and backups. |
| **SSRS** <sup>1</sup> | Perform server-level administration tasks like managing roles, jobs, and schedules for [!INCLUDE [sssql22-md](includes/sssql22-md.md)] and earlier versions. |

<sup>1</sup> For more information, see [Reporting Services consolidation FAQ](/sql/reporting-services/reporting-services-consolidation-faq).

### Productivity and user experience

SSMS includes the following new features and improvements:

- Presenter mode improvements.
- Integrated terminal access.
- Dark mode theme.
- Support for new data types and indexes in Object Explorer and results pane.

### Platform compatibility

SSMS is available for x86-64 and Arm64 processors on Windows.

For more information about Arm64 support, see:

- [SQL Server Management Studio product roadmap](roadmap.md)
- [Known issues in SQL Server Management Studio](known-issues.md)

## Release notes and known issues

- [Release notes for SQL Server Management Studio 22](release-notes-22.md)
- [Release notes for SQL Server Management Studio 21](release-notes-21.md)
- [Release notes for SQL Server Management Studio 20](release-notes-20.md)
- [Known issues in SQL Server Management Studio](known-issues.md)

## Related content

- [What is SQL Server Management Studio (SSMS)?](sql-server-management-studio-ssms.md)
- [Install SQL Server Management Studio](install/install.md)
- [Modify SQL Server Management Studio workloads, components, and language packs](install/modify.md)
- [Tutorial: Write Transact-SQL statements](/sql/t-sql/tutorial-writing-transact-sql-statements)
