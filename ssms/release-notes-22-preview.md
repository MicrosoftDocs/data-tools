---
title: "Release Notes for SQL Server Management Studio (SSMS) 22 Preview"
description: Release notes for SQL Server Management Studio (SSMS) 22 Preview.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, mbarickman
ms.date: 10/29/2025
ms.service: sql-server-management-studio
ms.topic: whats-new
ms.collection:
  - data-tools
---

# Release notes for SQL Server Management Studio (SSMS) 22 Preview

[!INCLUDE [sql-asdb-asdbmi-asa](includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

This article details updates, improvements, and bug fixes for the preview version of [!INCLUDE [ssms-22-md](includes/ssms-22-md.md)].

[!INCLUDE [ssms-connect-aazure-ad](includes/ssms-connect-azure-ad.md)]

## Latest SQL Server Management Studio Preview release

**[Download SQL Server Management Studio (SSMS) 22 Preview](https://aka.ms/ssms/22/preview/vs_SSMS.exe)**

## Latest GA SQL Server Management Studio release

[!INCLUDE [ssms-21-md](includes/ssms-21-md.md)] is the latest general availability (GA) release of SSMS.

**[Download SQL Server Management Studio (SSMS) 21](https://aka.ms/ssms/21/release/vs_SSMS.exe)**

For previous versions of SSMS, see:

- [Release notes for SQL Server Management Studio (SSMS) 21](release-notes-21.md)
- [Release notes for SQL Server Management Studio (SSMS) 20](release-notes-20.md)
- [Release notes for SQL Server Management Studio (SSMS) 19 and earlier versions](release-notes-19.md)

<a id="22.0.0-pre.4.0"></a>

### 22.0 Preview 4

**[Download SQL Server Management Studio (SSMS) 22 Preview](https://aka.ms/ssms/22/preview/vs_SSMS.exe)**

- Release number: 22.0 Preview 4
- Release date: October 27, 2025

#### What's new in 22.0 Preview 4

| Feature | Details |
| --- | --- |
| Connection Dialog | Added a **Reset** button to clear the fields in the **Connection Properties** section. |
| GitHub Copilot in SSMS (Preview) | Introduced support for the SSMS responder when using **Ask Copilot** within **Feature Search**. |
| Indexes | Added options to create Vector and JSON indexes. Right-click **Indexes > New Index > JSON Index...** or **Vector Index...** |
| Linked Server Wizard | Introduced a streamlined creation wizard for linked servers, including new encryption model options. |
| Object Explorer | Introduced display information for dimension and base type parameters for **vector** data types in Object Explorer. |
| Query Plans | Added support for JSON and Vector index operations. |
| Snippets | Added numerous new snippet files, including snippets for creating various index types, creating and altering external models for AI embeddings, and managing security and schema objects. |
| Visual Studio | Updated to Visual Studio 18.0.0 Insiders [11123.170]. |

#### Bug fixes in 22.0 Preview 4

| Feature | Description |
| --- | --- |
| Activity Monitor | Resolved various context menu issues for **Recent Expensive Queries** and **Active Expensive Queries**. See [Activity Monitor Failed to retrieve Execution Plan data](https://developercommunity.visualstudio.com/t/Activity-Monitor-Failed-to-retrieve-Exec/10983180). |
| Authentication | Introduced a new menu option in **Help > Clear Entra ID Token Cache** to fix an issue that prevented users were recently added to an Entra ID group from being able to login. See [Unable to login when recently been added to an EntraID group](https://developercommunity.microsoft.com/t/Unable-to-login-when-recently-been-added/10946664). |
| Available Databases | Resolved an issue that generated the error `Parse error at line: 1, column: 5: Incorrect syntax near 'NOEXEC'.` when switching between a SQL database and a Data Warehouse on the same server. See [Issue switching between DW and SQL database in SSMS21](https://developercommunity.visualstudio.com/t/-Issue-switching-between-DW-and-SQL-data/10972386). |
| Connection Dialog | Fixed an issue where the **Application Name** field in **Advanced Properties** was not being inherited. See [New Query from Object Explorer Does Not Inherit App Name from Highlighted Database](https://developercommunity.visualstudio.com/t/New-Query-from-Object-Explorer-Does-Not-/10977858). |
| Generate Scripts Wizard | Resolved an `Object reference not set to an instance of an object` error thrown when trying to select options on the **Set Scripting Option** menu. See [Advance option on generate script button click throwing error in SSMS 2022 Preview 3](https://developercommunity.visualstudio.com/t/Advance-option-on-generate-script-button/10984224). |
| GitHub Copilot in SSMS (Preview) | Fixed an issue with an empty chat window that hangs. See [SSMS 22 Preview hangs at Modern Connection Dialog after installing GitHub Copilot](https://developercommunity.visualstudio.com/t/SSMS-22-Preview-hangs-at-Modern-Connecti/10984949). | 
| Query Editor | Resolved a behavior that prevented scrolling of the query editor pane when the results pane was in focus. See [Query window pane does not mouse wheel scroll up if results window pane is selected](https://developercommunity.visualstudio.com/t/Query-window-pane-does-not-mouse-wheel-s/10851382). |
| Status Bar | Fixed an issue that caused color contrast issues when certain colors were selected. See [Query Summary Row, Text Illegible, Accessibility Issue](https://developercommunity.visualstudio.com/t/Query-Summary-Row-Text-Illegible-Acces/10958981). |

<a id="22.0.0-pre.3.0"></a>

### 22.0 Preview 3

- Release number: 22.0 Preview 3
- Release date: October 14, 2025

#### What's new in 22.0 Preview 3

| Feature | Details |
| --- | --- |
| Arm64 Support | Added initial Windows Arm64 support for core SSMS 22 Preview scenarios, including connecting and querying. See **Known Issues** for a list of scenarios that are still unsupported. |
| Edit Data | Added support for Vector data type to Edit Data. |
| Execution Plans | Added the ability to open an execution plan in a new tab. When viewing an Execution Plan, right-click to bring up the menu and select **Show Execution Plan in New Tab.** See [SSMS Right Click To Open Execution Plans In A New Tab](https://feedback.azure.com/d365community/idea/8c1f1930-35cc-ee11-92bc-6045bd83e1af). |
| IntelliSense | Added IntelliSense support for `VECTOR_SEARCH`, `CREATE VECTOR INDEX`, `AUTOSEEDING_SYSTEM_DATABASES`, `REUSE_SYSTEM_DATABASES`, AND `CREATE JSON INDEX`. |
| JSON Viewer | Added the ability to view JSON data from the results grid. See [JSON column view like in Azure Data Studio](https://developercommunity.microsoft.com/t/JSON-column-view-like-in-azure-data-stud/10881763). |
| GitHub Copilot in SSMS (Preview) | Added [GitHub Copilot in SQL Server Management Studio](github-copilot/get-started.md), available from the **AI Assistance** workload in the Visual Studio Installer. |
| Query Hint Recommendation Tool (Preview) | Added the [Query Hint Recommendation Tool (Preview)](query-hint-tool/hint-tool-overview.md) component under **Individual Components > Code Tools** in the Visual Studio Installer. |
| Scripting | Added scripting support for tables with Vector columns. |
| SQL Server Integration Services (SSIS) | Reinstated SQL Server Integration Services (SSIS) capabilities, including SSISDB catalog management, automated execution of SSIS packages, and the Import Export Wizard. |
| Table Designer | Added support for Vector data type to Table Designer. |
| Theming | Expanded dark theme support to include the Connect to Azure Storage dialog, and the Registered Servers Export, Import, and Move Registered Server dialogs. |
| Visual Studio | Updated to Visual Studio 18.0.0 Insiders [11111.16]. |

#### Bug fixes in 22.0 Preview 3

| Feature | Description |
| --- | --- |
| Database Properties | Fixed an issue that blocked the ability to change compatibility level for users with ALTER permissions. See [Database compatibility level drop down disabled but query works](https://developercommunity.visualstudio.com/t/Database-compatibility-level--drop-down-/10927466). |
| Object Explorer | Resolved an error that was generated when dragging table objects from the Object Explorer to the Query Editor. |
| Object Explorer | Resolved an issue that prevented direct scroll bar navigation from working properly. See [Direct scroll bar navigation via Shift-click does not work for Object Explorer and Results Grid](https://developercommunity.visualstudio.com/t/DirectscrollbarnavigationviaShift-clickdoesnotworkforObjectExplorerandResultsgrid/10936054). |
| PowerShell | Fixed a bug that generated an error when attempting to start PowerShell from the Object Explorer context menu. |
| Query Editor | Resolved an issue where the "Include column headers" option wasn't properly applied in new query windows. See [Copying query results does not include headers, even when the "Include column headers" option is enabled](https://developercommunity.visualstudio.com/t/Copying-query-results-does-not-include-h/10969136). |
| Reports | Addressed a bug that caused an arithmetic overflow error in the Object Execution Statistics and Batch Execution Statistics reports when execution_count exceeded the **int** data type limit. |
| Results Grid | Resolved an issue that prevented direct scroll bar navigation from working properly. See [Direct scroll bar navigation via Shift-click does not work for Object Explorer and Results Grid](https://developercommunity.visualstudio.com/t/DirectscrollbarnavigationviaShift-clickdoesnotworkforObjectExplorerandResultsgrid/10936054). |
| Solution Explorer | Resolved an error that was generated when opening a folder that was closed but had files that were open. See [SSMS 21 Preview - error while opening a folder in Windows 11](https://developercommunity.visualstudio.com/t/SSMS-21-Preview---error-while-opening-a-/10855845). |
| Status Bar | Reinstated line and column numbers in the status bar. See [In SSMS21 I can't find column number after clicking cell in grid results](https://developercommunity.visualstudio.com/t/In-SSMS21-I-cant-find-column-number-aft/10928369). |
| T-SQL Language Settings | Fixed a bug that caused some T-SQL language settings to persist between SSMS sessions. |

<a id="22.0.0-pre.2.0"></a>

### 22.0 Preview 2

- Release number: 22.0 Preview 2
- Release date: September 23, 2025

#### What's new in 22.0 Preview 2

| Feature | Details |
| --- | --- |
| Visual Studio | Updated to Visual Studio 18.0.0 Insiders [11018.127]. |

<a id="22.0.0-pre.1.1"></a>

### 22.0 Preview 1.1

- Release number: 22.0 Preview 1.1
- Release date: September 16, 2025

#### What's new in 22.0 Preview 1.1

| Feature | Details |
| --- | --- |
| Connection dialog | Added Fabric browsing to the Browse tab. |
| Visual Studio | Updated to Visual Studio 18.0.0 Insiders [11012.119]. |

<a id="22.0.0-pre.1.0"></a>

### 22.0 Preview 1

- Release number: 22.0 Preview 1
- Release date: September 9, 2025

For more new features and bug fixes that are available in SSMS 22 Preview 1, see [SSMS 21.5 release notes](release-notes-21.md#21514).

#### What's new in 22.0 Preview 1

| Feature | Details |
| --- | --- |
| Always Encrypted | Added support for sovereign cloud solutions Bleu and Delos. |
| Connection Dialog | The modern dialog is the default connection dialog. |
| Database Tuning Advisor (DTA) | Improved DTA functionality including better tuning coverage to queries with temp tables, table variables, triggers, improved index tuning quality, and general scalability and concurrency. |
| IntelliSense | Added support for CURRENT_TIMEZONE_ID syntax, see [SSMS 21 does not recognize CURRENT_TIMEZONE_ID function](https://developercommunity.microsoft.com/t/SSMS-21-does-not-recognize-CURRENT_TIMEZ/10879862). |
| IntelliSense | Added support for ANSI concatenation using the `||=` operator. |
| IntelliSense | Added support for `AI_GENERATE_EMBEDDINGS` syntax. |
| IntelliSense | Added support for regular expression functions `REGEXP_MATCHES` and `REGEXP_SPLIT_TO_TABLE`. |
| Libraries | Updated Server Management Objects (SMO) to version 17.100.73. |
| Libraries | Updated DacFx to version 170.0.97. |
| Managed Instance Link | Updated the authentication control to align with the one used elsewhere in SSMS. |
| Query Editor | Added information section to the Rename Tabs dialog to provide information about said functionality. |
| Query Store | Improved Find Query and Run Query buttons in the Tracked Queries report. |
| Results Grid | Introduced Zoom support for grid results, see [Zoom the results area independently](https://developercommunity.visualstudio.com/t/Zoom-the-results-area-independently/10860281). |
| Startup commands | Removed `-G` and `-E` options (replaced by `-A)`. |
| Themes | Introduced new themes and removed the Blue (SSMS) theme. |
| Visual Studio | Updated to Visual Studio 18.0.0 Insiders. |

#### Bug fixes in 22.0 Preview 1

| Feature | Description |
| --- | --- |
| Analysis Services | Resolved error `Object reference not set to an instance of an object. (Microsoft.VisualStudio.Design)` when browsing OLAP cubes. See [SSMS 21 Error browsing OLAP cubes](https://developercommunity.visualstudio.com/t/SSMS-21-Error-browsing-OLAP-cubes/10915226). |
| Analysis Services | Resolved error `Could not load file or assembly 'Microsoft.Data.ConnectionUI.Dialog, Version=17.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a' or one of its dependencies. The system cannot find the file specified.` See [Browse MDM models generates an error](https://developercommunity.visualstudio.com/t/Browse-MDM-models-generates-an-error/10920140). |
| Database Properties | Fixed validation for `MAXDOP` and `LEDGER_DIGEST_STORAGE_ENDPOINT` in Database Scoped Configurations tab. |
| Find/Replace | Restored ability to use **Ctrl**+**C** in the Find/Replace dialog after opening a saved `.sql` file. See [Copy (Ctrl+C) does not work in Find/Replace dialog](https://developercommunity.visualstudio.com/t/Copy-CtrlC-does-not-work-in-FindRepl/10909707). |
| General UI | Resolved behavior for selected dialogs that would appear behind the main windows when opened. |
| General UI | Fixed issue that generated the error `Unsaved documents cannot be cut or copied to the clipboard from the Miscellaneous Files project. You must save the unsaved document(s) before cutting or copying them.` when using **Ctrl**+**C** in the Quick Find dialog (Ctrl+F). |
| Query Store | Addressed incorrect sizing with Configure Regressed Queries dialog. See ["Configure regressed queries" dialog goes off the screen vertically on 1920x1080 monitor](https://developercommunity.visualstudio.com/t/Confgure-regressed-queries-dialog-goes/10929863). |

## Known issues

For more information, see [Known issues in SQL Server Management Studio 22 Preview](known-issues-preview.md).

[!INCLUDE [support](includes/support.md)]

## Related content

- [Install SQL Server Management Studio](install/install.md)
- [SQL Server Management Studio 21 FAQ](faq.yml)
- [Visual Studio 2022 release notes](/visualstudio/releases/2022/release-notes)
