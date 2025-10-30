---
title: "Release Notes for SQL Server Management Studio (SSMS)"
description: Release notes for SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, mbarickman
ms.date: 10/30/2025
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

<a id="21.6.17"></a>

### 21.6.17

**[Download SQL Server Management Studio (SSMS) 21](https://aka.ms/ssms/21/release/vs_SSMS.exe)**

- Release number: 21.6.17
- Release date: October 14, 2025

#### What's new in 21.6.17

| Feature | Details |
| --- | --- |
| Connection dialog | Added the ability to sort the Recent Connections list in the Modern connection dialog. To sort connections, select **Sort By** > **Date Added** or **Name** from the right-click menu. See [Permit sorting of the "Recent connections" box by name](https://developercommunity.visualstudio.com/t/Permit-sorting-of-the-Recent-connection/10971468). |
| Visual Studio | Updated to Visual Studio 17.14.17. |

#### Bug fixes in 21.6.17

| Feature | Details |
| --- | --- |
| Connection dialog | Resolved a bug that generated an error when using the `MUST_CHANGE` property and trying to change the password. See [Instead of Change password dialog an error pops up](https://developercommunity.visualstudio.com/t/Instead-of-Chage-password-dialog-an-erro/10899416). |
| Connection dialog | Fixed an issue that caused the server name to be blank in the Editor Tab name when Custom Name property was left blank. See [New Custom Properties in SSMS 21.5.14 breaks what's on the tab strip](https://developercommunity.visualstudio.com/t/New-Custom-Properties-in-SSMS-21514-br/10962982). |
| Connection dialog | Reinstated the execution timeout default value to 0. See [Execution Timeout Expired](https://developercommunity.visualstudio.com/t/Execution-Timeout-Expired/10963347). **Note**: this change doesn't update the execution timeout value for existing connections. To resolve this issue, delete all previously created connections or manually update the execution timeout to 0. |
| Connection dialog | Resolved an issue where the Modern connection dialog saved passwords when the **Remember Password** option wasn't checked. See [Connection Dialog SSMS 21](https://developercommunity.visualstudio.com/t/Connection-Dialog-SSMS-21/10966681). |
| Connection dialog | Added new icons to differentiate between on-prem/local connections and cloud connections. |
| Dark theme | Resolved a bug that made keywords in the query editor difficult to read for non-English languages. See [SSMS 21 preview dark mode text is not readable](https://developercommunity.visualstudio.com/t/SSMS-21-preview-dark-mode-text-is-not-re/10851866). |
| Managed Instance Link | Updated the setup process for Managed Instance Link to dynamically retrieve and install the current set of Azure-trusted root certificates. |
| Object Explorer | Updated the script generated when selecting **Script Table as** > **CREATE** from the right-click menu to include clustered columnstore indexes. See [Slow and incorrect 'Script Table as CREATE To'](https://developercommunity.visualstudio.com/t/Slow-and-incorrect-Script-Table-as-CREA/10930733). |
| Query Store | Fixed an issue that removed tooltips from Query Store report buttons. See [Query Store Regressed report - buttons missing tooltips](https://developercommunity.visualstudio.com/t/Query-Store-Regressed-report---buttons-m/10868722). |
| Query Store | Resolved a bug that caused resize issues with the Query Store reports window. See [Window Resizing Redraw Issue](https://developercommunity.visualstudio.com/t/Window-Resizing-Redraw-Issue/10917264). |
| SQL Profiler | Resolved an issue that generated an Assembly error when trying to connect to a Power BI Premium workspace. See [SQL Profiler 21.4.8 can't connect to Power BI Premium workspace any longer after update](https://developercommunity.visualstudio.com/t/SQL-Profiler-2148-cant-connect-to-Pow/10939290). |
| View Designer | Fixed an issue that caused the Add Table dialog to open on a different monitor or below other windows, sometimes causing SSMS to become unresponsive. See [SSMS 21 Preview 1: New View window "Add Table" not ware I closed out of New View](https://feedback.azure.com/d365community/idea/8790c2c0-22a8-ef11-95f6-000d3a01397d). |
| View Designer | Fixed an issue that caused the SQL Syntax Error Encountered dialog to open on a different monitor or behind other windows, sometimes causing SSMS to be unresponsive. See [SQL Syntax Errors Encountered Dialog Box](https://developercommunity.visualstudio.com/t/SQL-Syntax-Errors-Encountered-Dialog-Box/10935148). |

<a id="21.5.14"></a>

### 21.5.14

- Release number: 21.5.14
- Release date: September 9, 2025

#### What's new in 21.5.14

| Feature | Details |
| --- | --- |
| Connection dialog | Added an option to give connections a custom Name in the Custom Properties section. See [Add an option to give names to connection in Connection Properties](https://developercommunity.visualstudio.com/t/Add-an-option-to-give-names-to-connectio/10891990). |
| Connection dialog | Updated the Advanced Properties dialog UI to include an Always Encrypted section and added dark theme support. |
| Connection dialog | Introduced connection string copy/paste support. See [The New "Connect" button (Preview) is missing an important feature](https://developercommunity.microsoft.com/t/The-New-Connect-button-Preview-is-mi/10954313). |
| Connection dialog | Added Registered Servers browsing to the Browse tab. See [SSMS 21.1.3: Not possible to connect to registered servers via Connect (Preview) dialog](https://developercommunity.microsoft.com/t/SSMS-2113:-Not-possible-to-connect-to/10914915). |
| Visual Studio | Updated to Visual Studio 17.14.14. |

#### Bug fixes in 21.5.14

| Feature | Details |
| --- | --- |
| Analysis Services | Addressed a regression that generated an error when browsing Online Analytical Processing (OLAP) cubes. See [SSMS 21 Error browsing OLAP cubes](https://developercommunity.microsoft.com/t/SSMS-21-Error-browsing-OLAP-cubes/10915226). |
| Authentication | Fixed a bug that incorrectly populated the subscription list when attempting to restore from an Azure Storage account. See [Subscription List does NOT populate correctly when restoring a SQL DB from a Storage account](https://developercommunity.visualstudio.com/t/Subscription-List-does-NOT-populate-corr/10946164). |
| Central Management Server | Resolved an issue that caused the "New Query" option from the Central Management Server Actions menu to open all registered servers instead of the CMS server itself. See [Central Management Server Actions open all registered servers instead of the server hosting the CMS](https://developercommunity.visualstudio.com/t/Central-Management-Server-Actions-open-a/10936024). |
| Connection dialog | Fixed a bug that removed connections from the Recent connections list when pinning them to the Favorites list. |
| Database properties | Addressed an issue that caused Azure SQL Databases with a maximum size of 1,000 GB (1 TB) to generate the error "DbSize string does not contain a valid numeric integer portion." See [DbSize string does not contain a valid numeric integer portion](https://developercommunity.visualstudio.com/t/DbSize-string-does-not-contain-a-valid-n/10908376). |
| Execution plans | Updated the background color of Execution plans to match other tabs in the results pane. |
| Export bacpac | Addressed an issue that prevented the ability to create bacpac exports for Mirrored Fabric resources. See [Implementing a connection from Azure SQL for Fabric database mirroring breaks the export bacpac function in SSMS](https://developercommunity.visualstudio.com/t/Implementing-a-connection-from-Azure-SQL/10915279). |
| IntelliSense | Fixed a bug that prevented IntelliSense from changing context when using the T-SQL statement `USE`. See [SSMS 21 : IntelliSense think the current database is another one](https://developercommunity.visualstudio.com/t/SSMS-21-:-IntelliSense-think-the-current/10909716). |
| Login properties | Fixed a regression that didn't display credentials underneath Mapped Credentials in the Login Properties window. See [SSMS v21 Preview 1 - Bug in Login Properties for Credentials](https://feedback.azure.com/d365community/idea/e0687671-dca3-ef11-95f6-000d3a059eeb). |
| Object Explorer details | Reinstated the sort indicator when sorting columns in the Object Explorer details view. See [Sort Indicator Missing When Sorting Columns in Object Explorer Details](https://developercommunity.visualstudio.com/t/Sort-Indicator-Missing-When-Sorting-Colu/10925917). |
| Object Explorer details | Fixed a bug that threw an error when trying to generate scripts when multiple objects were selected. See [Generate multiple object script in Object Explorer](https://developercommunity.visualstudio.com/t/Generate-multiple-object-script-in-Objec/10911401). |
| Performance and reliability | Addressed an error that caused SSMS 21 to crash. See [SSMS v21.4 - Configure for General - Environment - Startup crashes](https://developercommunity.visualstudio.com/t/SSMS-v214---Configure-for-General---Env/10948873). |
| Query Store | Fixed a bug that incorrectly displayed Query Store data timestamps in UTC instead of local time when the "Local" option was selected in the Configure Overall Resource Consumption chart. See [Query Store viewer in SSMS 21 is reporting data with incorrect time offset when using local time](https://developercommunity.visualstudio.com/t/Query-Store-viewer-in-SSMS-21-is-reporti/10941754). |
| Results grid | Resolved a regression that included the header when copying values to the clipboard. See [Copy value copies with header](https://developercommunity.visualstudio.com/t/Copy-value-copies-with-header/10914881). |
| Tabify | Reinstated the Tabify/Untabify functionality in the **Edit** > **Advanced** menu. See [Impossible to untabify selection](https://developercommunity.visualstudio.com/t/Impossible-to-untabify-selection/10915182). |

<a id="21.4.12"></a>

### 21.4.12

- Release number: 21.4.12
- Release date: August 12, 2025

#### What's new in 21.4.12

| Feature | Details |
| --- | --- |
| Visual Studio | Updated to Visual Studio 17.14.12. |

<a id="21.4.8"></a>

### 21.4.8

- Release number: 21.4.8
- Release date: July 8, 2025

#### What's new in 21.4.8

| Feature | Details |
| --- | --- |
| Central Management Servers (CMS) | Updated the Central Management Servers registration dialog and removed unnecessary fields. |
| Copilot in SSMS (Preview) | Implemented automatic synchronization to the active query editor for the chat window using the **Sync Active Editor** option. |
| Files | Updated the default location for File Save to `%USERPROFILE%\Documents\SQL Server Management Studio 21`. See [File Open and File Save are using a different location to SSMS 20](https://developercommunity.visualstudio.com/t/File-Open-and-File-Save-are-using-as-dif/10856099). |
| IntelliSense | Added support for Query Store secondary replicas syntax `FOR SECONDARY SET` and `OPERATION_MODE`. |
| Query Data Store (QDS) | Added seconds and milliseconds to the data picker for Overall Resource Consumption: [SSMS - Query Store graphs configure options adding seconds and milliseconds to defined time interval](https://developercommunity.visualstudio.com/t/SSMS---Query-Store-graphs-configure-opti/10877985). |
| Visual Studio | Updated to Visual Studio 17.14.8. |

#### Bug fixes in 21.4.8

| Feature | Details |
| --- | --- |
| Always Encrypted | Fixed several issues including an issue in the Create a New Column Master Key wizard where **Sort by Create Date** was incorrectly sorting by String, an issue that prevented Always Encrypted set up to be completed [when using SSMS with Russian localization](https://developercommunity.visualstudio.com/t/Can-not-set-up-Always-Encrypted-with-Azu/10856776), and an issue in the Create a New Column Master Key wizard that improperly sized the subscription and tenant dropdown lists. |
| Central Management Servers (CMS) | Addressed a bug that didn't add the server connection information to the recently used connections in the Connection Dialog. |
| Copilot in SSMS (Preview) | Improved initial chat experience if Microsoft Entra authentication to Azure OpenAI doesn't occur. |
| Copilot in SSMS (Preview) | Fixed issue where the current context entry wasn't updating if a tab was renamed. |
| Connection Dialog | Fixed a bug that caused the Modern connection dialog (Preview) to clear its recent and pinned connections when multiple instances of SSMS were open. See [Connections dialog forgets connections](https://developercommunity.visualstudio.com/t/Connections-Dialog-forgets-connections/10908219). |
| Migration Assistant | Fixed an error in the Migration Assistant Assessment Wizard that caused UI elements to incorrectly display when the display resolution was set to 250%. |
| Query Data Store (QDS) | Addressed an issue where **Overall Resource Consumption** was incorrectly aggregating data when the display time was set to **Local**. See [QDS - Overall Resource Consumption graphs return incorrect information when choosing "Time format: Local" with aggregation per day](https://developercommunity.visualstudio.com/t/QDS---Overall-Resource-Consumption-graph/10873252). |
| Results Window | Addressed an issue where scrolling multiple datasets in the results grid didn't behave as expected. See [SSMS 21.0 - scrolling issue in results window](https://developercommunity.visualstudio.com/t/SSMS-210---scrolling-issue-in-results-w/10859401). |
| Scripting | Resolved the error `given key was not present in the dictionary` when running queries or scripting a table as select. See [SSMS 21 Preview .NET Framework error - the given key was not present in the dictionary](https://developercommunity.visualstudio.com/t/SSMS-21-Preview-NET-Framework-error---t/10896557). |
| View Designer | Fixed an issue that generated an error message when using `CONVERT` or `CAST` with several data types. See [SSMS returns error on valid query in view designer](https://developercommunity.visualstudio.com/t/SSMS-returns-error-on-valid-query-in-vie/10897549). |

<a id="21.3.7"></a>

### 21.3.7

- Release number: 21.3.7
- Release date: June 23, 2025

#### What's new in 21.3.7

| Feature | Details |
| --- | --- |
| Visual Studio | Updated to Visual Studio 17.14.7 |

#### Bug fixes in 21.3.7

| Feature | Details |
| --- | --- |
| SQL Server Integration Services (SSIS) | Resolved a bug that caused SQL Services Integration Services Projects 2022 to break when SSMS with SQL Server Integration Services (SSIS) was installed on the same machine. |

<a id="21.3.6"></a>

### 21.3.6

- Release number: 21.3.6
- Release date: June 17, 2025

#### What's new in 21.3.6

| Feature | Details |
| --- | --- |
| Query Editor | Added the ability to rename unsaved query editor tabs via the **Rename tab** option on the query tab context menu |
| Visual Studio | Updated to Visual Studio 17.14.6 |

#### Bug fixes in 21.3.6

| Feature | Details |
| --- | --- |
| Connection dialog | Fixed various Modern connection dialog (Preview) bugs, including [New Connection Dialog is leaking connections in SSMS 21](https://developercommunity.microsoft.com/t/New-Connection-Dialog-is-leaking-connect/10900958), [New connection dialog - Cancel should not close but allow changing to a different connection](https://developercommunity.microsoft.com/t/New-connection-dialog---Cancel-should-no/10900209), and [Importing earlier version of SSMS from SSMS 21](https://developercommunity.visualstudio.com/t/Importing-earlier-version-of-SSMS-from-S/10910984). |
| Copilot in SSMS (Preview) | Addressed an issue that erroneously caused an Azure OpenAI jailbreak response, causing the Copilot to try less effective alternatives to assess the database schema and return a valid query. |
| Files | Fixed a bug that caused multiple instances of SSMS to open when opening `.sql` files. See [SSMS: SQL files opening new instances of SSMS](https://developercommunity.visualstudio.com/t/SSMS:-SQL-files-opening-new-instances-of/10858946). |
| Git | Addressed an error that incorrectly colored text in the diff tool and prevented the code selection from being copied. See [SSMS 21 Preview 7 Git Changes, Diff coloring](https://developercommunity.visualstudio.com/t/SSMS-21-Preview-7-Git-Changes-Diff-colo/10898088) and [SSMS 21 diff tool does not allow copy of code selection unlike Visual Studio](https://developercommunity.visualstudio.com/t/SSMS-21-Diff-tool-left-side-does-not-all/10898618). |
| Object Explorer | Resolved Object Explorer performance regression by removing the "use current theme for selected node" setting, and fixed a bug that incorrectly displays database names that contain `&`. See [Performance regression: Object Explorer takes ~60 s to expand table nodes in large databases](https://developercommunity.visualstudio.com/t/Performance-regression:-Object-Explorer-/10913775) and [Object Explorer showing wrong database name](https://developercommunity.visualstudio.com/t/Object-Explorer-showing-wrong-database-n/10919352). |
| SQL Server Analysis Services (SSAS) | Fixed a bug that led to a crash when editing connection properties and credentials with a SAS key. |
| SQL Server Integration Services (SSIS) | Resolved errors that were generated when a data source other than Microsoft OLEDB Provider for SQL Server was selected in the Import and Export Wizard, and added support for the [Execute package utility (dtexecui)](/sql/integration-services/packages/execute-package-utility-dtexecui-ui-reference). |

<a id="21.2.5"></a>

### 21.2.5

- Release number: 21.2.5
- Release date: June 10, 2025

#### What's new in 21.2.5

| Feature | Details |
| --- | --- |
| Connection dialog | Added a Browse tab to the Modern connection dialog (Preview) that allows browsing your local, network, or Azure resources. |
| Maintenance plans | Reinstated maintenance plan capabilities, including creating and updating maintenance plans using the Maintenance Plan Wizard. |
| SQL Server Integration Services (SSIS) (Preview) | Reinstated SQL Server Integration Services (SSIS) capabilities (in preview), including SSISDB catalog management, automated execution of SSIS packages, and the Import Export Wizard. |
| Visual Studio | Updated to Visual Studio 17.14.5 |

#### Bug fixes in 21.2.5

| Feature | Details |
| --- | --- |
| Connection dialog | Fixed a bug that prevented creating new firewall rules for Azure resources from SSMS. See [Modern Connection dialog cannot add firewall exceptions](https://developercommunity.microsoft.com/t/Modern-Connection-dialog-cannot-add-fire/10899761). |
| Reliability | Addressed scenario related to Copilot in SSMS (Preview) that could lead to SSMS crashing. |
| Reliability | Fixed error 'Parameter is not valid' that also caused the active dialog to become with red lines. This error occurred in the results grid, database diagrams, and SQL Profiler. See [Unhandled Exception in SSMS 21 - "Parameter is not valid"](https://developercommunity.visualstudio.com/t/Unhandled-Exception-in-ssms-21---Parame/10897441) and [SQL Server Profiler Unhandled exception after switching theme in SSMS](https://developercommunity.visualstudio.com/t/SQL-Server-Profiler-Unhandeled-exception/10911208). |

<a id="21.1.3"></a>

### 21.1.3

- Release number: 21.1.3
- Release date: May 28, 2025

#### What's new in 21.1.3

| Feature | Details |
| --- | --- |
| Visual Studio | Updated to Visual Studio 17.14.3. |

#### Bug fixes in 21.1.3

| Feature | Details |
| --- | --- |
| Extended Events | Fixed a bug where the context menu for Extended Events while Dark theme was enabled didn't have enough contrast to be readable. See [Filter context menu ExtEvents not readable](https://developercommunity.visualstudio.com/t/Filter-context-menu-ExtEvents-not-readab/10900655). |
| Localization | Addressed an issue where reports weren't honoring the selected language in **Tools** > **Options** > **International Settings**. See [Wrong language located in elements in SSMS 21 and Profiler 21](https://developercommunity.visualstudio.com/t/Wrong-language-located-elements-in-SSMS-/10898516). |
| Object Explorer Details | Fixed an issue where adding columns to the Object Explorer details pane generated an error. See [Invalid object reference in Object Explorer Details pane](https://developercommunity.visualstudio.com/t/Invalid-object-reference-in-Object-Explo/10898449). |

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
| Connection Dialog | Introduced a Modern connection dialog experience for SQL Server database engines. You can enable or disable this experience within **Tools** > **Options** > **Environment** > **Connection Dialog**. |
| Connection Dialog | Added dark mode support for Modern connection dialog (Preview). See [New connection dialog does not support dark mode](https://developercommunity.microsoft.com/t/New-connection-dialog-does-not-support-d/10893407?q=%22dark%22). |
| Copilot in SSMS (Preview) | Added [Copilot in SQL Server Management Studio (Preview)](copilot/copilot-in-ssms-overview.md) available from the AI Assistance workload in the Visual Studio Installer. |
| Database Properties | Added a page to list Database Scoped Configuration values on the **Database Properties** dialog. |
| Database Properties | Added support for [!INCLUDE [sssql25-md](includes/sssql25-md.md)] FULLTEXT_INDEX_VERSION configuration options in the database properties dialog. |
| Drivers | Updated Microsoft.Data.SqlClient (MDS) to version 5.1.6. |
| File | Reinstated the ability to create projects (**File** > **New** > **Project or Solution...**) and view recent projects (**File** > **Open** > **Project/Solution...**). |
| Find | Reinstated the **Quick Find** option, accessed through **Edit** > **Find and Replace** > **Quick Find**, or with **Ctrl**+**F**. See [SSMS 21.0 Preview 1.0 - "Quick Find" missing, instead "Find in files" pops up](https://feedback.azure.com/d365community/idea/76326fd1-57b6-ef11-95f6-000d3ae2b698). |
| Git | Support for Git integration returns in SSMS 21 to support the growing emphasis on CI/CD, which can be found in the **Git** menu. Select **Settings** to configure options specific to Git. The Git integration allows developers and database administrators to track, manage, and collaborate on SQL scripts seamlessly within the SSMS environment, including support for creating and cloning repositories and creating and managing branches. |
| Help | Enabled support for Developer Community feedback, accessed from **Help** > **Send Feedback** > **Report a Problem/Suggest a Feature/My Feedback**. |
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
| Migration Component | Added the [SQL Server migration component](migrate-sql-server-component.md) under **Individual Components** > **Hybrid and Migration** in the Visual Studio Installer. |
| Presenter Mode | Reinstated [Presenter mode](presenter-mode.md) as an option under **View** > **Presenter Mode**. |
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
| Options | Removed localization of `ISOLATION LEVEL` option within **Tools** > **Options** > **Query Execution** > **SQL Server** > **Advanced**. |
| Query Plans | Addressed an issue where canceling a query while running a live query plan caused SSMS to crash. See [Live query statistics hangs waiting for plan and canceling query kills SSMS](https://feedback.azure.com/d365community/idea/9e4420f1-afac-ee11-92bc-000d3ae54955). |
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
