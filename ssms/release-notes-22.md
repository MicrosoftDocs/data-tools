---
title: "Release Notes for SQL Server Management Studio (SSMS)"
description: Release notes for SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, mbarickman
ms.date: 02/10/2026
ms.service: sql-server-management-studio
ms.topic: whats-new
ms.collection:
  - data-tools
---

# Release notes for SQL Server Management Studio (SSMS)

[!INCLUDE [sql-asdb-asdbmi-asa](includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

This article details updates, improvements, and bug fixes for the current version of [!INCLUDE [ssms-22-md](includes/ssms-22-md.md)].

[!INCLUDE [ssms-connect-aazure-ad](includes/ssms-connect-azure-ad.md)]

## Current SQL Server Management Studio release

**[Download SQL Server Management Studio (SSMS) 22](https://aka.ms/ssms/22/release/vs_SSMS.exe)**

[!INCLUDE [ssms-22-md](includes/ssms-22-md.md)] is the latest general availability (GA) release of SSMS.

For previous versions of SSMS, see:

- [Release notes for SQL Server Management Studio (SSMS) 21](release-notes-21.md)
- [Release notes for SQL Server Management Studio (SSMS) 20](release-notes-20.md)
- [Release notes for SQL Server Management Studio (SSMS) 19 and earlier versions](release-notes-19.md)

<a id="22.3"></a>

### 22.3

**[Download SQL Server Management Studio (SSMS) 22](https://aka.ms/ssms/22/release/vs_SSMS.exe)**

- Release number: 22.3
- Release date: February 10, 2026

#### What's new in 22.3

| Feature | Details |
| --- | --- |
| Connection dialog | Improved startup performance of the modern connection dialog. |
| External Models | Added template support for external models. |
| GitHub Copilot in SSMS (Preview) | Introduced support for database instructions. See [Use database instructions with GitHub Copilot in SQL Server Management Studio (Preview)](github-copilot/database-instructions.md). |
| Libraries | Updated Microsoft.Data.SqlClient to 6.1.3. |
| Libraries | Updated MSODBCSQL to 18.6.1.1. |
| Visual Studio | Updated to Visual Studio 18.3 [11506.43]. |

#### Bug fixes in 22.3

| Feature | Description |
| --- | --- |
| Analysis Services | Addressed error `Could not load file or assembly 'Microsoft.VisualStudio.Data.Framework, Version=18.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a' or one of its dependencies. The system cannot find the file specified.` when trying to change the connection string for an Analysis Services database. See [Can't change "Connection String" for Analysis Services Database](https://developercommunity.visualstudio.com/t/Cant-change-Connection-String-for-Ana/11000063). |
| Analysis Services | Fixed error `Object reference not set to an instance of an object` when trying to browse a multi-dimensional cube. |
| Arm64 | Added support for Profiler and Database Tuning Advisor (DTA) on Arm64 devices. See [SQL Server Profiler 22 does not open on ARM](https://developercommunity.visualstudio.com/t/SQL-Server-Profiler-22-does-not-open-on-/11006644). Both Profiler and DTA run as 32-bit applications. |
| Azure Authentication | Fixed an issue where errors could occur when signing into an account or selecting placeholder values in dialogs using Azure authentication. |
| Connection dialog | Updated the modern connection dialog to ensure advanced properties are carried to subsequent connections, for example, when opening a query editor from an existing connection in Object Explorer. |
| Dataverse | Resolved issue where expanding the list of columns for a table was blank for a Dynamics Dataverse database. See [When connected to Dynamics dataverse in SSMS 22, expanding the list of columns in a table shows nothing](https://developercommunity.visualstudio.com/t/When-connected-to-Dynamics-dataverse-in-/11012102). |
| GitHub Copilot | Reduced frequency of schema cache updates to optimize performance for code completions. |
| Maintenance Plans | Added ability to create maintenance plans in SQL Server 2025 with Strict Encryption enforced for the instance. |
| Query Editor | Fixed an issue where the editor would show an error notification when no error exists. See [1 Error, Click to navigate to the error list](https://developercommunity.visualstudio.com/t/1-Error-Click-to-navigate-to-the-error-/10855667). |
| Query Editor | Updated the behavior of the Query Editor to not prompt to save a file when closing if the contents were changed and then reverted. See ["Query Execution -> SQL Server -> General -> Prompt to save unsaved T-SQL query windows on close" Edge Case](https://developercommunity.visualstudio.com/t/Query-Execution---SQL-Server---Genera/10958824). |
| Query Store Reports | Addressed a scenario where Query Store data appeared under the incorrect time range. See [Query Store viewer in SSMS 21 is reporting data with incorrect time offset when using local time](https://developercommunity.visualstudio.com/t/Query-Store-viewer-in-SSMS-21-is-reporti/10941754). |
| Query Store Reports | Fixed an issue where query text is truncated in the execution plan for a query. See [In the SSMS 22 query store, the query display is cut off](https://developercommunity.visualstudio.com/t/In-the-SSMS-22-query-store-the-query-di/11002498). |
| Replication | Clarified the **Interval** option for the Publication Properties dialog. See [SSMS 21.3.7 - Replication Publication Properties - incorrect and misleading labels](https://developercommunity.visualstudio.com/t/SSMS-2137---Replication-Publication-Pr/10928637). |
| Results Grid | Fixed issue where large JSON text was split across multiple rows in the results grid. See [SSMS 22 Preview - Large JSON Output Split Across Multiple Rows](https://developercommunity.visualstudio.com/t/SSMS-22-Preview-%E2%80%93-Large-JSON-Output-Spli/10991392) and [The viewer's results table using "JSON PATH" sometimes does not show a row with valid JSON; instead, it shows several rows with truncated data](https://developercommunity.visualstudio.com/t/The-viewers-results-table-using-JSON-P/11000557). |
| Results Pane | Restored ability to use <kbd>Ctrl</kbd>+<kbd>R</kbd> to hide or restore the results pane when viewing an execution plan. See [SSMS 22: CTRL+R Shortcut Doesn't Work From Execution Plan Tab](https://developercommunity.visualstudio.com/t/SSMS-22:-CTRLR-Shortcut-Doesnt-Work-Fr/11007268). |
| Spatial results | Resolved error `One of the identified items was an invalid format` when viewing spatial results. See [Spatial results tab returns invalid format error when viewing features that pass .isValidDetailed() test](https://developercommunity.visualstudio.com/t/Spatial-results-tab-returns-invalid-form/10848203). |

<a id="22.2.1"></a>

### 22.2.1

- Release number: 22.2.1
- Release date: January 21, 2026

#### What's new in 22.2.1

| Feature | Details |
| --- | --- |
| GitHub Copilot in SSMS (Preview) | Introduced support for code completions and next edit suggestions (NES) in the query editor. |
| Libraries | Updated Server Management Objects (SMO) to version 17.100.91. |
| Visual Studio | Updated to Visual Studio 18.2 [11415.280]. |

#### Bug fixes in 22.2.1

| Feature | Description |
| --- | --- |
| Activity Monitor | Fixed an issue where query text wasn't available in Activity Monitor. See [Session details missing query information in Activity monitor, SSMS 22.0.0 Preview 3.0](https://developercommunity.visualstudio.com/t/Session-details-missing-query-informatio/10992835). |
| Database Diagrams | Addressed a crash in the database designer that occurs when a relationship is selected. |
| Database Diagrams | Resolved inability to edit database diagrams that were created in an earlier version of SSMS. See [Database Diagram cannot be modified](https://developercommunity.visualstudio.com/t/Database-Diagram-cannot-be-modified/10894990). |
| Migration Assistant | Addressed an issue where selecting **Previous** from the Summary window navigates to the incorrect page when both **Compatibility issues** and **SQL Server feature parity** are selected. See [SQL Server 2022 UI Issue while doing sql assessment from 2008 to 2025](https://developercommunity.visualstudio.com/t/SQL-Server-2022-UI-Issue--while-doing-sq/11014004). |
| Object Explorer | Fixed error generated when scripting a CREATE OR ALTER for a view in SQL On Demand provided via Synapse Analytics. See [Generate Scripttext for CREATE OR ALTER view produces error](https://developercommunity.visualstudio.com/t/Generate-Scripttext-for-CREATE-OR-ALTER-/11004800). |
| Object Explorer Details | Fixed error "Arithmetic operation resulted in an overflow" when navigating within Object Explorer Details with a specific three monitor configuration. See [Error editing table in object explorer details](https://developercommunity.visualstudio.com/t/Error-editing-table-in-object-explorer-d/10939472). |
| Toolbar | Addressed behavior where customizing the width of the Available Database dropdown list wasn't respected. See [SSMS.22.Preview : Toolbar->SQLEditor->AvailableDatabase customization](https://developercommunity.visualstudio.com/t/SSMS22Preview-:-Toolbar-SQLEditor-Av/10987121). |

<a id="22.1.0"></a>

### 22.1.0

- Release number: 22.1.0
- Release date: December 9, 2025

#### What's new in 22.1.0

| Feature | Details |
| --- | --- |
| GitHub Copilot in SSMS (Preview) | Introduced the GitHub Copilot Walkthrough, available from the Copilot badge. |
| GitHub Copilot in SSMS (Preview) | Added right-click menu support for Document, Explain, Fix, and Optimize code assistance. |
| GitHub Copilot in SSMS (Preview) | Improved response time after submitting the first prompt for a thread. |
| GitHub Copilot in SSMS (Preview) | Introduced Bring your own model (BYOM). |
| GitHub Copilot in SSMS (Preview) | Updated the default model to be Claude 4.5 for paid subscriptions. |
| Visual Studio | Updated to Visual Studio 18.1 [11304.174]. |

#### Bug fixes in 22.1.0

| Feature | Description |
| --- | --- |
| Accessibility | Fixed an issue in Profiler to restore keyboard focus to the proper element when Profiler window is reactivated. |
| Always Encrypted | Fixed a bug on the **New Column Master Key** page of the Always Encrypted Wizard that displayed the wrong name in the key vault dropdown list. See [New Column Master Key Dialog doesn't show AKV names](https://developercommunity.visualstudio.com/t/New-Column-Master-Key-Dialog-doesnt-sho/10990450). |
| Edit data | Resolved a crash that occurred when editing data for a table with a hierarchyid data type. See [Crash when data-editing Table with a hierarchyid column containing brackets ( ) in the name](https://developercommunity.visualstudio.com/t/Crash-when-data-editing-Table-with-a-hie/10978934). |
| GitHub Copilot in SSMS (Preview) | Reintroduced the `/optimize` code assistance command. |
| GitHub Copilot in SSMS (Preview) | Fixed the issue where Copilot displayed `Run ValidateGeneratedTQL` repeatedly and didn't answer, or answered incorrectly. See [SSMS v22 Copilot taking minutes to respond, generating inaccurate results](https://developercommunity.visualstudio.com/t/SSMS-v22-Copilot-taking-minutes-to-respo/11006503). |
| GitHub Copilot in SSMS (Preview) | Fixed the error `An exception was encountered while constructing the content of this frame`. See [Copilot Chat not working. Exception thrown.](https://developercommunity.visualstudio.com/t/Copilot-Chat-not-working-Exception-thro/11007777). |
| GitHub Copilot in SSMS (Preview) | Updated the query to identify blocking to account for sleeping sessions. |
| Profiler | Removed CTP from the SQL Server 2025 entry in the **Trace provider type**. |
| Query Hint Recommendation Tool (Preview) | Addressed an issue that inserted a query hint after an existing semicolon instead of before it. |

<a id="22.0.0"></a>

### 22.0.0

- Release number: 22.0.0
- Release date: November 11, 2025

#### What's new in 22.0.0

| Feature | Details |
| --- | --- |
| Always Encrypted | Added support for sovereign cloud solutions Bleu and Delos. |
| Arm64 Support | Added initial Windows Arm64 support for core SSMS 22 scenarios, including connecting and querying. See **Known Issues** for a list of scenarios that are still unsupported. |
| Connection dialog | Added Fabric browsing to the Browse tab. |
| Connection Dialog | The modern dialog is the default connection dialog. |
| Connection Dialog | Added a **Reset** button to clear the fields in the **Connection Properties** section. |
| Database Tuning Advisor (DTA) | Improved DTA functionality including better tuning coverage to queries with temp tables, table variables, triggers, improved index tuning quality, and general scalability and concurrency. |
| Edit Data | Added support for Vector data type to Edit Data. |
| Execution Plans | Added the ability to open an execution plan in a new tab. When viewing an Execution Plan, right-click to bring up the menu and select **Show Execution Plan in New Tab.** See [SSMS Right Click To Open Execution Plans In A New Tab](https://feedback.azure.com/d365community/idea/8c1f1930-35cc-ee11-92bc-6045bd83e1af). |
| GitHub Copilot in SSMS (Preview) | Added [GitHub Copilot in SQL Server Management Studio (Preview)](github-copilot/get-started.md), available from the **AI Assistance** workload in the Visual Studio Installer. |
| GitHub Copilot in SSMS | Added support for model selection within chat. |
| GitHub Copilot in SSMS | Improved responses for [!INCLUDE [sssql25-md](includes/sssql25-md.md)] features. |
| GitHub Copilot in SSMS (Preview) | Introduced support for the SSMS responder when using **Ask Copilot** within **Feature Search**. |
| Indexes | Added options to create Vector and JSON indexes. Right-click **Indexes** > **New Index** > **JSON Index...** or **Vector Index...** |
| IntelliSense | Added support for CURRENT_TIMEZONE_ID syntax, see [SSMS 21 does not recognize CURRENT_TIMEZONE_ID function](https://developercommunity.microsoft.com/t/SSMS-21-does-not-recognize-CURRENT_TIMEZ/10879862). |
| IntelliSense | Added support for ANSI concatenation using the `||=` operator. |
| IntelliSense | Added support for `AI_GENERATE_EMBEDDINGS` syntax. |
| IntelliSense | Added support for regular expression functions `REGEXP_MATCHES` and `REGEXP_SPLIT_TO_TABLE`. |
| IntelliSense | Added IntelliSense support for `VECTOR_SEARCH`, `CREATE VECTOR INDEX`, `AUTOSEEDING_SYSTEM_DATABASES`, `REUSE_SYSTEM_DATABASES`, AND `CREATE JSON INDEX`. |
| JSON Viewer | Added the ability to view JSON data from the results grid. See [JSON column view like in Azure Data Studio](https://developercommunity.microsoft.com/t/JSON-column-view-like-in-azure-data-stud/10881763). |
| Libraries | Updated Server Management Objects (SMO) to version 17.100.73. |
| Libraries | Updated DacFx to version 170.0.97. |
| Linked Server Wizard | Introduced a streamlined creation wizard for linked servers, including new encryption model options. |
| Managed Instance Link | Updated the authentication control to align with the one used elsewhere in SSMS. |
| Object Explorer | Introduced display information for dimension and base type parameters for **vector** data types in Object Explorer. |
| Query Editor | Added information section to the Rename Tabs dialog to provide information about said functionality. |
| Query Hint Recommendation Tool (Preview) | Added the [Query Hint Recommendation tool (Preview)](query-hint-tool/hint-tool-overview.md) component under **Individual Components** > **Code Tools** in the Visual Studio Installer. |
| Query Plans | Added support for JSON and Vector index operations. |
| Query Store | Improved Find Query and Run Query buttons in the Tracked Queries report. |
| Results Grid | Introduced Zoom support for grid results, see [Zoom the results area independently](https://developercommunity.visualstudio.com/t/Zoom-the-results-area-independently/10860281). |
| Scripting | Added scripting support for tables with Vector columns. |
| Snippets | Added numerous new snippet files, including snippets for creating various index types, creating and altering external models for AI embeddings, and managing security and schema objects. |
| SQL Server Integration Services (SSIS) | Reinstated SQL Server Integration Services (SSIS) capabilities, including SSISDB catalog management, automated execution of SSIS packages, and the Import Export Wizard. |
| Startup commands | Removed `-G` and `-E` options (replaced by `-A)`. |
| Table Designer | Added support for Vector data type to Table Designer. |
| Themes | Introduced new themes and removed the Blue (SSMS) theme. |
| Theming | Expanded dark theme support to include the Connect to Azure Storage dialog, and the Registered Servers Export, Import, and Move Registered Server dialogs. |
| Visual Studio | Updated to Visual Studio 18.0 [11205.157]. |

#### Bug fixes in 22.0.0

| Feature | Description |
| --- | --- |
| Activity Monitor | Resolved various context menu issues for **Recent Expensive Queries** and **Active Expensive Queries**. See [Activity Monitor Failed to retrieve Execution Plan data](https://developercommunity.visualstudio.com/t/Activity-Monitor-Failed-to-retrieve-Exec/10983180). |
| Analysis Services | Resolved error `Object reference not set to an instance of an object. (Microsoft.VisualStudio.Design)` when browsing OLAP cubes. See [SSMS 21 Error browsing OLAP cubes](https://developercommunity.visualstudio.com/t/SSMS-21-Error-browsing-OLAP-cubes/10915226). |
| Analysis Services | Resolved error `Could not load file or assembly 'Microsoft.Data.ConnectionUI.Dialog, Version=17.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a' or one of its dependencies. The system cannot find the file specified.` See [Browse MDM models generates an error](https://developercommunity.visualstudio.com/t/Browse-MDM-models-generates-an-error/10920140). |
| Authentication | Introduced a new menu option in **Help** > **Clear Entra ID Token Cache** to fix an issue that prevented users were recently added to an Entra ID group from being able to login. See [Unable to login when recently been added to an EntraID group](https://developercommunity.microsoft.com/t/Unable-to-login-when-recently-been-added/10946664). |
| Available Databases | Resolved an issue that generated the error `Parse error at line: 1, column: 5: Incorrect syntax near 'NOEXEC'.` when switching between a SQL database and a Data Warehouse on the same server. See [Issue switching between DW and SQL database in SSMS21](https://developercommunity.visualstudio.com/t/-Issue-switching-between-DW-and-SQL-data/10972386). |
| Connection Dialog | Fixed an issue where the **Application Name** field in **Advanced Properties** wasn't being inherited. See [New Query from Object Explorer Does Not Inherit App Name from Highlighted Database](https://developercommunity.visualstudio.com/t/New-Query-from-Object-Explorer-Does-Not-/10977858). |
| Database Properties | Fixed an issue that blocked the ability to change compatibility level for users with `ALTER` permissions. See [Database compatibility level drop down disabled but query works](https://developercommunity.visualstudio.com/t/Database-compatibility-level--drop-down-/10927466). |
| Database Properties | Fixed validation for `MAXDOP` and `LEDGER_DIGEST_STORAGE_ENDPOINT` in Database Scoped Configurations tab. |
| Find/Replace | Restored ability to use **Ctrl**+**C** in the Find/Replace dialog after opening a saved `.sql` file. See [Copy (Ctrl+C) does not work in Find/Replace dialog](https://developercommunity.visualstudio.com/t/Copy-CtrlC-does-not-work-in-FindRepl/10909707). |
| General UI | Resolved behavior for selected dialogs that would appear behind the main windows when opened. |
| General UI | Fixed issue that generated the error `Unsaved documents cannot be cut or copied to the clipboard from the Miscellaneous Files project. You must save the unsaved document(s) before cutting or copying them.` when using **Ctrl**+**C** in the Quick Find dialog (**Ctrl**+**F**). |
| Generate Scripts Wizard | Resolved an `Object reference not set to an instance of an object` error thrown when trying to select options on the **Set Scripting Option** menu. See [Advance option on generate script button click throwing error in SSMS 2022 Preview 3](https://developercommunity.visualstudio.com/t/Advance-option-on-generate-script-button/10984224). |
| GitHub Copilot in SSMS (Preview) | Updated Copilot Badge **Learn More** menus to reference SSMS documentation. |
| GitHub Copilot in SSMS (Preview) | Fixed unexpected hang in chat window or SSMS. See [SSMS 22 Preview hangs at Modern Connection Dialog after installing GitHub Copilot](https://developercommunity.visualstudio.com/t/SSMS-22-Preview-hangs-at-Modern-Connecti/10984949). |
| GitHub Copilot in SSMS (Preview) | Addressed bug where Copilot could generate broken queries where whitespace was incorrectly ignored. |
| GitHub Copilot in SSMS (Preview) | Updated the unsaved query editor name to match what displays on the editor tab. |
| GitHub Copilot in SSMS (Preview) | Fixed invalid file name error when selecting **Add to new file** for a query in the chat window. |
| GitHub Copilot in SSMS (Preview) | Fixed an issue with an empty chat window that hangs. See [SSMS 22 Preview hangs at Modern Connection Dialog after installing GitHub Copilot](https://developercommunity.visualstudio.com/t/SSMS-22-Preview-hangs-at-Modern-Connecti/10984949). |
| GitHub Copilot in SSMS (Preview) | Improved task execution reliability. |
| Object Explorer | Resolved an error that was generated when dragging table objects from the Object Explorer to the Query Editor. |
| Object Explorer | Resolved an issue that prevented direct scroll bar navigation from working properly. See [Direct scroll bar navigation via Shift-click does not work for Object Explorer and Results Grid](https://developercommunity.visualstudio.com/t/DirectscrollbarnavigationviaShift-clickdoesnotworkforObjectExplorerandResultsgrid/10936054). |
| PowerShell | Fixed a bug that generated an error when attempting to start PowerShell from the Object Explorer context menu. |
| Query Editor | Resolved an issue where the "Include column headers" option wasn't properly applied in new query windows. See [Copying query results does not include headers, even when the "Include column headers" option is enabled](https://developercommunity.visualstudio.com/t/Copying-query-results-does-not-include-h/10969136). |
| Query Editor | Resolved a behavior that prevented scrolling of the query editor pane when the results pane was in focus. See [Query window pane does not mouse wheel scroll up if results window pane is selected](https://developercommunity.visualstudio.com/t/Query-window-pane-does-not-mouse-wheel-s/10851382). |
| Query Store | Addressed incorrect sizing with Configure Regressed Queries dialog. See ["Configure regressed queries" dialog goes off the screen vertically on 1920x1080 monitor](https://developercommunity.visualstudio.com/t/Confgure-regressed-queries-dialog-goes/10929863). |
| Reports | Addressed a bug that caused an arithmetic overflow error in the Object Execution Statistics and Batch Execution Statistics reports when execution_count exceeded the **int** data type limit. |
| Results Grid | Resolved an issue that prevented direct scroll bar navigation from working properly. See [Direct scroll bar navigation via Shift-click does not work for Object Explorer and Results Grid](https://developercommunity.visualstudio.com/t/DirectscrollbarnavigationviaShift-clickdoesnotworkforObjectExplorerandResultsgrid/10936054). |
| Solution Explorer | Resolved an error that was generated when opening a folder that was closed but had files that were open. See [SSMS 21 Preview - error while opening a folder in Windows 11](https://developercommunity.visualstudio.com/t/SSMS-21-Preview---error-while-opening-a-/10855845). |
| Status Bar | Fixed an issue that caused color contrast issues when certain colors were selected. See [Query Summary Row, Text Illegible, Accessibility Issue](https://developercommunity.visualstudio.com/t/Query-Summary-Row-Text-Illegible-Acces/10958981). |
| Status Bar | Reinstated line and column numbers in the status bar. See [In SSMS21 I can't find column number after clicking cell in grid results](https://developercommunity.visualstudio.com/t/In-SSMS21-I-cant-find-column-number-aft/10928369). |
| T-SQL Language Settings | Fixed a bug that caused some T-SQL language settings to persist between SSMS sessions. |

## Known issues

For more information, see [Known issues in SQL Server Management Studio](known-issues.md).

[!INCLUDE [support](includes/support.md)]

## Related content

- [Install SQL Server Management Studio](install/install.md)
- [SQL Server Management Studio 21 FAQ](faq.yml)
- [Visual Studio 2022 release notes](/visualstudio/releases/2022/release-notes)
