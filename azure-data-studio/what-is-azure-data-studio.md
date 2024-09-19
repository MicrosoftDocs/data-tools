---
title: What is Azure Data Studio
description: Azure Data Studio is a free, light-weight tool that runs on Windows macOS, and Linux, for managing SQL Server, Azure SQL Database, and Azure Synapse Analytics.
author: "markingmyname"
ms.author: "maghan"
ms.reviewer: dlevy
ms.date: 09/19/2024
ms.service: azure-data-studio
ms.topic: overview
ms.custom:
  - intro-overview
---

# What is Azure Data Studio?

Azure Data Studio is a powerful, cross-platform data management and development tool for data professionals. It provides a modern editor experience with IntelliSense, code snippets, source control integration, and an integrated terminal, making it easier to manage and develop databases.

With Windows, macOS, and Linux support, Azure Data Studio allows you to connect to various databases, including Azure SQL, SQL Server, MySQL, PostgreSQL, and Cosmos DB. Its extensibility enables users to customize their experience by installing relevant extensions for their workflow.

Azure Data Studio's familiar interface offers a modern editor experience with IntelliSense, code snippets, source control integration, and an integrated terminal. Engineered with the data platform user in mind, its extensibility allows users to customize their experience by installing the extensions relevant to their workflow, including database migrations, charting, GitHub Copilot, and more!

The source code for Azure Data Studio and its data providers is available on GitHub under a source code EULA that provides rights to modify and use the software but not redistributing it or hosting it in a cloud service. See [Azure Data Studio FAQ](faq.yml) for more information.

**[Download and Install Azure Data Studio](./download-azure-data-studio.md)**

## SQL code editor with IntelliSense

Azure Data Studio offers a modern, keyboard-focused SQL coding experience that makes everyday tasks easier with built-in features like multiple tab windows, a rich SQL editor, IntelliSense, keyword completion, code snippets, code navigation, and source control integration (Git). Run on-demand SQL queries and view and save results as text, JSON, or Excel. Edit data, organize your favorite database connections, and browse database objects in a familiar object browsing experience. To learn how to use the SQL editor, see [Use the SQL editor to create database objects](tutorial-sql-editor.md).

## Smart SQL code snippets

SQL code snippets generate the proper SQL syntax to create databases, tables, views, stored procedures, users, logins, and roles and update existing database objects. Use smart snippets to quickly create copies of your database for development or testing purposes and to generate and execute CREATE and INSERT scripts.

Azure Data Studio also provides functionality to create custom SQL code snippets. See [Create and use code snippets](code-snippets.md) to learn more.

## Customizable Server and Database Dashboards

Create rich customizable dashboards to monitor and quickly troubleshoot performance bottlenecks in your databases. To learn about insight widgets and database (and server) dashboards, see [Manage servers and databases with insight widgets](insight-widgets.md).

## Connection management (server groups)

Server groups provide a way to organize connection information for the servers and databases you work with. For details, see [Server groups](server-groups.md).

## Integrated Terminal

You can use your favorite command-line tools (for example, Bash, PowerShell, sqlcmd, BCP, and ssh) in the Integrated Terminal window right within the Azure Data Studio user interface. See [Integrated terminal](integrated-terminal.md) to learn about the integrated terminal.

## Extensibility and extension authoring

Enhance the Azure Data Studio experience by extending the functionality of the base installation. Azure Data Studio provides extensibility points for data management activities and support for extension authoring.

To learn about extensibility in Azure Data Studio, see [Extensibility](extensibility.md).
See [Extension authoring](extensions/extension-authoring.md) to learn about authoring extensions.

## Feature comparison with SQL Server Management Studio (SSMS)

**Use Azure Data Studio if you:**

- Are mostly editing or executing queries.
- Need the ability to chart and visualize result sets quickly.
- Can execute most administrative tasks via the integrated terminal using sqlcmd or PowerShell.
- Have minimal need for wizard experiences.
- You don't need to do deep administrative or platform-related configuration.
- It needs to run on macOS or Linux.

**Use SQL Server Management Studio if you:**

- Are doing complex administrative or platform configuration.
- Are doing security management, including user management, vulnerability assessment, and configuration of security features.
- Performance tuning advisors and dashboards need to be made use of.
- Use database diagrams and table designers.
- Need access to Registered Servers.
- Make use of live query stats or client statistics.

### Shell features

| Feature | Azure Data Studio | SSMS |
| :--- | :--- | :--- |
| Azure Sign-In | Yes | Yes |
| Dashboard | Yes | |
| Extensions | Yes | |
| Integrated Terminal | Yes | |
| Object Explorer | Yes | Yes |
| Object Scripting | Yes | Yes |
| Select from Table | Yes | Yes |
| Source Code Control | Yes | |
| Task Pane | Yes | |
| Themes, including Dark Mode | Yes | |
| Azure Resource Explorer | Yes | |
| Generate Scripts Wizard | | Yes |
| Object Properties | Preview | Yes |
| Table Designer | Yes | Yes |

### Query Editor

| Feature | Azure Data Studio | SSMS |
| :--- | :--- | :--- |
| Chart Viewer | Yes | |
| Export Results to CSV, JSON, XLSX | Yes | |
| Results to File | | Yes |
| Results to Text | | Yes |
| IntelliSense | Yes | Yes |
| Snippets | Yes | Yes |
| Show Plan | Yes | Yes |
| Client Statistics | | Yes |
| Live Query Stats | | Yes |
| Query Options | | Yes |
| Spatial Viewer | | Yes |
| SQLCMD | Yes | Yes |

### Operating System Support

| Feature | Azure Data Studio | SSMS |
| :--- | :--- | :--- |
| Windows | Yes | Yes |
| macOS | Yes | |
| Linux | Yes | |

### Data Engineering

| Feature | Azure Data Studio | SSMS |
| :--- | :--- | :--- |
| External Data Wizard | Preview | |
| HDFS Integration | Preview | |
| Notebooks | Preview | |

### Database Administration

| Feature | Azure Data Studio | SSMS |
| :--- | :--- | :--- |
| Backup / Restore | Preview | Yes |
| Flat File Import | Yes | Yes |
| SQL Agent | Preview | Yes |
| SQL Profiler | Preview | Yes |
| Always On | | Yes |
| Always Encrypted | | Yes |
| Copy Data Wizard | | Yes |
| Data Tuning Advisor | | Yes |
| Database Diagrams | | Yes |
| Error Log Viewer | | Yes |
| Maintenance Plans | | Yes |
| Multi-Server Query | | Yes |
| Policy Based Management | | Yes |
| PolyBase | | Yes |
| Query Store | | Yes |
| Registered Servers | | Yes |
| Replication | | Yes |
| Security Management | Yes | Yes |
| Service Broker | | Yes |
| SQL Assessment | Preview | Yes |
| SQL Mail | | Yes |
| Template Explorer | | Yes |
| Vulnerability Assessment | | Yes |
| XEvent Management | | Yes |

### Database Development

| Feature | Azure Data Studio | SSMS |
| :--- | :--- | :--- |
| Import\Export DACPAC | Yes | Yes |
| SQL Projects | Preview | |
| Schema Compare | Yes | |

## SQL Tools Service

Azure Data Studio uses the [SqlToolsService](https://github.com/microsoft/sqltoolsservice) as the application's SQL API layer. SQL Tools Service is .NET-based and open source under the MIT license. For SQL connectivity, SQL Tools Service uses [Microsoft.Data.SqlClient](https://github.com/dotnet/SqlClient) as the SQL driver.

## Related content

- [Download and Install Azure Data Studio](./download-azure-data-studio.md)
- [Azure Data Studio FAQ](faq.yml)
- [Connect and query SQL Server](quickstart-sql-server.md)
- [Connect and query Azure SQL Database](quickstart-sql-database.md)
- [Download SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms)

[!INCLUDE [get-help-sql-tools](includes/get-help-sql-tools.md)]
[!INCLUDE [contribute-to-content](includes/contribute-to-content.md)]
