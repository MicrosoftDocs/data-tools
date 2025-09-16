---
title: "Release Notes for SQL Server Management Studio (SSMS) 22 Preview"
description: Release notes for SQL Server Management Studio (SSMS) 22 Preview.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, mbarickman
ms.date: 09/09/2025
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

<a id="22.0.0-pre.1.1"></a>

### 22.0 Preview 1.1

**[Download SQL Server Management Studio (SSMS) 22 Preview](https://aka.ms/ssms/22/preview/vs_SSMS.exe)**

- Release number: 22.0 Preview 1.1
- Release date: September 16, 2025

#### What's new in 22.0 Preview 1.1

| Feature | Details | 
| --- | --- |
| Connection dialog | Added Fabric browsing to the Browse tab. |
| Visual Studio | Updated to Visual Studio 2026 Preview 1.2. |

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
| Database Tuning Advisor (DTA) | Improved DTA functionality including better tuning coverage for queries with temp table, tuning coverage to queries with temp tables, table variables, triggers, as well as improved index tuning quality, and general scalability and concurrency. |
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
| Visual Studio | Updated to Visual Studio 18.0 Preview 1. |

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
