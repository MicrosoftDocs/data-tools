---
title: "Release Notes for SQL Server Management Studio (SSMS)"
description: Release notes for SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: maghan, randolphwest, mbarickman
ms.date: 05/28/2025
ms.service: sql-server-management-studio
ms.topic: whats-new
ms.collection:
  - data-tools
---

# Release notes for SQL Server Management Studio (SSMS)

[!INCLUDE [sql-asdb-asdbmi-asa](includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

This article details updates, improvements, and bug fixes for the current version of [!INCLUDE [ssms-21-md](includes/ssms-21-md.md)].

[!INCLUDE [ssms-connect-aazure-ad](includes/ssms-connect-azure-ad.md)]

## Current SQL Server Management Studio release

**[Download SQL Server Management Studio (SSMS) 21](https://aka.ms/ssms/21/release/vs_SSMS.exe)**

[!INCLUDE [ssms-21-md](includes/ssms-21-md.md)] is the latest general availability (GA) release of SSMS.

For previous versions of SSMS, see:

- [Release notes for SQL Server Management Studio (SSMS) 20](release-notes-20.md)
- [Release notes for SQL Server Management Studio (SSMS) 19 and earlier versions](release-notes-19.md)

<a id="21.1.3"></a>

### 21.1.3

**[Download SQL Server Management Studio (SSMS) 21](https://aka.ms/ssms/21/release/vs_SSMS.exe)**

- Release number: 21.1.3
- Release date: May 27, 2025

#### What's new in 21.1.3

| Feature | Details |
| --- | --- |
| Visual Studio | Updated to Visual Studio 17.14.3. |

#### Bug fixes in 21.1.3

| Feature | Details |
| --- | --- |
| Extended Events | Fixed a bug where the context menu for Extended Events while Dark theme was enabled didn't have enough contrast to be readable. See [Filter context menu ExtEvents not readable](https://developercommunity.visualstudio.com/t/Filter-context-menu-ExtEvents-not-readab/10900655). |
| Localization | Addressed an issue where reports weren't honoring the selected language in **Tools > Options > International Settings**. See [Wrong language located in elements in SSMS 21 and Profiler 21](https://developercommunity.visualstudio.com/t/Wrong-language-located-elements-in-SSMS-/10898516). |
| Object Explorer Details | Fixed an issue where adding additional columns to the Object Explorer details pane generated an error. See [Invalid object reference in Object Explorer Details pane](https://developercommunity.visualstudio.com/t/Invalid-object-reference-in-Object-Explo/10898449). |

<a id="21.0.1"></a>

### 21.0.1

- Release number: 21.0.1
- Release date: May 21, 2025

#### What's new in 21.0.1

| Feature | Details |
| --- | --- |
| Visual Studio | Updated to Visual Studio 17.14.1. |

<a id="21.0.0"></a>

### 21.0.0

- Release number: 21.0.0
- Release date: May 19, 2025

#### What's new in 21.0.0

| Feature | Details |
| --- | --- |
| 64-bit | SSMS 21 is a Visual Studio 2022-based application that supports 64-bit, ensuring smoother operations and reducing out-of-memory errors. |
| Always Encrypted | Introduced online encryption support in the Always Encrypted Wizard, which enables incremental copying, encrypting, decrypting, or re-encrypting of data. See [Configure column encryption using Always Encrypted Wizard in SSMS 21](/sql/relational-databases/security/encryption/always-encrypted-wizard-ssms-21). |
| Always Encrypted | Introduced the capability to generate new keys within the Always Encrypted Wizard that are securely stored in Azure Key Vault Managed HSM (Hardware Security Model). |
| Always Encrypted | Improved performance of the New Column Master Key dialog. |
| Always Encrypted | An assessment for Always Encrypted is available in the wizard. It can be found under the **Always Encrypted Wizard** menu (formerly named **Encrypt Columns...**) after right-clicking a database and selecting **Tasks**. For more information, see [Always Encrypted Assessment in SQL Server Management Studio 21](https://techcommunity.microsoft.com/blog/azuresqlblog/always-encrypted-assessment-and-online-encryption-in-sql-server-management-studi/4286148). |
| Azure Authentication | Introduced the ability to select a tenant within an Azure subscription. Tenant selection is available in dialogs such as creating a new firewall rule, using the Azure Storage browser, and selecting a container for backup to, or restore from, URL. |
| Azure SQL Database | Added support for MANUAL_CUTOVER and PERFORM_CUTOVER. For more information, see [Improving the conversion to Hyperscale with greater efficiency](https://techcommunity.microsoft.com/blog/azuresqlblog/improving-the-conversion-to-hyperscale-with-greater-efficiency/4377505). |
| Azure SQL Database | Introduced UI support for creating logins and database users. |
| Azure SQL Managed Instance | Introduced new validation steps in the Failover Readiness Assessment dialog to assess the health status of the link before failover. |
| Command Line | Added the `-A` option to specify the authentication method to use when connecting from the command line. Accepted values are authentication types from [SqlAuthenticationMethod](/dotnet/api/microsoft.data.sqlclient.sqlauthenticationmethod) supported by SSMS. The `–G` (use Entra ID authentication) and `–E` (use Windows Authentication) options are now deprecated and will be removed in a later version. |
| Configuration | The default value for a firewall rule name created in SSMS uses the format `ClientIPAddress_YYYY-MM-DD_HH-MM-SS`. |
| Connection | When you connect to a server from command line parameters, SSMS displays a prompt to confirm the connection and parameters. |
| Connection | Added **Close Idle SQL Connections** command under the Help menu. For more information, see [Connection Pooling in SQL Server Management Studio](https://aka.ms/ssms-close-idle-connections). |
| Connection Dialog | Updated strict encryption label to **Strict (Minimum SQL 2022 or Azure SQL)** in the **Encryption** dropdown list on the connection dialog. |
| Connection Dialog | Introduced a Modern connection dialog experience for SQL Server database engines. You can enable or disable this experience within **Tools > Options > Environment > Connection Dialog**. |
| Connection Dialog | Added dark mode support for Modern connection dialog (Preview). See [New connection dialog does not support dark mode](https://developercommunity.microsoft.com/t/New-connection-dialog-does-not-support-d/10893407?q=%22dark%22). |
| Copilot in SSMS | Added [Copilot in SSMS (preview)](copilot/copilot-in-ssms-overview.md) available from the AI Assistance workload in the Visual Studio Installer. |
| Database Properties | Added a page to list Database Scoped Configuration values on the **Database Properties** dialog. |
| Database Properties | Added support for [!INCLUDE [sssql25-md](includes/sssql25-md.md)] FULLTEXT_INDEX_VERSION configuration options in the database properties dialog. |
| Drivers | Updated Microsoft.Data.SqlClient (MDS) to version 5.1.6. |
| File | Reinstated the ability to create projects (**File > New > Project or Solution...**) and view recent projects (**File > Open > Project/Solution...**). |
| Find | Reinstated the **Quick Find** option, accessed through **Edit** > **Find and Replace** > **Quick Find**, or with **CTRL + F**. See [SSMS 21.0 Preview 1.0 - "Quick Find" missing, instead "Find in files" pops up](https://feedback.azure.com/d365community/idea/76326fd1-57b6-ef11-95f6-000d3ae2b698). |
| Git | Support for Git integration returns in SSMS 21 to support the growing emphasis on CI/CD, which can be found in the **Git** menu. Select **Settings** to configure options specific to Git. The Git integration allows developers and database administrators to track, manage, and collaborate on SQL scripts seamlessly within the SSMS environment, including support for creating and cloning repositories and creating and managing branches. |
| Help | Enabled support for Developer Community feedback, accessed from **Help > Send Feedback > Report a Problem/Suggest a Feature/My Feedback**. |
| Individual Components (Visual Studio Installer) | Reinstated Analysis Services and Reporting Services as Business Intelligence components in the Visual Studio Installer. |
| Installation | Updated the default Code Snippets folder location to be major-version specific (`%USERPROFILE%\Documents\SQL Server Management Studio 21\Code Snippets\SQL\My Code Snippets`). |
| Installation | SSMS 21 is installed using the Visual Studio Installer. For more information, see [Install SQL Server Management Studio](install/install.md). |
| IntelliSense | Added support for Vector data type and functions. |
| IntelliSense | Added support for `JSON_CONTAINS` built-in functions. |
| IntelliSense | Added support for `REGEXP_` functions. See [SSMS 21 Preview 2: REGEXP_ functions need to be color-coded](https://feedback.azure.com/d365community/idea/a53b6196-11d4-ef11-95f5-000d3ae46bae). |
| Language support | Introduced support for SSMS in Czech, Polish, and Turkish. |
| Libraries | Updated Server Management Objects (SMO) to version 17.100.64. |
| Libraries | Updated Azure.Core to version 1.41.0. |
| Libraries | Updated DacFx to version 170.0.94. |
| Libraries | Updated System.Text.Json to version 8.0.4. |
| Migration Component | Added the [SQL Server migration component](migrate-sql-server-component.md) under **Individual Components > Hybrid and Migration** in the Visual Studio Installer. |
| Presenter Mode | Reinstated [Presenter mode](presenter-mode.md) as an option under **View > Presenter Mode**. |
| Query Editor | Intellisense errors are updated to map to the IntelliSense dropdown list in the Error List pane. The Error List pane is available from the **View** > **Error List** menu or by selecting the error icon in the file health indicator, located in the bottom left of the Query Editor toolbar. |
| Query Editor | The scroll bar for the query editor in SSMS 21 defaults to **map mode**. To change the option, right-click the scroll bar and select **Scroll Bar Options...**. Within the **Options** dialog, you can change the display to **Use bar mode for vertical scroll bar**. |
| Query Plans | Added JSON index and Implicit Broadcast support to Query Plans. |
| Query Store | Added theme support for the search window and grid in the Tracked Queries report. |
| Query Store | Added theme support for Plan ID box and toolbar dropdown lists in Query Store reports. |
| Query Store | The Query Store reports feature a **Replica** dropdown list, allowing users to view Query Store data across various replica sets or roles. For more information, see [sys.query_store_replicas](/sql/relational-databases/system-catalog-views/sys-query-store-replicas) to understand the current association between a replica and its role. When the [Query Store for readable secondaries](/sql/relational-databases/performance/query-store-for-secondary-replicas) feature is enabled, data populates exclusively for roles that are deployed and designated as replicas. |
| Results Grid | Added the ability to customize the Results Grid cell border color. See [SSMS 21 - Add option to change ResultGrid cell border color](https://developercommunity.visualstudio.com/t/SSMS-21---Add-option-to-change-ResultGri/10859450). |
| Scripting | Added support for scripting objects that use the Vector data type. |
| Settings | Changed default startup option for SSMS back to **Open Object Explorer**, within **Tools** > **Options** > **Startup**. |
| Settings | Removed the **Preview** entry from the **Tools** > **Options Experience (requires restart)** menu, as SSMS doesn't currently support Preview Unified settings. |
| Sign in | Users can now access their Azure and GitHub accounts from SSMS 21. Sign-in isn't required to install or use SSMS 21. For more information, see [Access multiple accounts in SQL Server Management Studio](sign-in-access-multiple-accounts.md). |
| Terminal | Introduced integrated terminal access from the **View** menu to support writing and executing command line and PowerShell commands. |
| Theming | SSMS 21 supports dark theme for selected dialogs, including Object Explorer, Query Editor, Results pane, and Template Explorer. |
| Theming | Added theme support for Account picker. |
| Theming | Improved dark theme support for Query Store, Query Plans, and Object Explorer Details window. |
| Theming | Improved dark theme support for the Activity Monitor and Object Explorer Details dialogs. |
| Theming | Added dark theme support to tabs and icons in the Results pane of the Query Editor, and to the script splitter bar. |
| Theming | Added dark theme support to the query and plan panes within Query Store reports. |
| Tools | Removed Azure Data Studio entry from the Tools menu. For more information, see [What's Happening to Azure Data Studio](https://aka.ms/ads-retirement). |
| User Interface | The updated SSMS interface has a refreshed, modernized design optimized for a streamlined experience that integrates with high-DPI displays. The new design includes updated icons, a modern dark theme, and customizable layouts to suit your preferences. |
| Vector Data Types | Added support for Vector data type in object designers, the edit data window, and Object Explorer. |
| Visual Studio | Updated to Visual Studio 17.14.0. |

#### Bug fixes in 21.0.0

| Feature | Description |
| --- | --- |
| Accessibility | Fixed keyboard navigation issues in Profiler. |
| Always Encrypted | Renamed **Encrypt Column** to **Always Encrypted Wizard** in the Object Explorer context menu. |
| Always Encrypted | Introduced status **Completed With Warnings** for the Always Encrypted Wizard. |
| Azure SQL Database | Addressed issue of SSMS hanging when trying to connect to an Azure SQL Database that was deleted. |
| Azure SQL Database | Resolved the problem of SSMS becoming inaccessible when a user doesn't have permissions to access all the databases on a logical server. |
| Azure SQL Database | Fixed the behavior of SSMS hanging and generating the error "An error occurred while changing the current database." The error occurs when an invalid database name is entered in the database name dropdown list for the editor window. |
| Azure SQL Managed Instance | Removed the ability to select an alternate option for **Login auditing** within the **Server Properties** dialog. |
| Azure SQL Managed Instance | Removed the ability to configure the number of error log files in the **Configure SQL Server Error Logs** dialog. |
| Central Management Server | Added ability to save the **Trust Server Certificate** connection option. See [SSMS - Registered Servers and CMS do not persist auth settings for encryption](https://feedback.azure.com/d365community/idea/27452b60-0af8-ee11-a1ff-00224827349c). |
| Connection | Resolved inability to reconnect a query editor after a forced disconnection. See [Forcefully disconnect query window can't reconnect](https://feedback.azure.com/d365community/idea/61623b6d-c7c1-ee11-92bc-000d3a0fb290). |
| Connection | Updated check for open transaction count to not execute against SQL offerings that don't support transactions (for example, Azure synapse serverless pools). See [Query transaction count should not run if enabled from SSMS and underlying engine doesn't support transactions](https://feedback.azure.com/d365community/idea/d453ee93-6e47-ef11-b4ac-000d3a7b1c7e). |
| Connection | Updated the database Connection Properties dialog to show the correct authentication method. |
| Import/Export Data-Tier Application | Updated the file and log location to use default instead of `master` database location during a bacpac import. |
| IntelliSense | Corrected default IntelliSense toolbar icon state to be disabled when IntelliSense is disabled globally. |
| Options | Removed localization of `ISOLATION LEVEL` option within **Tools > Options > Query Execution > SQL Server > Advanced**. |
| Query Plans | Addressed an issue where canceling a query while running a live query plan caused SSMS to crash. See [Live query statistics hangs waiting for plan and cancelling query kills SSMS](https://feedback.azure.com/d365community/idea/9e4420f1-afac-ee11-92bc-000d3ae54955). |
| Query Plans | Updated operator Property dialog to correctly display Columns With Stale Statistics warning. |
| Security | Added the ability to assign a new user to a database login from the user properties dialog. |
| Scripting | Addressed a problem where the updated value for **Auto Create Incremental Statistics** wasn't included when scripting the change for Azure SQL Database. |
| Scripting | Removed `USE Database Name` syntax when generating scripts for users in Azure SQL Database. |
| Settings | Fixed issue where importing settings on a non-English Operating System (OS) generated an error. |
| SQL Agent | Removed unsupported SQL Agent features for Azure SQL Managed Instance including targets, multi-server administration, and Operator pager options. |

## Known issues

For more information, see [Known issues in SQL Server Management Studio](known-issues.md).

[!INCLUDE [support](includes/support.md)]

## Related content

- [Install SQL Server Management Studio](install/install.md)
- [SQL Server Management Studio 21 FAQ](faq.yml)
- [Visual Studio 2022 release notes](/visualstudio/releases/2022/release-notes)
