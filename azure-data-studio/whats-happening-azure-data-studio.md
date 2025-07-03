---
title: "What's Happening to Azure Data Studio?"
description: Azure Data Studio is being deprecated.
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest, maghan
ms.date: 07/02/2025
ms.service: azure-data-studio
ms.topic: concept-article
ms.collection:
  - data-tools
ms.custom:
  - deprecation-announcement
---

# What's happening to Azure Data Studio?

[!INCLUDE [azure-data-studio-deprecation](includes/azure-data-studio-deprecation.md)]

Azure Data Studio officially retires on February 28, 2026. You should migrate to [Visual Studio Code](https://code.visualstudio.com/download). This change aims to consolidate SQL development tools and provide a more robust and feature-rich environment for the developer community.

This article provides recommendations and resources to help you transition from Azure Data Studio to Visual Studio Code or alternative tools. During this period, all local files and Database Projects in Azure Data Studio remain available.

## Why retire Azure Data Studio?

The desire to retire Azure Data Studio was to simplify and enhance the SQL development experience.

### Key considerations

Visual Studio Code, a widely adopted platform with exceptional community support and an extensive ecosystem of extensions, allows us to deliver advanced features like cutting-edge schema management tools and enhanced developer experiences.

By consolidating efforts on Visual Studio Code, we can deliver advanced features and improved experiences more efficiently. This eliminates duplication, reduces maintenance costs, and accelerates feature delivery.

## Key benefits of migrating to Visual Studio Code

Migrating to Visual Studio Code offers a modern, versatile, and developer-friendly platform that empowers developers with advanced tools, extensive community support, and seamless integration into today's development workflows.

### Modern development environment

- Visual Studio Code is one of the world's most widely used code editors, trusted by millions of developers.
- Lightweight design and rich extension ecosystem.
- Regular updates and active open-source community.
- Built-in features designed to enhance productivity.

### Comprehensive feature set

- **Enhanced query execution**: Faster and more reliable query execution with detailed results and filtering options.
- **Modern schema management**: Tools for visualizing, designing, and managing database schemas.
- **Integration with CI/CD**: Support for automated database deployments and updates.
- **Improved user experience**: Modernized query editor, intelligent suggestions, and error highlighting.

### Cross-platform compatibility

- Like Azure Data Studio, Visual Studio Code runs seamlessly on **Windows**, **macOS**, and **Linux**.
- Provides a consistent development environment across platforms.

### Streamlined workflows

- **CI/CD integration**: Smooth migration from development to deployment.
- **Cloud-native development**: Built-in support for Azure services.
- **Collaboration tools**: Real-time collaboration with [live share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare).
- **Extensive extension marketplace**: Thousands of extensions for tailored workflows.

## Migration plan

Azure Data Studio users have diverse needs, from connecting to Azure SQL databases, to using extensions for non-SQL Server-related capabilities.

> [!NOTE]  
> For users primarily using Azure SQL, Azure SQL Database, or SQL server in Fabric, migrating to Visual Studio Code with the MSSQL extension is straightforward.
> The extension provides comprehensive support for these scenarios, ensuring no loss of functionality.

1. **Install Visual Studio Code and the MSSQL extension**

    - Download and install Visual Studio Code from the official website.
    - Install the MSSQL extension from the Visual Studio Code marketplace.

1. **Migrate Database Projects and queries**:

    - Open SQL database projects directly in Visual Studio Code without migration steps.
    - Queries and scripts from Azure Data Studio are fully compatible with Visual Studio Code.

1. **Explore additional features in Visual Studio Code**:

    - Use advanced schema management tools.
    - Use DevOps workflows, including CI/CD integration.

### Recommended alternatives for SQL Server capabilities in Azure Data Studio

| Azure Data Studio extension | Description | Replacement |
| --- | --- | --- |
| SQL Server Agent | Manage and automate SQL Server Agent jobs. | [SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms) |
| SQL Server Profiler | Trace and monitor SQL Server activity. | [SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms) |
| Database administration | Tools for managing databases on Windows. | [SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms) |
| Schema | Compare and synchronize database schemas. | Visual Studio SQL Server Data Tools (SSDT). In development for MSSQL extension for VS Code. |
| Flat-file import | Import `.txt` and `.csv` files into databases. | Bulk insert / PowerShell. In development for MSSQL extension for Visual Studio Code. |
| DACPAC import/export | Deploy and extract DACPAC files. | SqlPackage / MSSQL extension for Visual Studio Code. |
| SQL Server assessment | Assess an existing SQL Server data estate to prepare for migration. | [Assess migration readiness with SQL Server enabled by Azure Arc](/sql/sql-server/azure-arc/migration-assessment). |
| Azure SQL migration | Migrate SQL Server to Azure SQL. | Alternative migration tools for [Azure SQL Managed Instance](/data-migration/sql-server/managed-instance/overview#migration-tools), [SQL Serve on Azure VMs](/data-migration/sql-server/virtual-machines/overview#migrate), and [Azure SQL Database](/data-migration/sql-server/database/overview#migration-tools). |
| Notebooks | SQL + Markdown interactive documents. | Polyglot Notebooks in Visual Studio Code. |
| SQL Database Projects | Create, manage, and deploy SQL database projects. | Fully supported in the MSSQL extension for VS Code and Visual Studio. |

### Alternative Azure Data Studio capabilities

For users who relied on Azure Data Studio for non-SQL Server-related tasks (for example, **PostgreSQL**, **MySQL**, or **Azure Cosmos DB**), suitable Visual Studio Code alternatives are available.

#### Migration steps

1. Install the relevant Visual Studio Code extensions from the Marketplace.

1. Explore the recommended replacements:

   | Azure Data Studio extension | Description | Replacement |
   | --- | --- | --- |
   | **PostgreSQL** | Manage PostgreSQL databases. | [PostgreSQL extension for Visual Studio Code preview](/azure/postgresql/extensions/vs-code-extension/overview) |
   | **MySQL** | Manage MySQL databases. | Pending announcement |
   | **Azure Cosmos DB** | Manage Azure Cosmos DB API for MongoDB. | [Azure Databases for Visual Studio Code](/azure/cosmos-db/visual-studio-code-extension) |
   | **Azure Cosmos DB Migration for MongoDB** | Migrate MongoDB to Azure Cosmos DB. | Pending announcement |

### Available resources

| Resource | Description |
| --- | --- |
| [Documentation](/sql/tools/visual-studio-code-extensions/mssql/mssql-extension-visual-studio-code) | Access the MSSQL extension for Visual Studio Code documentation for tutorials and guides. |
| [Community support](https://stackoverflow.com/questions/tagged/visual-studio-code) | Join the Visual Studio Code community and explore forums like Stack Overflow. |
| [GitHub issues](https://github.com/microsoft/azuredatastudio/issues) | Submit feature requests or report bugs via the Azure Data Studio GitHub repository. |
| [Microsoft support](https://support.microsoft.com/topic/customer-service-phone-numbers-c0389ade-5640-e588-8b0e-28de8afeb3f2) | Contact Microsoft support for critical issues. |

## Frequently asked questions (FAQ)

Here are answers to questions about the Azure Data Studio deprecation and migration to Visual Studio Code.

### What happens to Azure Data Studio after February 28, 2026?

After **February 28, 2026**, Azure Data Studio will no longer be supported. This means that it stops receiving any updates, security patches, or maintenance after that date. You should migrate to an alternative solution before February 28, 2026, to ensure continued support and security.

### What happens to existing database projects in Azure Data Studio?

Projects can be opened in Visual Studio Code without migration.

### Is there a deadline for migrating?

Azure Data Studio will be retired on **February 6, 2025**, with support until **February 28, 2026**.

### Can my queries and scripts work in Visual Studio Code?

Yes, they're fully compatible.

### What about extensions not yet available in Visual Studio Code?

Refer to the Migration Plan for alternatives.

### Are there plans for missing features like SQL Server Agent?

Features under development include Schema Compare and Dacpac support. Use [SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms) for others.

### How do I install the MSSQL extension for Visual Studio Code?

Install it from the Visual Studio Code Marketplace. Detailed steps are available in the documentation.

### What benefits does Visual Studio Code offer over Azure Data Studio?

A modern, extensible environment with enhanced community support and DevOps integration.

## Related content

- [What is the MSSQL extension for Visual Studio Code?](/sql/tools/visual-studio-code-extensions/mssql/mssql-extension-visual-studio-code)
- [Download Visual Studio Code](https://code.visualstudio.com/download)
- [Visual Studio Code extensions](https://marketplace.visualstudio.com/VSCode)
