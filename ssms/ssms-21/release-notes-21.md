---
title: Release Notes for SQL Server Management Studio 21 Preview
description: Release notes for SQL Server Management Studio 21 Preview (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: maghan, randolphwest
ms.date: 02/11/2025
ms.service: sql-server-management-studio
ms.topic: whats-new
---

# Release notes for SQL Server Management Studio 21 Preview

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

This article details updates, improvements, and bug fixes for the current and previous versions of [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)].

[!INCLUDE [ssms-connect-aazure-ad](../includes/ssms-connect-azure-ad.md)]

## Current SQL Server Management Studio 21 preview release

**[Download SQL Server Management Studio 21 Preview](https://aka.ms/ssms/21/preview/vs_SSMS.exe)**

[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] is the latest preview release of SSMS. If you need a previous version of SSMS, see [previous SSMS releases](../release-notes-ssms.md#previous-ssms-releases).

### 21.0 Preview 4.1

- Release number: 21.0 Preview 4.1
- Build number: 21.0.85
- Release date: February 24, 2025

#### What's new in 21.0 Preview 4.1

| Feature | Details |
| -------- | -------- |
| Visual Studio | Updated to Visual Studio 17.14 Preview 1.1. |

### 21.0 Preview 4

- Release number: 21.0 Preview 4
- Build number: 21.0.85
- Release date: February 11, 2025

#### What's new in 21.0 Preview 4

| Feature | Details |
| --- | --- |
| Account Authentication | Added theme support for Account picker. |
| File | Reinstated the ability to create projects (**File > New > Project or Solution...**) and view recent projects (**File > Open > Project/Solution...**). |
| Help | Enabled support for Developer Community feedback, accessed from **Help > Send Feedback > Report a Problem/Suggest a Feature/My Feedback**. |
| IntelliSense | Added support for `JSON_CONTAINS` built-in functions. |
| IntelliSense | Added support for `REGEXP_` functions. See [SSMS 21 Preview 2: REGEXP_ functions need to be color-coded](https://feedback.azure.com/d365community/idea/a53b6196-11d4-ef11-95f5-000d3ae46bae). |
| Query Store | Added theme support for the search window and grid in the Tracked Queries report. |
| Visual Studio | Updated to Visual Studio 17.14 Preview 1. |

#### Bug fixes in 21.0 Preview 4

| Feature | Details |
| --- | --- |
| Options | Removed localization of `ISOLATION LEVEL` option within **Tools > Options > Query Execution > SQL Server > Advanced**. |
| IntelliSense | Corrected default IntelliSense toolbar icon state to be disabled when IntelliSense is disabled globally. |
| Query Plans | Addressed an issue where canceling a query while running a live query plan caused SSMS to crash. See [Live query statistics hangs waiting for plan and cancelling query kills SSMS](https://feedback.azure.com/d365community/idea/9e4420f1-afac-ee11-92bc-000d3ae54955). |
| Query Plans | Addressed an issue where viewing live query statistics for a table with a geography data type caused an error. |

### 21.0 Preview 3

- Release number: 21.0 Preview 3
- Build number: 21.0.83
- Release date: January 22, 2025

#### What's new in 21.0 Preview 3

| Feature | Details |
| --- | --- |
| Always Encrypted | Introduced online encryption support in the Always Encrypted Wizard, which enables incremental copying, encrypting, decrypting, or re-encrypting of data. See [Configure column encryption using Always Encrypted Wizard in SSMS 21 Preview](/sql/relational-databases/security/encryption/always-encrypted-wizard-ssms-21). |
| Azure SQL Managed Instance | Introduced new validation steps in the Failover Readiness Assessment dialog to assess the health status of the link before failover. |
| Configuration | The default value for a firewall rule name created in SSMS uses the format `ClientIPAddress_YYYY-MM-DD_HH-MM-SS`. |
| Find | Reinstated the **Quick Find** option, accessed through **Edit** > **Find and Replace** > **Quick Find**, or with **CTRL + F**. See [SSMS 21.0 Preview 1.0 - "Quick Find" missing, instead "Find in files" pops up](https://feedback.azure.com/d365community/idea/76326fd1-57b6-ef11-95f6-000d3ae2b698). |
| Installation | Updated the default Code Snippets folder location to be major-version specific (`%USERPROFILE%\Documents\SQL Server Management Studio 21\Code Snippets\SQL\My Code Snippets`). |
| Query Store | Added theme support for Plan Id box and toolbar dropdown lists in Query Store reports. |
| Intellisense | Added support for VECTOR data type. |
| Visual Studio | Updated to Visual Studio 17.13 Preview 3. |

#### Bug fixes in 21.0 Preview 3

| Feature | Details |
| --- | --- |
| Always Encrypted | Addressed an issue where the default constraint was removed after performing in-place encryption in the Always Encrypted Wizard. |
| Connection | Updated the database Connection Properties dialog to show the correct authentication method. |
| Intellisense | Disabling IntelliSense by unchecking **Enable IntelliSense** in **Tools** > **Options** > **Text Editor** > **Transact-SQL** > **IntelliSense** now persists between restarts of SSMS. See [Intellisense enabled for SSMS 21 despite being off in the settings](https://feedback.azure.com/d365community/idea/d7b6fb21-8aa3-ef11-95f6-000d3a01397d). |
| License | Updated the "Microsoft Software License Terms" link in the Visual Studio Install splash screen to direct to the SSMS 21 license. |
| Query Plans | Updated operator Property dialog to correctly display Columns With Stale Statistics warning. |
| Query Store | Improved readability for Plan Id text in the Top Resource Consuming Queries report for High Contrast Mode. |
| Security | Added the ability to assign a new user to a database login from the user properties dialog. |
| Security | Corrected size of "Add" button on the Login Properties dialog. |
| SQL Agent | Removed unsupported SQL Agent features for Azure SQL Managed Instance including targets, multi-server administration, and Operator pager options. |

### 21.0 Preview 2.1

- Release number: 21.0 Preview 2.1
- Build number: 21.0.73
- Release date: December 18, 2024

#### What's new in 21.0 Preview 2.1

| Feature | Details |
| --- | --- |
| Visual Studio | Updated to Visual Studio 17.13 Preview 2.1. |

### 21.0 Preview 2

- Release number: 21.0 Preview 2
- Build number: 21.0.73
- Release date: December 10, 2024

#### What's new in 21.0 Preview 2

| Feature | Details |
| --- | --- |
| Accessibility | Improved accessibility in the View Designer. |
| Always Encrypted | Introduced the capability to generate new keys within the Always Encrypted Wizard that are securely stored in Azure Key Vault Managed HSM (Hardware Security Model). |
| Always Encrypted | Improved performance of the New Column Master Key dialog. |
| Azure Authentication | Introduced the ability to select a tenant within an Azure subscription. Tenant selection is available in dialogs such as creating a new firewall rule, using the Azure Storage browser, and selecting a container for backup to, or restore from, URL. |
| Connection | Updated strict encryption label to **Strict (Minimum SQL 2022 or Azure SQL)** in the **Encryption** dropdown list on the connection dialog. |
| Query Editor | Intellisense errors are updated to map to the IntelliSense dropdown list in the Error List pane. The Error List pane is available from the **View** > **Error List** menu or by selecting the error icon in the file health indicator, located in the bottom left of the Query Editor toolbar. |
| Settings | Changed default startup option for SSMS back to **Open Object Explorer**, within **Tools** > **Options** > **Startup**. |
| Settings | Removed the **Preview** entry from the **Tools** > **Options Experience (requires restart)** menu, as SSMS doesn't currently support Preview Unified settings. |
| Theming | Added dark theme support to tabs and icons in the Results pane of the Query Editor, and to the script splitter bar. |
| Theming | Added dark theme support to the query and plan panes within Query Store reports. |
| Visual Studio | Updated to Visual Studio 17.13 Preview 2. |

#### Bug fixes in 21.0 Preview 2

| Feature | Details |
| --- | --- |
| Always Encrypted | Renamed **Encrypt Column** to **Always Encrypted Wizard** in the Object Explorer context menu. |
| Always Encrypted | Introduced status **Completed With Warnings** for the Always Encrypted Wizard. |
| Connection | Resolved inability to reconnect a query editor after a forced disconnection. See [Forcefully disconnect query window can't reconnect](https://feedback.azure.com/d365community/idea/61623b6d-c7c1-ee11-92bc-000d3a0fb290) |
| Connection | Updated check for open transaction count to not execute against SQL offerings that don't support transactions (for example, Azure synapse serverless pools). See [Query transaction count should not run if enabled from SSMS and underlying engine doesn't support transactions](https://feedback.azure.com/d365community/idea/d453ee93-6e47-ef11-b4ac-000d3a7b1c7e). |
| Connection | Resolved issue where connection dialog might appear while SSMS is still loading. |
| Database Mirroring | Resolved issues in Database Mirroring Monitor where mirrored databases couldn't be registered and server instance connections can't be added. |
| Installer | Corrected the product version listed on the Details page within the Properties of the bootstrapper `vs_SSMS.exe`. |
| Installer | Updated installation to place SSMS 21 and related applications in a folder named **Microsoft SQL Server Tools 21**. See [Rename SSMS 21 to align with pervious versions in Control Panel](https://feedback.azure.com/d365community/idea/c96048d0-d4a1-ef11-95f6-000d3a01397d). |
| Object Explorer | Resolved error "Couldn't load file or assembly 'Microsoft.DataWarehouse, Version=16.2.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The system can't find the file specified." when trying to filter in Object Explorer. See [SSMS 21 Preview 1 - Right-click "Filter settings" does not work](https://feedback.azure.com/d365community/idea/fbad8782-30a8-ef11-95f6-000d3ae2b698). |
| Object Explorer | Removed the overlapped display new object name and original object name when renaming an object in Object Explorer. |
| Query Plans | Resolved behavior where selecting showplan XML in the results grid opened the plan as XML instead of the graphical display. |
| Query Store Reports | Fixed problem where changes to configuration in the Tracked Queries report weren't retained. |
| Query Store Reports | Implemented sizing restrictions for the Configuration dialog to prevent a degraded display. |
| Scripting | Addressed a problem where the updated value for **Auto Create Incremental Statistics** wasn't included when scripting the change for Azure SQL Database. |
| Scripting | Removed ```USE Database Name``` syntax when generating scripts for users in Azure SQL Database. |
| Settings | Fixed issue where importing settings on a non-English Operating System (OS) generated an error. |
| Settings | Removed **CodeLens** from **Tools** > **Options** > **Text Editor** > **All Languages**. |
| Settings | Removed duplicate and irrelevant entries from **Tools** > **Options** > **Text Editor** > **File Extensions**. |
| Theming | Resolved an issue where the Messages tab in the Results pane wouldn't pick up a theme change until SSMS was restarted. |
| Theming | Improved handling of NULL cells in the results grid. |
| Theming | Fixed incorrect theming for Extended Events context menus. |
| Theming | Improved themed support for **Recently Used Templates** in Template Explorer. |
| Theming | Improved theme support in the Messages tab of the results pane. |
| Theming | Addressed issue where the results window would show as white until the results appeared with dark theme enabled. |

### 21.0 Preview 1

- Release number: 21.0 Preview 1
- Build number: 21.0.47
- Release date: November 12, 2024

#### What's new in 21.0 Preview 1

| Feature | Details |
| --- | --- |
| 64-bit | SSMS 21 is a Visual Studio 2022-based application that supports 64-bit, ensuring smoother operations and reducing out-of-memory errors. |
| Always Encrypted | An assessment for Always Encrypted is available in the wizard. It can be found under the **Always Encrypted Wizard** menu (formerly named **Encrypt Columns...**) after right-clicking a database and selecting **Tasks**. For more information, see [Always Encrypted Assessment in SQL Server Management Studio 21](https://techcommunity.microsoft.com/blog/azuresqlblog/always-encrypted-assessment-and-online-encryption-in-sql-server-management-studi/4286148). |
| Azure Authentication | Azure Authentication encompasses a subset of dialogs where authentication to Azure is required. Examples of these dialogs include adding an Azure firewall rule, configuring the Service Level Objective (SLO) when creating an Azure database, and the Azure storage browser. |
| Azure SQL Database | Introduced UI support for creating logins and database users. |
| Dark theme | SSMS 21 supports dark theme for selected dialogs, including Object Explorer, Query Editor, Results pane, and Template Explorer. |
| Database Properties | Added a page to list Database Scoped Configuration values on the **Database Properties** dialog. |
| Drivers | Updated Microsoft.Data.SqlClient (MDS) to version 5.1.6. |
| Git | Support for Git integration returns in SSMS 21 to support the growing emphasis on CI/CD, which can be found in the **Git** menu. Select **Settings** to configure options specific to Git. The Git integration allows developers and database administrators to track, manage, and collaborate on SQL scripts seamlessly within the SSMS environment, including support for creating and cloning repositories and creating and managing branches. |
| Installation | SSMS 21 is installed using the Visual Studio Installer. For more information, see [Install SQL Server Management Studio 21 Preview](../install/install.md). |
| Language support | Introduced support for SSMS in Czech, Polish, and Turkish. |
| Libraries | Updated Azure.Core to version 1.41.0. |
| Libraries | Updated DacFx to version 162.4.92. |
| Libraries | Updated Server Management Objects (SMO) to version 17.100.52. |
| Libraries | Updated System.Text.Json to version 8.0.4. |
| Query Editor | The scroll bar for the query editor in SSMS 21 defaults to **map mode**. To change the option, right-click the scroll bar and select **Scroll Bar Options...**. Within the **Options** dialog, you can change the display to **Use bar mode for vertical scroll bar**. |
| Query Store | The Query Store reports feature a **Replica** dropdown list, allowing users to view Query Store data across various replica sets or roles. For more information, see [sys.query_store_replicas](/sql/relational-databases/system-catalog-views/sys-query-store-replicas) to understand the current association between a replica and its role. When the [Query Store for secondary replicas](/sql/relational-databases/performance/query-store-for-secondary-replicas) feature is enabled, data populates exclusively for roles that are deployed and designated as replicas. |
| Sign in | Users can now access their Azure and GitHub accounts from SSMS 21. Sign-in isn't required to install or use SSMS 21. For more information, see [Access multiple accounts in SQL Server Management Studio 21 Preview](sign-in-access-multiple-accounts.md). |
| Terminal | Introduced integrated terminal access from the **View** menu to support writing and executing command line and PowerShell commands. |
| User Interface | The updated SSMS interface has a refreshed, modernized design optimized for a streamlined experience that integrates with high-DPI displays. The new design includes updated icons, a modern dark theme, and customizable layouts to suit your preferences. |
| Visual Studio | Updated to Visual Studio 17.13 Preview 1. |

#### Bug fixes in 21.0 Preview 1

| Feature | Details |
| --- | --- |
| Azure SQL Database | Addressed issue of SSMS hanging when trying to connect to an Azure SQL Database that was deleted. |
| Azure SQL Database | Resolved the problem of SSMS becoming inaccessible when a user doesn't have permissions to access all the databases on a logical server. |
| Azure SQL Database | Fixed the behavior of SSMS hanging and generating the error "An error occurred while changing the current database." The error occurs when an invalid database name is entered in the database name dropdown list for the editor window. |
| Azure SQL Managed Instance | Removed the ability to select an alternate option for **Login auditing** within the **Server Properties** dialog. |
| Azure SQL Managed Instance | Removed the ability to configure the number of error log files in the **Configure SQL Server Error Logs** dialog. |
| Central Management Server | Added ability to save the **Trust Server Certificate** connection option. |

### Known issues 21.0 Preview

See [Known issues in SQL Server Management Studio 21 Preview](known-issues.md) for known issues using [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)].

[!INCLUDE [support](../includes/support.md)]

## Related content

- [Install SQL Server Management Studio 21 Preview](../install/install.md)
- [SQL Server Management Studio 21 Preview FAQ](faq.yml)
- [Visual Studio 2022 Preview release notes](/visualstudio/releases/2022/release-notes-preview)
