---
title: Azure Data Studio Release Notes
description: This article has release notes for Azure Data Studio.
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest
ms.date: 06/18/2025
ms.service: azure-data-studio
ms.topic: concept-article
ms.collection:
  - data-tools
---

# Release notes for Azure Data Studio

[!INCLUDE [azure-data-studio-deprecation](includes/azure-data-studio-deprecation.md)]

This article provides details about updates, improvements, and bug fixes for the current and previous versions of Azure Data Studio.

> [!NOTE]  
> [!INCLUDE [azure-active-directory-microsoft-entra-id](includes/azure-active-directory-microsoft-entra-id.md)]

## Current Azure Data Studio release

:::image type="icon" source="includes/media/download.svg" border="false"::: **[Download and install Azure Data Studio](download-azure-data-studio.md)**

### June 2025

Azure Data Studio 1.52 is the latest general availability (GA) release.

- Release number: 1.52
- Release date: June 18, 2025

#### Bug fixes in 1.52

| Category | Details |
| --- | --- |
| Security | Resolved an issue related to permissions on a temporary folder on some platforms |
| Extensibility | Updated the SQL Database Projects and Azure SQL migration extensions to improve security and performance |

For details about the issues addressed in the June 2025 release, visit the [June 2025 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/118?closed=1).

## Azure Data Studio feedback

You can reference [Azure Data Studio feedback](https://github.com/microsoft/azuredatastudio/issues/new/choose) for other known issues and to provide feedback to the product team.

For a list of the current known issues, visit the [issues list on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue).

## Previous Azure Data Studio releases and updates

| Azure Data Studio release | Build number | Release date | Hotfix |
| --- | --- | --- | --- |
| [January 2025](#january-2025) | 1.51.0 |  January 29, 2025 | [hotfix](#january-2025-hotfix) |
| [November 2024](#november-2024) | 1.50.0 |  November 20, 2024 | N/A |
| [August 2024](#august-2024) | 1.49.0 | August 1, 2024 | [hotfix](#august-2024-hotfix) |
| [February 2024](#february-2024) | 1.48.0 | February 28, 2024 | [hotfix](#june-2024-hotfix) |
| [November 2023](#november-2023) | 1.47.0 | November 8, 2023 | [hotfix](#november-2023-hotfix) |
| [September 2023](#september-2023) | 1.46.0 | September 20, 2023 | [hotfix](#september-2023-hotfix) |
| [July 2023](#july-2023) | 1.45.0 | July 26, 2023 | [hotfix](#july-2023-hotfix) |
| [May 2023](#may-2023) | 1.44.0 | May 24, 2023 | [hotfix](#may-2023-hotfix) |
| [April 2023](#april-2023) | 1.43.0 | April 12, 2023 | N/A |
| [March 2023](#march-2023) | 1.42.0 | March 22, 2023 | N/A |
| [January 2023](#january-2023) | 1.41.0 | January 25, 2023 | [hotfix 1](#january-2023-hotfix)<br />[hotfix 2](#january-2023-hotfix-2) |
| [November 2022](#november-2022) | 1.40.0 | November 16, 2022 | [hotfix 1](#november-2022-hotfix)<br />[hotfix 2](#november-2022-hotfix-2) |
| [August 2022](#august-2022) | 1.39.1 | August 30, 2022 | [hotfix](#august-2022-hotfix) |
| [August 2022](#august-2022) | 1.39.0 | August 24, 2022 | N/A |
| [July 2022](#july-2022) | 1.38.0 | July 27, 2022 | N/A |
| [June 2022](#june-2022) | 1.37.0 | June 15, 2022 | N/A |
| [April 2022](#april-2022) | 1.36.0 | April 20, 2022 | [hotfix](#may-2022-hotfix) |
| [February 2022](#february-2022) | 1.35.0 | February 24, 2022 | [hotfix](#february-2022-hotfix) |
| [December 2021](#december-2021) | 1.34.0 | December 15, 2021 | N/A |
| [October 2021](#october-2021) | 1.33.0 | October 27, 2021 | N/A |
| [August 2021](#august-2021) | 1.32.0 | August 18, 2021 | N/A |
| [July 2021](#july-2021) | 1.31.0 | July 21, 2021 | N/A |
| [June 2021](#june-2021) | 1.30.0 | June 17, 2021 | N/A |
| [May 2021](#may-2021) | 1.29.0 | May 19, 2021 | N/A |
| [April 2021](#april-2021) | 1.28.0 | April 15, 2021 | N/A |
| [March 2021](#march-2021) | 1.27.0 | March 17, 2021 | N/A |
| [February 2021](#february-2021) | 1.26.0 | February 18, 2021 | N/A |
| [December 2020](#december-2020) | 1.25.0 | December 9, 2020 | [hotfix](#december-2020-hotfix) |
| [November 2020](#november-2020) | 1.24.0 | November 12, 2020 | N/A |
| [October 2020](#october-2020) | 1.23.0 | October 14, 2020 | N/A |
| [September 2020](#september-2020) | 1.22.0 | September 22, 2020 | [hotfix](#september-2020-hotfix) |
| [August 2020](#august-2020) | 1.21.0 | August 12, 2020 | N/A |
| [July 2020](#july-2020) | 1.20.0 | July 15, 2020 | [hotfix](#july-2020-hotfix) |
| [June 2020](#june-2020) | 1.19.0 | June 15, 2020 | N/A |
| [May 2020](#may-2020) | 1.18.0 | May 20, 2020 | [hotfix](#may-2020-hotfix) |
| [April 2020](#april-2020) | 1.17.0 | April 27, 2020 | [hotfix](#april-2020-hotfix) |
| [March 2020](#march-2020) | 1.16.0 | March 18, 2020 | N/A |
| [February 2020](#february-2020) | 1.15.0 | February 13, 2020 | [hotfix](#february-hotfix) |
| [December 2019](#december-2019) | 1.14.0 | December 19, 2019 | [hotfix](#november-2019-hotfix) |
| [November 2019](#november-2019) | 1.13.0 | November 4, 2019 | [hotfix](#november-2019-hotfix) |
| [October 2019](#october-2019) | 1.12.0 | October 2, 2019 | [hotfix 1](#october-2019-hotfix)<br />[hotfix 2](#october-2019-hotfix-2) |
| [September 2019](#september-2019) | 1.11.0 | September 10, 2019 | N/A |
| [August 2019](#august-2019) | 1.10.0 | August 15, 2019 | N/A |
| [July 2019](#july-2019) | 1.9.0 | July 11, 2019 | N/A |
| [June 2019](#june-2019) | 1.8.0 | June 6, 2019 | N/A |
| [May 2019](#may-2019) | 1.7.0 | May 8, 2019 | N/A |
| [April 2019](#april-2019) | 1.6.0 | April 18, 2019 | N/A |
| [March 2019](#march-2019) | 1.5.1 | March 18, 2019 | [hotfix](#march-2019-hotfix) |
| [February 2019](#february-2019) | 1.4.5 | February 13, 2019 | N/A |
| [January 2019](#january-2019) | 1.3.8 | January 09, 2019 | [hotfix](#january-2019-hotfix) |

[Download the previous release of Azure Data Studio](https://github.com/microsoft/azuredatastudio/releases).

> [!NOTE]  
> All previous versions of Azure Data Studio aren't supported.

### January 2025 (hotfix)

- Release number: 1.51.1
- Release date: February 10, 2025

#### Bug fixes in 1.51.1

| Category | Details |
| --- | --- |
| Core | Added banner with information about ADS retirement |
| Core | Added notification about ADS retirement |
| Documentation | Updated README with ADS retirement information |

For details about ADS retirement, visit [aka.ms/ads-retirement](https://aka.ms/ads-retirement).

### January 2025

Azure Data Studio 1.51.0 is the latest general availability (GA) release.

- Release number: 1.51.0
- Release date: January 29, 2025

#### Bug fixes in 1.51.0

| Category | Details |
| --- | --- |
| Core | Fixed dependency conflicts preventing Notebook kernels from starting. |
| Core | Added a warning prompt before loading Jupyter configuration scripts from shared locations. |
| Proxies | Fixed tunneling issues for HTTPS-over-HTTP proxies. |
| Accessibility | Addressed minor accessibility bugs. |

For details about the issues addressed in the January 2025 release, visit the [January 2025 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/115?closed=1).

### November 2024

- Release number: 1.50.0
- Release date: November 20, 2024

#### Bug fixes in 1.50.0

| Category | Details |
| --- | --- |
| Core | Upgraded to Electron v30.5.1 to incorporate upstream fixes |
| SQL Database Projects | Updated to 1.4.4 to include the latest version of DacFx |
| Query Editor | Fixed compatibility issue with `DESC` keyword and snippets |

### August 2024 (hotfix)

- Release number: 1.49.1
- Release date: August 15, 2024

#### Bug fixes in 1.49.1

| New item | Details |
| --- | --- |
| Extensibility | Fixed minimum version detection error causing extensions to incorrectly show no extension update available |
| Installer | Fixed the certificate signing the Azure Data Studio Windows installers displaying as signed by Microsoft Azure instead of Microsoft |
| Shell | Fixed an issue with the Windows executable of Azure Data Studio has product version property as undefined |

For details about the issues addressed in the August 2024 hotfix release, visit the [August 2024 hotfix Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/114?closed=1).

#### Known issues in 1.49.1

| New item | Details | Workaround |
| --- | --- | --- |
| Installation | Azure Data Studio installation fails on RHEL 8 | Use RHEL 9, or manually install glibc-2.29 and add it to the Library Path and then re-install ADS |

### August 2024

- Release number: 1.49.0
- Release date: August 1, 2024

#### What's new in 1.49.0

| New item | Details |
| --- | --- |
| SQL Database Projects Extension | Support for Fabric mirrored SQL database (preview) target platform |

#### Bug fixes in 1.49.0

| New item | Details |
| --- | --- |
| Accessibility | Accessibility improvements were made in the Database Properties dialog. |
| Query editor | Fixed query editor override of transaction isolation level setting in T-SQL script |

For details about the issues addressed in the August 2024 release, visit the [August 2024 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/110?closed=1).

### June 2024 (hotfix)

- Release number: 1.48.1
- Release date: June 18, 2024

#### Bug fixes in 1.48.1

| New item | Details |
| --- | --- |
| Shell | Improved in-app update notifications to use Microsoft Download Center directly |

#### Known issues in 1.48.1

| New item | Details | Workaround |
| --- | --- | --- |
| Installation | Azure Data Studio installation fails on RHEL 8 | Use RHEL 9, or manually install glibc-2.29 and add it to the Library Path and then re-install ADS |

### February 2024

- Release number: 1.48.0
- Release date: February 28, 2024

#### What's new in 1.48.0

| New item | Details |
| --- | --- |
| Backup/Restore | Add restore from S3-compatible storage to restore dialog |
| Backup/Restore | Updated Restore Database option to Database context menu in Object Explorer |
| Backup/Restore | Add SQL Server Restore from URL to restore dialog |
| Copilot | Add ability to change github account |
| Query Editor | Add Session ID / SPID to query editor tabs |
| Object Explorer | Add ability to enable Ledger in Create Database dialog |
| Shell | Support Connect command when launching ADS from the command line |

#### Bug fixes in 1.48.0

| New item | Details |
| --- | --- |
| Connections | Fixed Azure AD - Universal with MFA support doesn't work on Redhat Linux |
| Connections | Fixed Error: "Cannot read properties of undefined (reading 'serverInfo')" |
| Connections | Fixed proxy errors browsing Azure resources |
| Connections | Fixed Error: "UserName cannot be null or empty when using SqlLogin authentication" message when using 'Active Directory Default' authentication |
| Edit Data | Deleting row causes focus to be in wrong row |
| Notebooks | Fixed Installing Notebook dependencies failed with error: Cannot read property 'version' of undefined |
| Notebooks | Fixed "Open in editor" link in Notebooks search results doesn't work |
| Object Explorer | Removed the drop database icon from the connection browser menu |
| Query Editor | Fixed tabs not visible in query editor |
| Query Editor | Fixed query editor does not display any results when results being with "#" |
| Query Editor | Improved speed when copying data from results grid to clipboard |
| Query Editor | Fixed blank/empty results pane after executing a query |
| Query Editor | Fixed invalid results when field contains HTML or XML |

For details about the issues addressed in the February 2024 release, visit the [February 2024 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/107?closed=1).

#### Known issues in 1.48.0

| New item | Details | Workaround |
| --- | --- | --- |
| Installation | Azure Data Studio installation fails on RHEL 8 | Use RHEL 9, or manually install glibc-2.29 and add it to the Library Path and then re-install ADS |

### November 2023 (hotfix)

- Release number: 1.47.1
- Release date: January 10, 2024

#### Bug fixes in 1.47.1

| New item | Details |
| --- | --- |
| Query Editor | Fixed query results with blank string interpreted as XML |
| Shell | Fixed not all installation files signed |
| Security | Update to [Microsoft.Data.SqlClient 5.1.3](https://github.com/dotnet/SqlClient/blob/main/release-notes/5.1/5.1.3.md) that patches [CVE-2024-0056](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2024-0056) |

#### Known issues in 1.47.1

| New item | Details | Workaround |
| --- | --- | --- |
| Installation | Azure Data Studio installation fails on RHEL 8 | Use RHEL 9, or manually install glibc-2.29 and add it to the Library Path and then re-install ADS |

### November 2023

- Release number: 1.47.0
- Release date: November 8, 2023

#### What's new in 1.47.0

| New item | Details |
| --- | --- |
| Connection | Improved visibility of advanced options in tabs and tooltips |
| Database Properties | Implemented usability improvements to object properties dialogs |
| Extensibility | Allow extensions to hook into provider events |
| Extensibility | Improved charting capability |
| General | Enabled `Mssql: Parallel Message Processing` by default to improve application performance when working with MSSQL connections. |
| General | Added `Mssql: Parallel Message Processing Limit` with a default of 100 to control the number of threads used for parallel processing. |
| General | Updated notifications so they close automatically upon task completion |
| Notebooks | Updated version to 6.5.6 and removed traitlets v5.9.0 from required notebook dependencies |
| Object Explorer | Added `Select Top 1000` menu option for the history table of a system-versioned temporal table |
| Object Explorer | Usability improvements including added context menus |
| Result Set | Added additional options for saving results to Excel |
| Result Set | Added support to display formatted XML data when stored as a VARCHAR data type |
| User Management | References to Azure Active Directory (Azure AD) have been updated to Microsoft Entra, see [Azure AD is Becoming Microsoft Entra ID](https://techcommunity.microsoft.com/t5/microsoft-entra-blog/azure-ad-is-becoming-microsoft-entra-id/ba-p/2520436) for details. |
| VS Code Merge | Merges upstream improvements from VS Code 1.80, 1.81, and 1.82. These releases contained numerous new features and quality, performance, stability, and compliance enhancements. The full details can be reviewed in the VS Code release notes at: [Visual Studio Code June 2023](https://code.visualstudio.com/updates/v1_80), [Visual Studio Code July 2023](https://code.visualstudio.com/updates/v1_81), and [Visual Studio Code August 2023](https://code.visualstudio.com/updates/v1_82). |

#### Bug fixes in 1.47.0

| New item | Details |
| --- | --- |
| Authentication | Fixed error "multiple matching_tokens occurred when acquiring token." when authenticating to Azure resources |
| Autocomplete | Fixed autocomplete suggests "abort" whenever new comment is begun |
| Connection | Updated prefix for Clear Pooled Connections in the command palette to use the MSSQL prefix |
| Connection | Fixed proxy setting values not being passed to backend SQL Tools Service |
| Connection | Removed tenant filter config setting |
| Extensibility | Fixed issue where server dashboard was loading before activation of extension completed |
| Notebooks | Fixed issue where the Notebook Python process continued to run after Azure Data Studio is closed |
| Notebooks | Fixed Jupyter Notebook entry in new file command under command palette does nothing |
| Object Explorer | Fixed silent failure when attempting to open script files |
| Object Explorer | Removed duplicate entry for Group By Schema from command palette |
| Object Explorer | Addressed behavior where selecting Manage for an Azure SQL Database opened the dashboard for the logical server instead of the database |
| Profiler Extension | Fixed issue where Profiler columns weren't resizeable |
| Profiler Extension | Resolved problem where selecting Ctrl + F in the Profiler extension didn't bring up Find dialog |
| Query Editor | Updated maximum value supported for `Query: Text Size` setting to fix results not being copied to the clipboard |
| Query Editor | Fixed issue where query editor wouldn't open due to initialization errors |
| Query Editor | Fixed error "Cannot connect to the database due to invalid OwnerUri" after saving a new query file |
| Query History Extension | Fixed error loading query history items |
| Schema Compare | Fixed issue where schema compare doesn't show that it's running while doing a comparison |
| Schema Compare | Fixed issue where Azure Data Studio stops responding after attempting to apply schema compare changes |
| Shell | Shortened query tab titles for edit data |
| Shell | Updated hyperlinks to use correct theming so they're visible when using dark theme |
| Shell | Updated shell default behavior to not open any editor when `Show welcome page on startup` isn't selected |
| SQL Project | Fixed issue where database project fails to build with syntax error when including a database scoped credential object |

For details about the issues addressed in the November 2023 release, visit the [November 2023 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/105?closed=1).

#### Known issues in 1.47.0

| New item | Details | Workaround |
| --- | --- | --- |
| Installation | Azure Data Studio installation fails on RHEL 8 | Use RHEL 9, or manually install glibc-2.29 and add it to the Library Path and then re-install ADS |

### September 2023 (hotfix)

- Release number: 1.46.1
- Release date: October 3, 2023

#### Bug fixes in 1.46.1

| New item | Details |
| --- | --- |
| Security | Update to Electron v22.3.25 with patch for [CVE-2023-5217](https://github.com/advisories/GHSA-qqvq-6xgj-jw8g) |

For details about the issue addressed in the September 2023 hotfix release, visit the [September 2023 Hotfix Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/106?closed=1).

#### Known issues in 1.46.1

| New item | Details | Workaround |
| --- | --- | --- |
| Installation | Azure Data Studio installation fails on RHEL 8 | Use RHEL 9, or manually install glibc-2.29 and add it to the Library Path and then re-install ADS |

### September 2023

- Release number: 1.46.0
- Release date: September 20, 2023

#### What's new in 1.46.0

| New item | Details |
| --- | --- |
| Attach/Detach Database | Introduced support for attaching and detaching databases (Preview) |
| Connection | Introduced support for custom cloud providers, see [Azure Data Studio - Azure connectivity](azure-connectivity.md#configuring-custom-cloud-endpoints) for configuration information |
| Connection | Enabled Connection Pooling as default behavior |
| Connection | Introduced command `SQL Server: Clear Pooled Connections` to clear inactive pooled connections |
| Database Properties | Introduced support for viewing database properties (Preview) |
| Result Set | Updated copy notification to automatically close after three (3) seconds, and included an option to disable notifications |
| Result Set | Added a prompt to open the file location after saving result to Excel |
| Profiler Extension | Introduced a progress dialog when opening an XEL file |
| Server Properties | Introduced support for viewing server properties (Preview) |
| SQL Database Projects Extension | Released version 1.3.1 |
| SQL Database Projects Extension | Added support for "Azure Synapse Serverless SQL Pool" target platform |
| SQL Database Projects Extension | Added support for "Synapse Data Warehouse in Microsoft Fabric" target platform |
| SQL Database Projects Extension | Updated to use Microsoft.Build.Sql SDK version 0.1.12-preview |

#### Bug fixes in 1.46.0

| New item | Details |
| --- | --- |
| Accessibility | Improved screen reader prompts for SQL Database Projects extension, Database Migration Assessment for Oracle extension, SQL Agent extension, and when installing a new extension |
| Accessibility | Addressed issues with install button tool tip, new connection button, and new server group buttons |
| Accessibility | Fixed color contrast for creating connections and notebooks, running queries, and deploying a server |
| Connection | Added refresh prompt for Azure accounts when error AADSTS700082 occurs |
| Connection | Introduced notification when a duplicate connection exists upon dragging a connection to a different group |
| Connection | Fixed issue to prevent Dashboard server name from being replaced with profile name |
| Connection | Added retry logic to wait for resume when establishing connection to a serverless Azure database |
| Connection | Fixed issue where tab color didn't align with server group color |
| Connection | Updated Cluster Server connection property to have the correct Boolean value for Cosmos DB |
| Connection | Fixed issue with advanced connection options not correctly transferred to change password dialog |
| Connection | Addressed incorrect label for first connection in the Recent connections list |
| Connection | Improved account selection experience after enabling cloud settings |
| General | Fixed issue with incorrect cell colors when editing data |
| General | Addressed problem with invalid data for a column's data type when editing data |
| General | Re-enabled full screen toggle behavior for the F11 key binding |
| Notebooks | Addressed issue where kernel failed to change correctly when switching to Python |
| Query Editor | Fixed Intellisense refresh behavior |
| Query Editor | Improved query execution performance |
| Query Editor | Improved read performance for large data sets |
| Query Editor | Addressed issue where selecting Cancel wouldn't immediately cancel a query that was executing |
| Query Editor | Resolved problem of queries hanging when executing against Synapse Dedicated Pool |
| Query Plan Viewer | Fixed issue where missing index definition recommendation included incorrect column |
| Query Plan Viewer | Addressed issue with query plan XML having the incorrect format |
| Result Set | Corrected XML formatting when opening a column from the result set |
| Result Set | Fixed issue where copying results to clipboard didn't work |
| Schema Compare | Added support to automatically resize the split view when the window changes size |
| Schema Compare | Addressed error "StartIndex cannot be less than zero" which occurred when applying change using Schema Compare |
| Schema Compare | Display 'Yes' button to re-compare after changing options in Schema Compare |
| SQL Database Projects | Fixed issue where databases weren't populated if a project was created from the server instead of a database |
| SQL Database Projects | Addressed error 'Could not run the "SqlModelResolutionTask" task because MSBuild couldn't create or connect to a task host with runtime "NET" and architecture "arm64"' resulting in build failure on arm64 with SDK-style and legacy style projects |
| Welcome Page | Improved display of Install button under the extension list on Welcome Page |

For a full list of bug fixes addressed for the September 2023 hotfix release, visit the [September 2023 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/102?closed=1).

#### Known issues in 1.46.0

| New item | Details | Workaround |
| --- | --- | --- |
| Installation | Azure Data Studio installation fails on RHEL 8 | Use RHEL 9, or manually install glibc-2.29 and add it to the Library Path and then re-install ADS |

For a list of the current known issues, visit the [issues list on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue).

### July 2023 (hotfix)

- Release number: 1.45.1
- Release date: August 07, 2023

#### Bug fixes in 1.45.1

| New item | Details |
| --- | --- |
| Connection | Fixed an issue that prevented all connections from appearing in the recent and saved connection tree views. |
| Connection | Fixed an issue where temporary connections weren't saved in the recent connection list. |
| Database Migration Assessment for Oracle | Resolved issue where links to open the assessment output were no longer working. |
| Database Schema Conversion Toolkit | Resolved issue where links to open the conversion output were no longer working. |
| Profiler | Fixed an issue where the session dropdown list wasn't populated when Profiler is opened. |
| Profiler | Addressed an issue where the running state was incorrectly set after a session was started. |

For a full list of bug fixes addressed for the July 2023 hotfix release, visit the [July 2023 Hotfix Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/104?closed=1).

#### Known issues in 1.45.1

| New item | Details | Workaround |
| --- | --- | --- |
| Installation | Azure Data Studio installation fails on RHEL 8 | Use RHEL 9, or manually install glibc-2.29 and add it to the Library Path and then re-install ADS |

### July 2023

- Release number: 1.45.0
- Release date: July 26, 2023

#### What's new in 1.45.0

| New item | Details |
| --- | --- |
| Connection | Introduced support for Tenant hierarchy in the Azure tree |
| Connection | Updated Azure tree icons |
| Connection | Updated the Azure tree in the Connection Pane to show only available resource types |
| Connection | Added Azure Postgres Flexible Server and Azure Cosmos DB for PostgreSQL in the Azure resource tree |
| Connection | Introduced support for multiple connections against same target, with different profile names and advanced options |
| Connection | Added capability to clear encryption keys with the 'Clear Azure Account Token Cache' command |
| Connection | Introduced support for connection pooling for MSSQL connections |
| GitHub Copilot | GitHub Copilot extension version 1.95.239 |
| MySQL Extension | General Availability |
| Object Explorer | Added support for additional Filter options in Object Explorer |
| Object Explorer | Reduced size of server group color block |
| Object Explorer | Enabled 'Async Server tree' for the Server tree view |
| Object Explorer | Added inline actions (for example, edit, delete, refresh) |
| Object Explorer | Introduced an action to collapse all open objects in Object Explorer |
| Object Explorer | Added ability to use left and right arrows in OE to open or close trees |
| Object Explorer | Right-click menu options updated and order modified |
| Profiler / Extended Events | Introduced support for opening .XEL files up to 1GB in size |
| Query Editor | Introduced a new configuration option to control whether to add a line break between rows when copying if the previous row has a trailing line break |
| Result Set | Introduced keyboard shortcut (Ctrl/CMD + Shift + C) to copy information from the results grid with headers |
| Result Set | Introduced keyboard shortcut (Ctrl/CMD + Shift + O) to sort columns in a result set |
| SQL Database Projects Extension | Added the ability to create a publish profile from the Add Item... menu |
| Table Designer | Added configuration option to prevent DDL triggers from being disabled as part of the table modification |
| User Management | Improved table component performance in the Securables dialog of User properties |
| VS Code merge | VS Code merges to version 1.79.2, read [their release notes](https://code.visualstudio.com/updates/v1_79) to learn more |

#### Bug fixes in 1.45.0

| New item | Details |
| --- | --- |
| Accessibility | Improved contrast for buttons on Welcome page when using light themes |
| Accessibility | Improved focus on Home tab when using High Contrast Aquatic/Desert theme |
| Accessibility | Corrected border color the issue reporter dialog when using light theme |
| Accessibility | Fixed multiple issues with screen readers |
| Accessibility | Improved keyboard navigation in select database dropdown list and added visual label |
| Accessibility | Added required indicator for Server group name when configuring a server group |
| Accessibility | Fixed display so contents are visible at 200% zoom in Notebook cell |
| Accessibility | Added tooltip for Learn more button in New Deployment window |
| Backup/Restore | Addressed issue with backup/restore dialog titles not updating for non-MSSQL databases |
| Central Management Servers Extension | Resolved error generated after saving a connection using SQL authentication |
| Charting | Addressed issue with mix/max value setting for a chart axis |
| Connection | Improved dialog window for adding an Azure account when authentication code is required |
| Connection | Fixed throttling of ARM requests when in the Browse Connections tab |
| General | Fixed issue with vertical scrolling in dialog windows |
| General | Fixed error "Cannot read properties of undefined" |
| Notebooks | Addressed inability to open JSON in a new tab from Notebook results cell |
| Notebooks | Fixed error "Unable to load and parse grammar for scope markdown.math.inline" when creating a Notebook text cell |
| Object Explorer | Addressed connection leak, which occurred when renaming a table |
| Object Explorer | Improved error handling in server tree expand requests |
| Object Explorer | Fixed issue with unexpected connection drops in Object Explorer |
| Query Editor | Corrected syntax highlighting for nested multi-line comments |
| Query Editor | Addressed issue where folding behavior incorrectly included blank lines at the end of a text block |
| Query Editor | Resolved issue when executing USE DATABASE_NAME command and database context didn't change in the status bar |
| Query Plan Viewer | Fixed issue with filter icon appearing over query text in Top Operations window |
| Result Set | Fixed issue where HTML entered in Edit Rows mode was being rendered |
| Result Set | Fixed incorrect aggregation (sum) when selecting rows in the result set and implemented performance improvements |
| Result Set | Improved support for copying large result sets to the clipboard |
| Result Set | Added progress notification when copying result sets and implemented performance improvements |
| Result Set | Improved formatting and result set navigation for columns containing XML |
| Result Set | Added notification to identify when the number of rows or columns copied exceed Excel limits |
| SQL Database Projects Extension | Addressed issue with schema compare dropping constraints |
| SQL Database Projects Extension | Removed incorrect delete command from database references node |
| SQL Database Projects Extension | Introduced ability to add sqlcmd variables without a default value via the quickpick |
| User Management | Removed unsupported database roles for Azure SQL DB user creation |
| User Management | Included MUST_CHANGE option for Azure SQL when creating a new login or for a password change |

For a full list of bug fixes addressed for the July 2023 release, visit the [July 2023 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/101?closed=1).

#### Known issues in 1.45.0

| New item | Details | Workaround |
| --- | --- | --- |
| Installation | Azure Data Studio installation fails on RHEL 8 | Use RHEL 9, or manually install glibc-2.29 and add it to the Library Path and then re-install ADS |

### May 2023 (hotfix)

- Release number: 1.44.1
- Release date: June 5, 2023

#### Bug fixes in 1.44.1

| New item | Details |
| --- | --- |
| Backup & Restore | Fixed an issue in Object Explorer where the Restore dialog failed to open |
| Connection | Resolved issue that caused a login failure in Azure SQL for hyphenated user accounts |
| Object Explorer | Addressed inability to open a view using CTRL/CMD + Q or the Open View menu |
| Query Editor | Introduced a performance improvement in the Query Editor language service by enabling connection pooling |

For a full list of bug fixes addressed for the May 2023 Hotfix release, visit the [May 2023 Hotfix Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/103?closed=1).

### May 2023

- Release number: 1.44.0
- Release date: May 24, 2023

#### What's new in 1.44.0

| New item | Details |
| --- | --- |
| Connection | Enabled Sql Authentication Provider by default for Azure SQL connections and the MSAL Authentication Library. Learn more at [Connect with Azure Data Studio](https://aka.ms/azuredatastudio-connection) |
| Connection | Introduced support for passing in advanced connection options in command line arguments |
| Connection | Added ability to provide an Application Name in the connection string parameter |
| Connection | Added support for advanced connection options for other providers |
| General | Added support for customizing table keyboard shortcuts |
| General | Added warning notification on startup if Azure PII logging is enabled |
| GitHub Copilot | GitHub Copilot extension for autocomplete-style suggestions added to extension gallery. Learn more at [GitHub Copilot extension: Overview](extensions/github-copilot-extension-overview.md) |
| Notebooks | Fixed issue where deleted text listed using the Find feature |
| Object Explorer | Introduced filtering capability for Object Explorer (preview) |
| Query Editor | Shorted text for Change Connection and Export as Notebook button |
| Query Results | Increased the default max column width |
| SQL Database Projects Extension | Released version 1.1.1 |
| SQL Database Projects Extension | Improved performance of loading one or more large projects |
| SQL Database Projects Extension | Introduced ability to save publish settings to a new or existing publish profile |
| User Management | Added support for creating database and server roles (preview) |
| User Management | Improved authentication options when creating database users (preview) |

#### Bug fixes in 1.44.0

| New item | Details |
| --- | --- |
| Accessibility | Added labels to radio groups in SQL Database Projects dialog |
| Accessibility | Fixed issue with narrator reading character twice in network share path for Azure SQL migration extension |
| Accessibility | Addressed problem where keyboard focus didn't shift to error message when creating a new database |
| Accessibility | Fixed issue with voiceover not announcing label names correctly when updating a database project |
| Connection | Improved token refresh behavior |
| Connection | Enabled support to login with blank passwords when creating MSSQL connection |
| Connection | Added change password dialog display after password expiration occurs for a SQL login |
| Connection | Addressed scenario where Intellisense stopped working after a connection token expired |
| Connection | Fixed behavior where PostgreSQL username was incorrectly replaced |
| Connection | Implemented support for connections against the same server but with different properties |
| Connection | Resolved issue where connection status changed to red (disconnected) after moving an active connection to a server group |
| Connection | Updated Azure node in Connection dialog to include notation when no subscriptions are found |
| Connection | Updated firewall dialog to pre-select the account and tenant in the connection dialog |
| Extension | Fixed an issue with over-encoded URLs in diagnostic error messages |
| Intellisense | Resolved issue with SORT_IN_TEMPDB not recognized as valid T-SQL syntax when creating an object |
| Notebooks | Updated Notebook connection to support MySQL and PostgreSQL when connecting to an existing Notebook |
| Query Results | Fixed overlapping action display when multiple result sets are returned |
| Schema Compare | Update scmp files to be backward compatible |
| SQL Database Projects Extension | Fixed multiple issues related to SQLCMD variables and projects |
| SQL Database Projects Extension | Addressed a failure that was occurring when using schema compare with Azure Synapse dedicated pools |
| SQL Database Projects Extension | Resolved problem where a database project wouldn't build after a reference to a system database was added from SSDT |
| SQL Database Projects Extension | Fixed issue where projects were listed twice when using multi root workspaces |
| SQL Database Projects Extension | Fixed an issue where file structure information wasn't stored in the scmp file after a schema compare |
| SQL Database Projects (VS Code) | Updated default folder location when creating a new project from database workflow |

For a full list of bug fixes addressed for the May 2023 release, visit the [May 2023 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/98?closed=1).

### April 2023

- Release number: 1.43.0
- Release date: April 12, 2023

#### What's new in 1.43.0

| New item | Details |
| --- | --- |
| Connection | Added notation for required properties (for example, Attestation protocol and Attestation URL) when Secure Enclaves are enabled |
| SQL Database Projects extension | General Availability |
| SQL Database Projects extension | Move and rename files within Database Projects view |
| SQL Database Projects extension | SQLCMD variables available for editing in Database Projects view |
| Object Explorer | Double-clicking on a user or table in Object Explorer opens the designer for the object |
| Query Editor | Added a Parse button to the Query Editor toolbar for parsing queries before execution |
| Query Results | Added support to select a row in query results via double-click |

#### Bug fixes in 1.43.0

| New item | Details |
| --- | --- |
| Connection | Added support for linked accounts with same username but different domains |
| Connection | Fixed issue with incorrect cache write path |
| Connection | Added ability to include optional name and grouping when creating a new connection using a connection string |
| Connection | Updating username in MSSQL connections to use Preferred username for the display name |
| Connection | Fixed issue with encoding for OSX keychain on macOS |
| Connection | Added support for Microsoft Entra multifactor authentication and 'Sql Authentication Provider' on Linux |
| Dataverse | Addressed error generated when expanding the database node for a Dataverse database in Object Explorer |
| IntelliCode extension | Fixed error that occurred when launching Azure Data Studio with Visual Studio Code IntelliCode extension installed |
| PostgreSQL extension | Implemented support for exporting query results on Apple M1 from a notebook |
| SQL Database Projects extension | Added Accessibility Fixes related to screen reader, label names, and improved focus when navigating |

For a full list of bug fixes addressed for the April 2023 release, visit the [April 2023 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/99?closed=1).

### March 2023

- Release number: 1.42.0
- Release date: March 22, 2023

#### What's new in 1.42.0

| New item | Details |
| --- | --- |
| ARM64 Support for macOS | Implemented native arm64 SqlToolsService support for arm64 Windows and macOS. |
| Connection | Changed the icon under Linked Accounts when adding a new Azure account. |
| Connection | Introduced support for the Command Timeout connection property. |
| Connection | Added support for all three connection encryption options: Strict, Mandatory, and Optional. |
| Connection | Introduced HostNameInCertificate connection property under Security on the Advanced tab, for server with a certificate configured. |
| Connection | Added new advanced option in the Connection dialog to support Secure Enclaves. |
| Connection | Introduced a new setting, Mssql Enable Sql Authentication Provider to allow connections to be maintained without the concern of losing access token lifetime or getting dropped by server. Access tokens are refreshed internally by the SqlClient driver when they are expired. This option is disabled by default. |
| Connection | Added support for connections to Microsoft Dataverse using the TDS endpoint. |
| Connection | Introduced additional error reporting for Azure connections. |
| Connection | Introduced support for change password. |
| Connection | Added support for encryption options for Arc SQL Managed Instance when server certificates aren't installed. |
| Deployment | Moved the New Deployment option from the Connections breadcrumb to the File Menu. |
| Object Explorer | Introduced ability to group objects in Object Explorer by database schema. Grouping applies to all MSSQL connections when enabled or disabled. |
| Object Explorer | Introduced a new option to allow a custom timeout to be configured for Object Explorer. Within Settings, enable Mssql > Object Explorer: Expand Timeout. |
| Query Results | Added option to disable special handling for JSON strings. |

#### Bug fixes in 1.42.0

| New item | Details |
| --- | --- |
| Accessibility | Updated server group color display to improve visibility and contrast. |
| Backup | Addressed inability to select "Backup Set" checkbox. |
| Connection | Removed refresh action for connections that are disconnected. |
| Connection | Fixed issue with MSAL not properly set for connections. |
| Connection | Added ability to delete a server group if no connections exist for it. |
| Connection | Added connection display name to the Delete Connection dialog. |
| Connection | Azure connections with "Do not save" for the server group are no longer added to the default server group list. |
| Connection | Improved error handling in the connection dialog. |
| Connection | Fixed issue where saved passwords weren't retained for Azure SQL connections. |
| Connection | Improved method to retrieve database access when connecting to Azure SQL. |
| Connection | Improved connection experience for cloud users. |
| Connection | Improved account and tenant selection when connecting to Azure SQL in the connection dialog. |
| Deployment | Improved narration for deployment wizard. |
| Installation | Updated default install location for the Windows on ARM64 installer. |
| MySQL Extension | Addressed issue where dialog boxes in the MySQL connection pane weren't editable. |
| Notebooks | Fixed issue with updating the relative path in a Notebook cell. |
| Notebooks | Fixed issue that caused internal notebook links to break when editing characters in the page. |
| Notebooks | Addressed error thrown when opening a Notebook via a link. |
| Object Explorer | Fixed issue with Object Explorer node not expanding. |
| Query Editor | Fixed database dropdown list for contained users to display correctly. |
| Query Editor | Addressed issue where database dropdown list wasn't ordered the same as in Object Explorer. |
| Query Editor | Added the ability to properly escape special characters when they exist in object names. |
| Query Editor | Fixed issue that caused query timer to continue to run even though execution was complete. |
| Query Plan Viewer | Addressed an issue where a query plan wouldn't render when opened via a URL. |
| Query Results | Improved precision formatting for datetimeoffset data type. |

For a full list of bug fixes addressed for the March 2023 release, visit the [March 2023 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/95?closed=1).

### January 2023 (hotfix 2)

- Release number: 1.41.2
- Release date: February 10, 2023

#### Bug fixes in 1.41.2

| New item | Details |
| --- | --- |
| Connection | Addressed an issue that prevented users in non-public clouds from using Azure Data Studio with MSAL. |
| Connection | Fixed a bug that opened the output window when unexpected errors occurred. |

For a full list of bug fixes addressed for the January 2023 hotfix 2 release, visit the [January 2023 Hotfix 2 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/97?closed=1).

### January 2023 (hotfix)

- Release number: 1.41.1
- Release date: January 30, 2023

#### Bug fixes in 1.41.1

| New item | Details |
| --- | --- |
| Connection | Fixed a bug causing incorrect Azure account tenant selection when connecting to server through the Azure view. |
| Object Explorer | Fixed a regression that caused Object Explorer to not show database objects for Azure SQL DB Basic SLO. |

For a full list of bug fixes addressed for the January 2023 hotfix release, visit the [January 2023 Hotfix 1 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/96?closed=1).

### January 2023

- Release number: 1.41.0
- Release date: January 25, 2023

#### What's new in 1.41.0

| New item | Details |
| --- | --- |
| Azure Subscriptions | Introduced Azure Synapse Analytics and Dedicated SQL Pools nodes. |
| Azure SQL Migration Extension | Premium series memory optimized SQL MI SKUs included in recommendations. |
| Connection | Migrated Azure authentication library from ADAL to MSAL. MSAL is the library used by default starting with release 1.41. However, if you encounter issues, you can change back to ADAL within **Settings > Azure: Authentication Library**. |
| Connection | Added ability to provide a description when creating a firewall rule from Azure Data Studio. |
| Connection | Include ability to change password for new or expired login. |
| Connection | Add support for SQL Server Alias use when connecting to a server. |
| MongoDB Atlas Extension | Provides the ability to connect to and query data on MongoDB Atlas (Preview). |
| Notebooks | Provide option for users to convert markdown to a table or not when HMTL table tag is present. |
| Object Explorer | Databases are no longer brought online in serverless Azure SQL when Databases node is expanded. |
| Object Explorer | Added support for Ledger views. |
| Query Editor | Fixes and updates to SQL grammar (colorization and autocomplete). |
| Query Plan Viewer | Changed default folder to be user's home directory when saving a query plan. |
| Query Results | Added ability to only copy Column Headers, and only for cells that are highlighted. |
| Query Results | Added option to show or hide the action bar in the results window. |
| Query Results | Increased height of horizontal scrollbar in results window. |
| Query Results | Added new aggregate details in the results toolbar when selecting multiple cells. |
| SQL Projects Extension | Provide the ability select an existing project via a new dropdown list. |

#### Bug fixes in 1.41.0

| New item | Details |
| --- | --- |
| Accessibility | Accessibility improvements were made in the Query Plan Viewer, Query History Extension and Migration Extension. |
| Big Data Cluster | Fix missing connect icon in BDC view header bar. |
| Big Data Cluster | Fixed issue preventing HDFS nodes for BDC servers in Object Explorer from expanding. |
| Connection | Added ability to delete a connection that has expired Microsoft Entra credentials. |
| Connection | Improved experience when Microsoft Entra token expiration occurs. |
| Connection | Improved connection experience when using multiple Azure tenants. |
| Connection | Addressed problem with adding a firewall exception for a nondefault Azure subscription. |
| Migration Extension | Added support for non-public clouds for migration scenarios. |
| MySQL Extension | Updated resource endpoints to support Microsoft Entra logins in the MySQL extension. |
| Notebooks | Improve Intellisense refresh in Notebook cells. |
| Notebooks | Address issue with "New Notebook Job" resulting in an empty form. |
| Object Explorer | Fixed issue with database list not loading. |
| Object Explorer | Fixed issue with key binding for objectExplorer.manage not working. |
| Query Execution | Fixed error generated when executing a query with LEFT JOIN and NULL values. |
| Query Plan Viewer | When saving query plans (.sqlplan file), the filename numerically increments to prevent duplicate filenames. |
| Query Results | Fixed issue where users were unable to open JSON data as a new file. |
| Query Results | Provide proper cell selection and navigation in the query results grid. |
| Query Results | Improved the handling of line breaks when copying cell contents. |
| Query Results | Addressed issue where a column would resize incorrectly when autosizing in the results output. |
| Query Results | Improved JSON cell handling from query results. |
| Query Results | Fixed behavior where focus was incorrectly set on a cell using keyboard navigation. |
| Resource Deployment | Remove 'Preview' flag for SQL Server 2022 deployment types. |
| Schema Compare Extension | Fixed problem where differences in schema compare weren't being highlighted. |
| Schema Compare Extension | Permissions are now included in schema compare when the "Include Permissions" option is selected. |
| SQL Projects Extension | Changes to db_datawriter or db_datareader roles are now supported. |
| SQL Projects Extension | Updated Database Projects Net Core SDK Location dialog to be more descriptive. |
| Table Designer | Updated Table Designer to disable transaction support for Azure Synapse databases. |
| Table Designer | Addressed problem of the table name not refreshing after being updated prior to publishing. |
| Table Designer | Fixed issue where table designer couldn't be opened for existing Ledger tables. |

For a full list of bug fixes addressed for the January 2023 release, visit the [January 2023 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/92?closed=1).

### November 2022 (hotfix 2)

- Release number: 1.40.2
- Release date: December 27, 2022

#### Bug fixes in 1.40.2

| New item | Details |
| --- | --- |
| Terminal | Fixed a security vulnerability that allowed an .exe to be easily run by a user. |

### November 2022 (hotfix)

- Release number: 1.40.1
- Release date: November 23, 2022

#### Bug fixes in 1.40.1

| New item | Details |
| --- | --- |
| Object Explorer | Fixed bug that caused folders in the Servers tree to display incorrect contents. |

### November 2022

- Release number: 1.40
- Release date: November 16, 2022

#### What's new in 1.40.0

| New item | Details |
| --- | --- |
| Connections | Connections for SQL now default to Encrypt = 'True'. |
| ARM64 Support for macOS | ARM64 build for macOS is now available. |
| Table Designer | Announcing the General Availability of the Table Designer. |
| Table Designer | Period columns now added by default when System-Versioning table option is selected. |
| Table Designer | Added support for hash indexes for In-Memory tables, and added support for columnstore indexes. |
| Table Designer | New checkbox added, "Preview Database Updates", when making database changes to ensure that users are aware of potential risks prior to updating the database. |
| Table Designer | "Move Up" and "Move Down" buttons added to support column reordering for Primary Keys. |
| Query Plan Viewer | Announcing the General Availability of the Query Plan Viewer in Azure Data Studio. |
| Query Plan Viewer | Introduced the ability to identify the most expensive operator in plan, based on user-selected metric (for example, cost, elapsed time). |
| Query Plan Viewer | Updates were made to the properties window to allow for full display of text when hovering over a cell, and text can now be copied to the clipboard. |
| Query Plan Viewer | Implemented filter functionality in the Properties pane for an execution plan. |
| Query Plan Viewer | Added support for collapsing and expanding all subcategories within the Plan Comparison Properties window. |
| Query History Extension | Announcing the General Availability of the SQL History Extension. |
| Query History Extension | Now includes ability to persist history across multiple user sessions. |
| Query History Extension | Added the ability to limit the number of entries stored in the history. |
| Schema Compare | Users can now open `.scmp` files directly from the context menu for existing files in the file explorer. |
| Query Editor | Now allows full display for text strings larger than 65,535 characters. |
| Query Editor | Added support for the SHIFT key when making multiple cell selections. |
| MySQL Extension | Support for MySQL extension is now available in preview. |
| Azure SQL Migration Extension | Azure SQL Database Offline Migrations is now available in preview. Customers can use this new capability to save and share reports as needed. |
| Azure SQL Migration Extension | Addition of elastic Azure recommendations model. |
| Database Migration Assessment for Oracle | Assessment tooling for Oracle database migrations to Azure Database for PostgreSQL and Azure SQL available in preview. |
| VS Code merge | VS Code merges to version 1.67. Read [their release notes](https://code.visualstudio.com/updates/v1_67) to learn more. |
| SQL Database Projects | Adds SQL projects support for syntax introduced in SQL Server 2022. |

#### Bug fixes in 1.40.0

| New item | Details |
| --- | --- |
| Connections | Fixed bug that occurred when trying to connect to the Dedicated Admin Connection (DAC) on SQL Server. |
| Connections | Fixed issue with wrong tenant showing up while trying to connect to a database with Microsoft Entra login. |
| Connections | Fixed zoom reset behavior when adding a new connection. |
| Connections | Fixed loading bug what occurred when attempting to sign in to Azure via proxy. |
| Connections | Fixed issue encountered while attempting to connect to a "sleeping" Azure SQL Database. |
| Object Explorer | Fixed the SELECT script generation issue for Synapse Databases. |
| Schema Compare | Fixed error that caused duplication of comment headers when applying schema changes on stored procedure objects. |
| Schema Compare | Fixed issue that prevented schema compare issues when creating a new empty schema with a "DOMAIN\User" pattern. |
| Query Editor | Fixed bug that caused results to be lost upon saving query files. |
| Table Designer | Fixed a bug that caused creation of a new table when renaming an existing table. |
| Query Plan Viewer | Fixed missing index recommendation T-SQL syntax. |
| SQL Projects | Fixed bug in SQL Projects that led to extension not using output path when publishing a project. |
| SQL Projects | Fixed bug that caused .NET install to not be found when using the SQL Projects extension on Linux platforms. |

For a full list of bug fixes addressed for the November 2022 release, visit the [November 2020 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/91?closed=1).

### August 2022 (hotfix)

- Release number: 1.39.1
- Release date: August 30, 2022

#### Bug fixes in 1.39.1

| New item | Details |
| --- | --- |
| Object Explorer | Fixed bug that caused Database Trees in server connections to not expand in the Object Explorer. |

### August 2022

- Release number: 1.39.0
- Release date: August 24, 2022

#### What's new in 1.39.0

| New item | Details |
| --- | --- |
| Deployment Wizard | Azure Data Studio now supports [!INCLUDE [sssql22-md](includes/sssql22-md.md)] in the Deployment Wizard for both local and container installation. |
| Object Explorer | Added Ledger icons and scripting support to Object Explorer for Ledger objects. |
| Dashboard | Added hexadecimal values to support color detection. |
| Query Plan Viewer | Added the ability to copy text from cells in the Properties Pane of a query plan. |
| Query Plan Viewer | Introduced a "find node" option in plan comparison to search for nodes in either the original or added plan. |
| Table Designer | Now supports the ability to add included columns to a nonclustered index, and the ability to create filtered indexes. |
| SQL Projects | Publish options were added to the Publish Dialog. |
| Query History Extension | Added double-click support for query history to either open the query or immediately execute it, based on user configuration. |

#### Bug fixes in 1.39.0

| New item | Details |
| --- | --- |
| Dashboard | Fixed an accessibility issue that prevented users from being able to access tooltip information using the keyboard. |
| Voiceover | Fixed a bug that caused voiceover errors across the Dashboard, SQL Projects, SQL Import Wizard, and SQL Migration extensions. |
| Schema Compare | Fixed a bug that caused the UI to jump back to the top of the options list after selecting/deselecting any option. |
| Schema Compare | Fixed a bug involving Schema Compare (.SCMP) file incompatibility with Database Project information causing errors when reading and using information stored in this file type. |
| Object Explorer | Fixed a bug that caused menu items in Object Explorer not to show up for non-English languages. |
| Table Designer | Fixed a bug that caused the History Table name not to be consistent with the current table name when working with System-Versioned Tables. |
| Table Designer | Fixed a bug in the Primary Key settings that caused the "Allow Nulls" option to be checked, but disabled, preventing users from changing this option. |
| Query Editor | Fixed a bug that prevented the SQLCMD in T-SQL from working correctly, giving false errors when running scripts in Azure Data Studio. |
| Query Editor | Fixed a bug that caused user-specified zoom settings to reset to default when selecting JSON values after query that returned JSON dataset was run. |
| SQL Projects | Fixed a bug that caused the "Generate Script" command to not work correctly when targeting a new Azure SQL Database. |
| Notebooks | Fixed a bug that caused pasted images to disappear from editor after going out of edit mode. |
| Notebooks | Fixed a bug that caused a console error message to appear after opening a markdown file. |
| Notebooks | Fixed a bug that prevented markdown cell toolbar shortcuts from working after creating a new split view cell. |
| Notebooks | Fixed a bug that caused text cells to be erroneously created in split view mode when the notebook default text edit mode was set to "Markdown". |

For a full list of bug fixes addressed for the August 2022 release, visit the [August 2022 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/87?closed=1).

### July 2022

- Release number: 1.38.0
- Release date: July 27, 2022

### What's new in 1.38.0

| New item | Details |
| --- | --- |
| VS Code merges to 1.62 | This release includes updates to VS Code from the three previous VS Code releases. Read [their release notes](https://code.visualstudio.com/updates/v1_62) to learn more. |
| Table Designer | New column added to Table Designer for easier access to additional actions specific to individual rows. |
| Query Plan Viewer | The Top Operations pane view now includes selectable links to operations in each of its rows to show the runtime statistics, which can be used to evaluate estimated and actual rows when analyzing a plan. |
| Query Plan Viewer | Improved UI on selected operation node in Execution Plan. |
| Query Plan Viewer | The keyboard command **CTRL + M** no longer executes queries. It now just enables or disables the actual execution plan creation when a query is executed. |
| Query Plan Viewer | Plan labels are now updated in the Properties window when plans are compared and the orientation is toggled from horizontal to vertical, and back. |
| Query Plan Viewer | Updates were made to the Command Palette. All execution plan commands are prefixed with "Execution Plan", so that they're easier to find and use. |
| Query Plan Viewer | A collapse/expand functionality is now available at the operator level to allow users to hide or display sections of the plan during analysis. |
| Query History | The Query History extension was refactored to be fully implemented in an extension. This makes the history view behave like all other extension views and also allows for searching and filtering in the view by selecting the view and typing in your search text. |

### Bug fixes in 1.38.0

| New item | Details |
| --- | --- |
| Table Designer | Error found in edit data tab when switching back to previously selected column when adding a new row. To fix this, editing the table is now disabled while new rows are being added and only reenabled afterwards. |
| Query Editor | Fixed coloring issues for new T-SQL functions in the Query Editor. |
| Query Plan Viewer | Fixed bug that caused custom zoom level spinner to allow values outside valid range. |
| Dashboard | Fixed issue that caused incorrect displaying of insight widgets on the dashboard. |
| Notebooks | Fixed issue where keyboard shortcuts and toolbar buttons weren't working when first creating a Split View markdown cell. |
| Notebooks | Fixed issue where cell languages weren't being set correctly when opening an ADS .NET Interactive notebook in VS Code. |
| Notebooks | Fixed issue where notebook was being opened as empty when exporting a SQL query as a notebook. |
| Notebooks | Disables install and uninstall buttons in Manage Packages dialog while a package is being installed or uninstalled. |
| Notebooks | Fixed issue where cell toolbar buttons weren't refreshing when converting cell type. |
| Notebooks | Fixed issue where notebook wasn't opening if a cell contains an unsupported output type. |
| Schema Compare | Fixed issue where views and stored procedures weren't correctly recognized by schema compare after applying changes. |

For a full list of bug fixes addressed for the July 2022 release, visit the [July 2022 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/90?closed=1).

### June 2022

- Release number: 1.37.0
- Release date: June 15, 2022

### What's new in 1.37.0

| New item | Details |
| --- | --- |
| Backup & Restore | Backup & Restore to URL is now available in preview for Azure SQL Managed Instances. |
| Table Designer | Added support for computed columns in Table Designer. |
| Table Designer | Can now specify where to add new columns and columns can now be rearranged by mouse dragging. |
| Table Designer | Table Designer is now supported in the SQL Database Projects extension for editing tables in the SQL project. |
| Query Plan Viewer | Plan comparison is now available and includes visual indicators in the Properties pane for easier identification of differences. |
| Query Plan Viewer | Added a toolbar button to toggle the display for actual execution plans. |
| Query Plan Viewer | Larger query plans will now display additional precision for operator cost. |
| MongoDB Extension for Azure Cosmos DB (Preview) | This extension introduces support for access to Mongo resources for Cosmos DB. |

### Bug fixes in 1.37.0

| New item | Details |
| --- | --- |
| Table Designer | Fixed issue that caused app to not prompt user to save before closing. |
| Table Designer | Fixed issue that returned empty data set upon attempting to edit the first cell of a new row. |
| Table Designer | Improved resize to fit experience when zooming in on user interface and tab behavior issues. |
| Query Plan Viewer | Fixed bug that caused custom zoom level spinner to allow values outside valid range. |
| Schema Compare | Fixed issue with indexes not being added correctly when updating project from database. |
| Notebooks | Fixed inconsistencies with notebook cell behavior and toolbars. |
| Notebooks | Fixed issues with keyboard navigation. |

For a full list of bug fixes addressed for the June 2022 release, visit the [June 2022 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/85?closed=1).

### May 2022 (hotfix)

- Release number: 1.36.2
- Release date: May 20, 2022

#### What's new in 1.36.2

| New item | Details |
| --- | --- |
| Power BI | Introduced support for Power BI Datamart connectivity. See [Announcing public preview of datamart in Power BI](https://powerbi.microsoft.com/blog/announcing-public-preview-of-datamart-in-power-bi). |

#### Bug fixes in 1.36.2

| New item | Details |
| --- | --- |
| Query Plan Viewer | Fixed issue with execution plan zoom and operator icons. |
| Query Plan Viewer | Updated parallelism icon direction. |

### April 2022 (hotfix)

- Release number: 1.36.1
- Release date: April 22, 2022

#### Bug fixes in 1.36.1

| New item | Details |
| --- | --- |
| Table Designer | Fix for timeout occurring when viewing table list |

### April 2022

- Release number: 1.36.0
- Release date: April 20, 2022

#### What's new in 1.36.0

| New item | Details |
| --- | --- |
| Table Designer | Added support for System Versioning, Memory Optimized, and Graph Tables. |
| Query Plan Viewer | Added support icons and additional support for searching within plans. Added additional telemetry to Execution Plans. Provided support on plan toolbar to enable or disable tooltips. Added support for saving .sql plan files on Azure Data Studio |
| SQL Projects | Introduced new SQL Project format based on an SDK-Style project file |
| Azure SQL Migration Extension | Announcing General Availability of the Azure SQL Migration Extension |
| .NET Interactive Notebooks extension | This extension provides additional multi-language support to Jupyter Notebooks. Reference [.NET Notebooks in Visual Studio Code](https://devblogs.microsoft.com/dotnet/net-interactive-with-sql-net-notebooks-in-visual-studio-code/)for an introduction to using SQL and .NET interactive |

#### Bug fixes in 1.36.0

| New item | Details |
| --- | --- |
| Table Designer | Added missing validation rules for primary key column specifications |
| Table Designer | Now able to add description to Primary Key, Foreign Key, and check constraints |
| Table Designer | Fixed bug that prevents the primary key checkbox from being unchecked for unsupported primary key types |
| Query Plan Viewer | Added option to turn off tooltip in execution plan |
| Query Plan Viewer | Fixed display and sizing issues |
| Query Plan Viewer | Fixed latency issues while switching tabs when execution plan is shown |
| Query Editor | Fixed performance issues in Query Editor |
| Notebooks | Fixed keyboard navigation issues |
| Notebooks | Fixed .NET Interactive log errors on startup |
| Notebooks | Fixed inconsistencies with notebook URI handling |

For a full list of bug fixes addressed for the April 2022 release, visit the [April 2022 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/84?closed=1).

### February 2022 (hotfix)

- Release number: 1.35.1
- Release date: March 17, 2022

#### Bug fixes in 1.35.1

| New item | Details |
| --- | --- |
| Query Editor | Geometry Data Type Returned as Unknown Charset in Results Grid |
| Query Editor | Excel number format |

### February 2022

- Release number: 1.35.0
- Release date: February 24, 2022

#### What's new in 1.35.0

| New item | Details |
| --- | --- |
| Table Designer | Added functionality for creation and management of tables for SQL Servers. Built using DacFx framework |
| Query Plan Viewer | Added functionality for users to view a graphic view of estimated and actual query plans without need for an extension |
| Azure Arc Extension | Updated the Data Controller deployment wizard and the SQL Managed Instance - Azure Arc deployment wizard to reflect the deployment experience in Azure portal |

#### Bug fixes in 1.35.0

| New item | Details |
| --- | --- |
| Azure Arc Extension | SQL Managed Instance-Azure Arc is now fixed for both indirect connectivity mode and direct connectivity mode |
| Notebooks | Support for keyboard navigation between cells to minimize mouse selecting |

For a full list of bug fixes addressed for the February 2022 release, visit the [February 2022 Release on GitHub](https://github.com/microsoft/azuredatastudio/milestone/83?closed=1).

### December 2021

- Release number: 1.34.0
- Release date: December 15, 2021

#### What's new in 1.34.0

| New item | Details |
| --- | --- |
| SQL Migration extension | Added 'Currently restoring backup file' in the migration progress details page of Azure SQL migration extension when backup files location is Azure Storage blob container |
| Notebooks | Added undo/redo support |
| SQL Database Projects extension | Support for project build with .NET 6 in SQL Database Projects extension |
| SQL Database Projects extension | Publish to container in SQL Database Projects extension |
| Extension update | [SQL Database Projects extension](extensions/sql-database-project-extension.md) |
| Extension update | Lang packs |
| Extension update | Azure SQL Migration |

#### Bug fixes in 1.34.0

| New item | Details |
| --- | --- |
| SQL Migration | Fix for multiple database migrations when using network share as backup files location in Azure SQL migration extension |
| SQL Migration | Fix for multiple database migrations when using blob storage containers as backup files location in Azure SQL migration extension |
| SQL Migration | Fix to prepopulate target database names in the migration wizard in Azure SQL migration extension |
| Grid | Fix to column sorting in grids where the presence of null values could lead to unexpected results |
| Notebooks | Fix for Python upgrades when two or more notebooks were open |

### October 2021

- Release number: 1.33.0
- Release date: October 27, 2021

#### What's new in 1.33.0

| New item | Details |
| --- | --- |
| Notebooks | Added Notebook Views support |
| Notebooks | Added split cell support |
| Notebooks | Added keyboard shortcuts for Markdown Toolbar cells |
| Notebooks | Large performance improvement for large notebooks<br />- Ctrl/Cmd + B = Bold Text<br />- Ctrl/Cmd + I = Italicize Text<br />- Ctrl/Cmd + U = Underline Text<br />- Ctrl/Cmd + Shift + K = Add Code Block<br />- Ctrl/Cmd + Shift + H = Highlight Text |
| Notebooks | Added Book improvements<br />- Add a new section<br />- Drag and Drop |
| Extension update | [Azure Monitor Logs extension for Azure Data Studio (Preview)](extensions/azure-monitor-logs-extension.md) |
| Extension update | [Schema Compare extension](extensions/schema-compare-extension.md) |
| Extension update | [SQL Database Projects extension](extensions/sql-database-project-extension.md) |
| Extension update | [Machine Learning extension for Azure Data Studio (Preview)](extensions/machine-learning-extension.md) |
| Extension update | [SQL Server Profiler extension (Preview)](extensions/sql-server-profiler-extension.md) |
| Extension update | [SQL Server Profiler extension (Preview)](extensions/sql-server-profiler-extension.md) |
| Extension update | [Kusto (KQL) extension for Azure Data Studio (Preview)](extensions/kusto-extension.md) |
| Extension update | [SQL Server dacpac extension](extensions/sql-server-dacpac-extension.md) |
| Extension update | Lang packs |
| Extension update | Azure SQL Migration |
| Extension update | CMS |
| Extension update | Kusto |

#### Bug fixes in 1.33.0

| New item | Details |
| --- | --- |
| Notebook | Fixed Notebook linking |
| Notebook | Fixed horizontal scrollbar (when word wrap is off in MD Splitview / MD mode) in Notebooks |
| Notebook | Fixed vertical scrollbar for MD Splitview in Notebooks |

For a full list of bug fixes addressed for the August 2021 release, visit the [bugs and issues list on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+milestone%3A%22October+2021+Release%22+is%3Aclosed).

### August 2021

- Release number: 1.32.0
- Release date: August 18, 2021

#### What's new in 1.32.0

| New item | Details |
| --- | --- |
| Notebooks | Large performance improvement for large notebooks |
| Extension (new) | [Azure Monitor Logs extension for Azure Data Studio (Preview)](extensions/azure-monitor-logs-extension.md) |
| Extension update | [Schema Compare extension](extensions/schema-compare-extension.md) |
| Extension update | [SQL Database Projects extension](extensions/sql-database-project-extension.md) |
| Extension update | [Machine Learning extension for Azure Data Studio (Preview)](extensions/machine-learning-extension.md) |
| Extension update | [Azure Arc extension for Azure Data Studio](extensions/azure-arc-extension.md) |
| Extension update | Lang packs |

#### Bug fixes in 1.32.0

| New item | Details |
| --- | --- |
| Database Projects | Fixed Seeing "Project already opened" message for every project I open or create |
| Schema Compare | Fixed Schema compare subsequent results after once aren't loading in view |
| Lang packs | Fixed Localization for previously untranslated extensions. |
| Machine Learning | Fixed Machine Learning - View models dialog is broken |

For a full list of bug fixes addressed for the August 2021 release, visit the [bugs and issues list on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+milestone%3A%22August+2021+Release%22+is%3Aclosed).

### July Hotfix 2021

- Release number: 1.31.1
- Release date: July 29, 2021

#### Bug fixes in 1.31.1

| New item | Details |
| --- | --- |
| Connections | Fixed Database connection toolbar missing for sql scripts |
| Connections | Fixed Connection dropped / isn't maintained when saving / opening scripts |
| Connections | Script file opened from command line doesn't allow DB connection |

For a full list of bug fixes addressed for the July Hotfix 2021 release, visit the [bugs and issues list on GitHub](https://github.com/microsoft/azuredatastudio/milestone/75).

### July 2021

- Release number: 1.31.0
- Release date: July 21, 2021

#### What's new in 1.31.0

| New item | Details |
| --- | --- |
| Notebooks | WYSIWYG link improvements |
| Extension update | [Schema Compare extension](extensions/schema-compare-extension.md) |
| Extension update | [SQL Database Projects extension](extensions/sql-database-project-extension.md) |

#### Bug fixes in 1.31.0

| New item | Details |
| --- | --- |
| Import Wizard | Fixed Import extension next button doesn't work in July release |
| Schema Compare | Fixed issue that Schema compare Select Source target dialog OK button not enabled |
| Notebooks | Fixed Export Notebook as SQL file has no query editor toolbar |
| SQL Server Big Data Clusters | Fixed Can't connect to BDC Clusters |
| Accessibility bug fixes | |

For a full list of bug fixes addressed for the July 2021 release, visit the [bugs and issues list on GitHub](https://github.com/microsoft/azuredatastudio/milestone/75).

### June 2021

- Release number: 1.30.0
- Release date: June 17, 2021

#### What's new in 1.30.0

| New item | Details |
| --- | --- |
| Results Grid | Added filtering/sorting feature for query result grid in query editor and notebook, the feature can be invoked from the column headers. note that this feature is only available when you enable the preview features. |
| Results Grid | Added a status bar item to show summary of the selected cells if there are multiple numeric values |
| Notebooks | Added new book icon |
| Notebooks | Notebook URI Handler File Support |
| Python | Updated Python to 3.8.10 |

#### Bug fixes in 1.30.0

| New item | Details |
| --- | --- |
| Notebooks | Fixed WYWIWYG Table cell adding new line in table cell |
| Notebooks | Fixed issue that Kusto notebook doesn't change kernels properly |

For a full list of bug fixes addressed for the May 2021 release, visit the [bugs and issues list on GitHub](https://github.com/microsoft/azuredatastudio/milestone/73?closed=1).

### May 2021

- Release number: 1.29.0
- Release date: May 19, 2021

#### What's new in 1.29.0

| New item | Details |
| --- | --- |
| Notebooks | Added run with parameters action. For more information, see [Create a parameterized notebook by using the Run with Parameters action](notebooks/run-with-parameters.md). |

#### Bug fixes in 1.29.0

| New item | Details |
| --- | --- |
| Database | Fixed an issue with the title not changing when the database connection changes. |
| Extensions | Fixed an issue with no longer prompting the user to install 3rd-party extensions. |
| General Azure Data Studio | Fixed an issue with the account button in the sidebar getting stuck loading. |
| General Azure Data Studio | Fixed an issue with the *Run With Parameters* silently failing if the parameters cell is empty or invalid. |
| General Azure Data Studio | Fixed an issue with the *Run With Parameters* not handling multiple parameters on the same line. |
| General Azure Data Studio | Fixed an issue with being unable to connect to Azure. |
| General Azure Data Studio | Fixed an issue with the wrong line number showing up in the output. |
| General Azure Data Studio | Fixed an issue when receiving an error when connecting to an Azure server in the Azure viewlet. |
| General Azure Data Studio | Fixed an issue with the loading spinner not being animated. |
| General Azure Data Studio | Fixed an issue with the links inserted in the split view/MD view not being inserted as a list item. |
| General Azure Data Studio | Fixed an issue with the *Issue Reporter* being blank. |
| Extensions | Fixed an issue with the extensions view having many filter options that aren't applicable to Azure Data Studio. |
| General Azure Data Studio | Fixed an issue with getting the Azure subscriptions API failing across Azure Data Studio. |
| General Azure Data Studio | Fixed an issue with the wrong event prefix. |
| General Azure Data Studio | Fixed an issue with converting the default tables from Excel, Word, and OneNote into markdown tables. |
| Notebooks | Fixed an issue with selecting notebooks from the notebooks viewlet recentering the viewlet vertically. |
| Notebooks | Fixed an issue with not connecting to SQL Server from SQL Notebook. |
| Notebooks | Fixed an issue with the notebook icons being sized incorrectly. |
| PowerShell | Fixed an issue with using the Cloud Shell (PowerShell). |
| SQL Database Project | Fixed an issue with showing an unnecessary horizontal scrollbar in the *create project from database* dialog SQL Database Project dashboard update. |

For a full list of bug fixes addressed for the May 2021 release, visit the [bugs and issues list on GitHub](https://github.com/microsoft/azuredatastudio/issues?page=3&q=is%3Aissue+is%3Aclosed+milestone%3A%22May+2021+Release%22).

### April 2021

April 15, 2021 / version: 1.28.0

#### What's new in 1.28.0

| New item | Details |
| --- | --- |
| Extension update | [Kusto (KQL) extension for Azure Data Studio (Preview)](extensions/kusto-extension.md) |
| Extension update | [Machine Learning extension for Azure Data Studio (Preview)](extensions/machine-learning-extension.md) |
| Extension update | [Schema Compare extension](extensions/schema-compare-extension.md) |
| Extension update | [SQL Database Projects extension](extensions/sql-database-project-extension.md) |
| Notebook features | Added *Add Notebook* and *Remove Notebook commands* |

#### Bug fixes in 1.28.0

For the list of the bug fixes addressed for the April 2021 release, visit the [bugs and issues list on GitHub](https://github.com/microsoft/azuredatastudio/issues?page=1&q=is%3Aissue+is%3Aclosed+milestone%3A%22April+2021+Release%22).

### March 2021

March 17, 2021 / version: 1.27.0

| Change | Details |
| --- | --- |
| Bug Fixes | For a complete list of fixes, see [Bugs and issues on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+is%3Aclosed+milestone%3A%22March+2021+Release%22). |
| Extension(s) update | [SQL Server dacpac extension](extensions/sql-server-dacpac-extension.md)<br />[SQL Database Projects extension](extensions/sql-database-project-extension.md) |
| New Notebook features | Added create book dialog |

### February 2021

February 18, 2021 / version: 1.26.0

| Change | Details |
| --- | --- |
| Bug Fixes | For a complete list of fixes, see [Bugs and issues on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+milestone%3A%22February+2021+Release%22+is%3Aclosed). |
| Extension(s) update | [SQL Server dacpac extension](extensions/sql-server-dacpac-extension.md)<br />[Kusto (KQL) extension for Azure Data Studio (Preview)](extensions/kusto-extension.md)<br />[Machine Learning extension for Azure Data Studio (Preview)](extensions/machine-learning-extension.md)<br />[SQL Server Profiler extension (Preview)](extensions/sql-server-profiler-extension.md)<br />[Schema Compare extension](extensions/schema-compare-extension.md)<br />[SQL Database Projects extension](extensions/sql-database-project-extension.md) |
| New Azure Arc features | Multiple data controllers now supported<br />New connection dialog options like the *kube config file*<br />Postgres dashboard enhancements |
| New Notebook features | Improved Jupyter server start-up time by 50% on Windows<br />Added support to edit Jupyter Books through right-click<br />Added URI notebook parameterization support and [added notebook parameterization documentation](notebooks/parameterize-papermill.md) |

### December 2020 (hotfix)

February 10, 2021 / version: 1.25.3

| Change | Details |
| --- | --- |
| Fix bug [#13899](https://github.com/microsoft/azuredatastudio/issues/13899) | Scrolling to the appropriate cross-reference links in Notebooks |
| Upgrade Electron to incorporate important bug fixes | N/A |

### December 2020

December 9, 2020 / version: 1.25.0

| Change | Details |
| --- | --- |
| Bug Fixes | For a complete list of fixes, see [Bugs and issues on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+is%3Aclosed+milestone%3A%22December+2020+Release%22). |
| Database Projects extension update | Added workspaces and improved sidebar |

### November 2020

November 12, 2020 / version: 1.24.0

| Change | Details |
| --- | --- |
| Bug Fixes | For a complete list of fixes, see [Bugs and issues on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+milestone%3A%22November+2020+Release%22+is%3Aclosed). |
| Connection dialog | Added new browse tab for connection dialog. |
| Extension(s) update | Released update to Postgres extension. |
| New notebook features | Added new features to SQL to notebook support.<br />Added new features to Notebook parameterization support.<br />Added new features to results streaming for SQL Notebooks. |
| Python installation | PROSE package has been removed from default Python installation. |

### Known issues (1.24.0)

| New item | Details | Workaround |
| --- | --- | --- |
| Azure Arc extension | [Known Issue:](https://github.com/microsoft/azuredatastudio/issues/13319) The "Script to Notebook" button for Arc MIAA & PG deployments doesn't do field validation before scripting the notebook. This means that if users enter the password wrong in the password confirm inputs then they might end up with a notebook that has the wrong value for the password. | The "Deploy" button works as expected though so users should use that instead. |
| Object Explorer | Releases of Azure Data Studio before 1.24.0 have a breaking change in object explorer because of the engine's changes related to [Azure Synapse Analytics serverless SQL pool](/azure/synapse-analytics/sql/on-demand-workspace-overview). | To continue utilizing object explorer in Azure Data Studio with Azure Synapse Analytics serverless SQL pool, you need to use Azure Data Studio 1.24.0 or later. |

You can reference [Azure Data Studio feedback](https://github.com/microsoft/azuredatastudio) for other known issues and to provide feedback to the product team.

### October 2020

October 14, 2020 / version: 1.23.0

| Change | Details |
| --- | --- |
| Azure SQL Edge | Support for Azure SQL Edge objects. |
| Bug Fixes | For a complete list of fixes, see [Bugs and issues on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is:issue+milestone:%22October+2020+Release%22+is:closed). |
| Databases | Support for same database reference. |
| Extension updates | [Azure Arc extension for Azure Data Studio](extensions/azure-arc-extension.md)<br />[azdata](/sql/azdata/install/deploy-install-azdata)<br />[Machine Learning extension for Azure Data Studio (Preview)](extensions/machine-learning-extension.md)<br />[Kusto (KQL) extension for Azure Data Studio (Preview)](extensions/kusto-extension.md)<br />[Schema Compare extension](extensions/schema-compare-extension.md)<br />SQL Assessment<br />[SQL Database Projects extension](extensions/sql-database-project-extension.md)<br />[SQL Server Import extension](extensions/sql-server-import-extension.md) |
| New deployment features | Added Azure SQL DB and VM deployments. |
| PowerShell | Added PowerShell kernel results streaming support. |

### September 2020 (hotfix)

September 30, 2020 / version: 1.22.1

| Change | Details |
| --- | --- |
| Resolved bugs and issues | For a complete list of fixes, see [Bugs and issues on GitHub](https://github.com/microsoft/azuredatastudio/releases/tag/1.22.1). |

### September 2020

September 22, 2020 / version: 1.22.0

| Change | Details |
| --- | --- |
| New notebook features | - Supports brand new text cell editing experience based on rich text formatting and seamless conversion to markdown, also known as WYSIWYG toolbar (What You See Is What You Get)<br />- Supports Kusto kernel<br />- Supports pinning of notebooks<br />- Added support for new version of Jupyter Books<br />- Improved Jupyter Shortcuts<br />- Introduced perf loading improvements |
| SQL Database Projects extension | The SQL Database Projects extension brings project-based database development to Azure Data Studio. In this preview release, SQL projects can be created and published from Azure Data Studio. |
| Kusto (KQL) extension | Brings native Kusto experiences in Azure Data Studio for data exploration and data analytics against massive amount of real-time streaming data stored in Azure Data Explorer. This preview release supports connecting and browsing Azure Data Explorer clusters, writing KQL queries and authoring notebooks with Kusto kernel. |
| Azure Arc extension | Users can try out Azure Arc public preview through Azure Data Studio. This includes:<br />- Deploy data controller<br />- Deploy Postgres<br />- Deploy SQL Managed Instance for Azure Arc<br />- Connect to data controller<br />- Access data service dashboards<br />- Azure Arc Jupyter Book |
| Deployment options | - Azure SQL Database Edge<br />(Edge requires Azure SQL Edge Deployment Extension) |
| SQL Server Import extension GA | Announcing the GA of the SQL Server Import extension, features no longer in preview. This extension facilitates importing csv/txt files. Learn more about the extension in [this article](extensions/sql-server-import-extension.md). |
| Resolved bugs and issues | For a complete list of fixes see [Bugs and issues, on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+milestone%3A%22September+2020+Release%22+is%3Aclosed). |

### August 2020

August 12, 2020 / version: 1.21.0

| Change | Details |
| :--- | :--- |
| New notebook features | - Move cell locations<br />- Convert cells to Text Cell or Code cell |
| Jupyter Books picker | Users can now choose Jupyter Books from GitHub releases and open seamlessly in Azure Data Studio |
| Search added to Notebooks Viewlet | Users can easily search through content across their notebooks and Jupyter Books |
| Resolved bugs and issues | For a complete list of fixes see [Bugs and issues, on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+milestone%3A%22August+2020+Release%22+is%3Aclosed). |

### July 2020 (hotfix)

July 17, 2020 / version: 1.20.1

| Change | Details |
| :--- | :--- |
| Fix bug #11372 Object Explorer drag-and-drop table incorrectly wraps table names | [#11372](https://github.com/microsoft/azuredatastudio/issues/11372) |
| Fix bug #11356 Dark theme is now the default theme | [#11356](https://github.com/microsoft/azuredatastudio/issues/11356) |

### Known Issue

- Some users have reported connection errors from the new Microsoft.Data.SqlClient v2.0.0 included in this release. Users have found [following these instructions](https://github.com/microsoft/azuredatastudio/issues/11367#issuecomment-659614111) to successfully connect

### July 2020

July 15, 2020 / version: 1.20.0

| Change | Details |
| :--- | :--- |
| Added new Feature Tour | From welcome page and command palette, users can now launch a feature tour to get a walkthrough of commonly used features including Connections Viewlet, Notebooks viewlet, and Extensions Marketplace |
| New notebook features | - Header support in Markdown Toolbar<br />- Side-by-side Markdown Preview in Text Cells |
| Drag and Drop Columns and Tables in Query Editor | Users can now directly drag and drop columns and tables from connections viewlet to query editor |
| Added Azure Account icon to Activity Bar | Users can now easily see where to sign in to Azure |
| Resolved bugs and issues | For a complete list of fixes see [Bugs and issues, on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+milestone%3A%22July+2020+Release%22+is%3Aclosed). |

### June 2020

June 15, 2020 / version: 1.19.0

| Change | Details |
| :--- | :--- |
| Added Azure Data Studio to Azure portal Integration | Users can now directly launch to Azure portal from an Azure SQL Database connection, Azure Postgres, and more. |
| New notebook features | - New Notebook toolbar<br />- New Edit Cell toolbar<br />- Python dependencies wizard UX updates<br />- Improved spacing across notebooks |
| Announcing SQL Assessment API extension | This extension adds SQL Server best-practice assessment in Azure Data Studio. It exposes SQL Assessment API, which was previously available for use in PowerShell SqlServer module and SMO only, to let you evaluate your SQL Server instances and receive for them recommendations by SQL Server Team. Learn more about SQL Assessment API and what it's capable of [in this article.](/sql/tools/sql-assessment-api/sql-assessment-api-overview) |
| [Machine Learning extension for Azure Data Studio (Preview)](extensions/machine-learning-extension.md) | Now supports Azure SQL Managed Instance. |
| Data Virtualization extension improvements | Now supports MongoDB and Teradata |
| Postgres extension bug fixes | Fixed Microsoft Entra multifactor authentication |
| Resolved bugs and issues | For a complete list of fixes see [Bugs and issues, on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+milestone%3A%22June+2020+Release%22+is%3Aclosed). |

### May 2020 (hotfix)

May 27, 2020 / version: 1.18.1

| Change | Details |
| :--- | :--- |
| Fix bug #10538 "Run Current Query" key binding no longer behaving as expected | [#10538](https://github.com/microsoft/azuredatastudio/issues/10538) |
| Fix bug #10537 Unable to open new or existing sql files on v1.18 | [#10537](https://github.com/microsoft/azuredatastudio/issues/10537) |

### May 2020

May 20, 2020 / version: 1.18.0

| Change | Details |
| :--- | :--- |
| Announcing Redgate SQL Prompt extension | This extension lets you manage formatting styles directly within Azure Data Studio, so you can create and edit your styles without leaving the IDE. |
| Announcing Machine Learning Extension | This extension enables you to:<br />- Manage Python and R packages with SQL Server machine learning services with Azure Data Studio.<br />- Use ONNX model to make predictions in Azure SQL Edge.<br />- View ONNX models in an Azure SQL Edge database.<br />- Import ONNX models from a file or Azure Machine Learning into Azure SQL Edge database.<br />- Create a notebook to run experiments. |
| New notebook features | - Added new Python Dependencies Wizard to make it easier to install Python dependencies<br />- Added underline support for Markdown Toolbar |
| Parameterization for Always Encrypted | Allows you to run queries that insert, update, or filter by encrypted database columns. |
| Resolved bugs and issues | For a complete list of fixes see [Bugs and issues, on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+milestone%3A%22May+2020+Release%22+is%3Aclosed). |

### April 2020 (hotfix)

April 30, 2020 / version: 1.17.1

| Change | Details |
| :--- | :--- |
| Fix bug #10197 Can't connect via MFA | [#10197](https://github.com/microsoft/azuredatastudio/issues/10197) |

### April 2020

April 27, 2020 / version: 1.17.0

| Change | Details |
| :--- | :--- |
| Improved welcome page | UI update on the welcome page to make it easier to see common actions and highlighting extensions. |
| New notebook features | - Added Markdown toolbar when editing text cells to help write with Markdown<br />- Revamped Jupyter Books viewlet to become a Notebooks viewlet where you can manage Jupyter Books and notebooks together<br />- Added support for persisting charts when saving a notebook<br />- Added support for KQL magic in Python notebooks |
| Improved dashboards | Dashboards throughout Azure Data Studio have been updated with latest design patterns, including an actions toolbar. This also applies to many extensions. |
| Added Cloud Shell integration in the Azure view. | |
| Support for Always Encrypted and Always Encrypted with secure enclaves. | |
| Resolved bugs and issues | For a complete list of fixes see [Bugs and issues, on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+is%3Aclosed+milestone%3A%22April+2020+Release%22). |

### March 2020

March 18, 2020 / version: 1.16.0

| Change | Details |
| :--- | :--- |
| Added charting support in SQL Notebooks | When running a SQL query in a code cell, users can now create and save charts. |
| Added Create Jupyter Book experience | Users can now create their own Jupyter Books using a notebook. |
| Added Microsoft Entra ID support for Postgres extension | |
| Fixed many accessibility bugs | [List of accessibility bugs](https://github.com/microsoft/azuredatastudio/issues?page=1&q=is%3Aissue+is%3Aclosed+milestone%3A%22S360+-+Accessibility%22+label%3AA11y_AzureDataStudio) |
| VS Code merges to 1.42 | This release includes updates to VS Code from the three previous VS Code releases. [Read their release notes](https://code.visualstudio.com/updates/v1_42) to learn more. |
| Resolved bugs and issues | For a complete list of fixes see [Bugs and issues, on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+milestone%3A%22March+2020%22+is%3Aclosed). |

### February (hotfix)

February 19, 2020 / version: 1.15.1

| Change | Details |
| :--- | :--- |
| Fix bug #9149 Show active connections | [#9149](https://github.com/microsoft/azuredatastudio/issues/9149) |
| Fix bug #9061 Edit Data grid doesn't properly resize when showing or hiding SQL Pane | [#9061](https://github.com/microsoft/azuredatastudio/issues/9061) |

### February 2020

February 13, 2020 / version: 1.15.0

| Change | Details |
| :--- | :--- |
| New Azure Sign-in improvement | Added improved Azure Sign-in experience, including removal of copy/paste of device code to make a more seamless connected experience. |
| Find in Notebook support | Users can now use Ctrl+F in a notebook. Find in Notebook support searches line by line through both code and text cells. |
| VS Code merges from 1.38 to 1.42 | This release includes updates to VS Code from the three previous VS Code releases. [Read their release notes](https://code.visualstudio.com/updates/v1_42) to learn more. |
| Fix for the ["white/blank screen"](https://github.com/microsoft/azuredatastudio/issues/8775) issue reported by many users. | |
| Resolved bugs and issues | For a complete list of fixes see [Bugs and issues, on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+is%3Aclosed+milestone%3A%22February+2020%22). |

### Known Issue

- Users on macOS Catalina need to right-click Azure Data Studio and then select open.

### December 2019 (hotfix)

December 26, 2019 / version: 1.14.1

| Change | Details |
| :--- | :--- |
| Fix bug #8747 OE Expansion fails | [#8747](https://github.com/microsoft/azuredatastudio/issues/8747) |

### December 2019

December 19, 2019 / version: 1.14.0

| Change | Details |
| :--- | :--- |
| Changed attach to connection dropdown list in Notebooks to only list the currently active connection | [#8129](https://github.com/microsoft/azuredatastudio/issues/8129) |
| Added bigdatacluster.ignoreSslVerification setting to allow ignoring TLS/SSL verification errors when connecting to a BDC | [#8582](https://github.com/microsoft/azuredatastudio/pull/8582) |
| Allow changing default language flavor for offline query editors | [#8419](https://github.com/microsoft/azuredatastudio/pull/8419) |
| GA status for Big Data Cluster/SQL 2019 features | [#8269](https://github.com/microsoft/azuredatastudio/issues/8269) |
| Resolved bugs and issues | For a complete list of fixes see [Bugs and issues, on GitHub](https://github.com/microsoft/azuredatastudio/milestone/44?closed=1). |

### November 2019 (hotfix)

November 15, 2019 / version: 1.13.1

| Change | Details |
| :--- | :--- |
| Fix bug #8210 Copy/Paste results are out of order | |

### November 2019

November 4, 2019 / version: 1.13.0

| Change | Details |
| :--- | :--- |
| New SQL Server 2019 support | - Deploy SQL Server 2019 Big Data Cluster with BDC Deploy wizard<br />- Manage cluster health with controller dashboard<br />- Manage HDFS access control lists using Security ACLs Dialog<br />- Add mounts using HDFS Tiering Dialog<br />- Troubleshoot using built-in Jupyter Book, SQL Server 2019 guide<br />- Renamed to SQL vNext extension Data virtualization extension<br />- Added Teradata and Mongo support in External Table Wizard |
| New notebook features | - Announcing PowerShell notebooks<br />- Announcing collapsible code cells<br />- Perf improvements in Notebooks<br />- View the full list of improvements [on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+milestone%3A%22November+2019+Release%22+is%3Aclosed+label%3A%22Area+-+Notebooks%22) |
| Announcing Jupyter Books | Jupyter Books are a collection of notebooks and markdown files organized in a table of contents. |
| New SQL Server Deploy wizard | Now includes support for deploying:<br />- SQL Server 2019 on Windows<br />- SQL Server 2017 on Windows<br />- SQL Server 2019 in Linux containers<br />- SQL Server 2017 in Linux containers |
| Announcing GA of Schema Compare extension | - SQLCMD mode<br />- Localization support<br />- Accessibility fixes<br />- Security bugs |
| Announcing GA of SQL Server Dacpac extension | - Localization support<br />- Accessibility fixes<br />- Security bugs |
| Announcing Visual Studio IntelliCode extension | Visual Studio IntelliCode now supports SQL, which allows for smarter suggestions of reserved keywords. |
| Resolved bugs and issues | For a complete list of fixes see [Bugs and issues, on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+milestone%3A%22November+2019+Release%22+is%3Aclosed). |

### October 2019 (hotfix 2)

October 11, 2019 / version: 1.12.2

| Change | Details |
| :--- | :--- |
| Disable automatically starting the EH in inspect mode | |

### October 2019 (hotfix)

October 8, 2019 / version: 1.12.1

| Change | Details |
| :--- | :--- |
| Fixed issue for quotes and backslashes in Notebooks to escape correctly. | |

### October 2019

October 2, 2019 / version: 1.12.0

| Change | Details |
| :--- | :--- |
| Release of Query History extension | The SQL History extension saves all past queries executed in an Azure Data Studio session and lists them in execution order. Users can see open the query, execute the query, delete the query, pause query history, or delete all query history entries. |
| New Copy/Paste Results | We have added more ways to copy/paste results from the results grid. |
| Update to PowerShell extension | |
| Resolved bugs and issues | For a complete list of fixes see [Bugs and issues, on GitHub](https://github.com/microsoft/azuredatastudio/milestone/42?closed=1). |

### Known issues

- Notebooks
  - [7080](https://github.com/microsoft/azuredatastudio/issues/7080) Rare Case when Notebook is Serialized Incorrectly

### September 2019

September 10, 2019 / version: 1.11.0

| Change | Details |
| :--- | :--- |
| Enable SQLCMD Mode | Query editor now supports toggling of SQLCMD mode to write and edit queries as SQLCMD scripts |
| Community Extension: Query Editor Boost | Query Editor Boost is an open-source extension focused on enhancing the Azure Data Studio query editor for users who are frequently writing queries.<br />- Save the current query as a snippet<br />- Switch databases using Ctrl+U<br />- New Query from template<br />- View the full list of improvements [on GitHub](https://github.com/dzsquared/query-editor-boost). |
| Notebook Improvements | - Performance improvements for supporting larger notebook files<br />- View the full list of improvements [on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+milestone%3A%22September+2019+Release%22+label%3A%22Area%3A+Notebooks%22+is%3Aclosed). |
| Visual Studio Code August Release Merge 1.38 | For the latest improvements, see [August 2019 (version 1.38)](https://code.visualstudio.com/updates/v1_38). |
| Resolved bugs and issues | For a complete list of fixes see [Bugs and issues, on GitHub](https://github.com/microsoft/azuredatastudio/milestone/39?closed=1). |

### Known issues

- Notebooks
  - [7080](https://github.com/microsoft/azuredatastudio/issues/7080) Rare Case when Notebook is Serialized Incorrectly

### August 2019

August 15, 2019 / version: 1.10.0

| Change | Details |
| :--- | :--- |
| Release of SandDance 1.3.1 extension | - Smart chart detection<br />- 3D Visualizations<br />- Data filtering |
| Notebook Improvements | - Add code or text cell in-line<br />- Added ability to right-click SQL results grid to save result as CSV, JSON, etc.<br />- Improvement to notebook loading performance for loading JSON faster<br />- View the full list of improvements [on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+label%3A%22Area%3A+Notebooks%22+milestone%3A%22August+2019+Release%22+is%3Aclosed). |
| SQL Server 2019 Support | This release includes support for extra SQL Server 2019 Big Data Cluster features including:<br />- Reduced time taken to load table and column information on the object-mapping page.<br />- Fixed a bug with loading existing database scoped credentials on the connection details page.<br />- Increased default sample size used for PROSE parsing. |
| Dacpac extension now supports Microsoft Entra ID |
| Visual Studio Code July Release Merge 1.37 | For the improvements, see [July 2019 (version 1.37)](https://code.visualstudio.com/updates/v1_37). |
| Resolved bugs and issues | For a complete list of fixes see [Bugs and issues, on GitHub](https://github.com/microsoft/azuredatastudio/milestone/39?closed=1). |

### July 2019

July 11, 2019 / version: 1.9.0

| Change | Details |
| :--- | :--- |
| Release of SentryOne Plan Explorer extension | Our valued Microsoft partner, SentryOne, will be shipping their [SentryOne Plan Explorer extension for Azure Data Studio](https://www.solarwinds.com/sql-sentry).<br />This is a free extension, which provides enhanced plan diagrams for queries run in Azure Data Studio, with optimized layout algorithms and intuitive color-coding to help quickly identify the most expensive operators affecting query performance. For more information about the extension, see [SentryOne Plan Explorer Extension for Azure Data Studio](https://sqlperformance.com/2019/08/sentryone/plan-explorer-extension-azure-data-studio). |
| New Features coming to Schema Compare | - Schema Compare File Support (.SCMP)<br />- Cancel Schema Compare Support<br />- Complete changes can be found [on GitHub](https://github.com/microsoft/azuredatastudio/issues?utf8=%E2%9C%93&q=is%3Aissue+milestone%3A%22July+2019+Release%22+label%3A%22Area%3A+Schema+Compare%22+is%3Aclosed+). |
| Notebook Improvements | - Plotly Python Support<br />- Open Notebook from Browser<br />- Python Package Management Dialog<br />- Performance and Markdown Enhancements<br />- Keyboard Shortcuts Update<br />- Bug Fixes and Minor Features can be found [on GitHub](https://github.com/microsoft/azuredatastudio/issues?utf8=%E2%9C%93&q=is%3Aissue+milestone%3A%22July+2019+Release%22+is%3Aclosed+label%3A%22Area%3A+Notebooks%22+). |
| SQL Server 2019 Support | This release includes support for extra SQL Server 2019 Big Data Cluster features including:<br />- Service Endpoints table within the Management Dashboard that lists all key services in the cluster.<br />- Cluster Status Notebook shows how you can query & troubleshoot cluster status across all services and pods. |
| Updated Language Packs Available | There are now 10 language packs available in the Extension Manager marketplace. Simply, search for the specific language using the extension marketplace and install. Once you install the selected language, Azure Data Studio prompts you to restart with the new language. |
| SQL Server Profiler Update | The SQL Server Profile extension has been updated to include new features including:<br />- Filtering by Database Name<br />- Copy & Paste Support<br />- Save/Load Filter<br />A full list of improvements for SQL Server Profiler Extension can be found [on GitHub](https://github.com/microsoft/azuredatastudio/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aclosed+milestone%3A%22July+2019+Release%22+label%3A%22Area%3A+SQL+Profiler%22+). |
| Visual Studio Code May Release Merge 1.35 | For the latest improvements, see [May 2019 (version 1.35)](https://code.visualstudio.com/updates/v1_35). |
| Resolved bugs and issues | In previous releases of Azure Data Studio, if a user database was selected when connecting from the Connection dialog, the resulting Object Explorer entry was scoped entirely to that single database. Beginning in this release, that behavior is being changed so that server level properties are also shown in the object explorer.<br />For a complete list of fixes see [Bugs and issues, on GitHub](https://github.com/microsoft/azuredatastudio/milestone/35?closed=1). |

### June 2019

June 6, 2019 / version: 1.8.0

| Change | Details |
| :--- | :--- |
| Release of Central Management Servers (CMS) extension | Central Management Servers store a list of instances of SQL Server that is organized into one or more central management server groups. Users can connect to their own existing CMS servers and manage their servers like adding and removing servers. For more information, see [Administer multiple servers using Central Management Servers](/sql/relational-databases/administer-multiple-servers-using-central-management-servers). |
| Release of Database Administration Tool Extensions for Windows | This extension launches two of the most used experiences in SQL Server Management Studio from Azure Data Studio. Users can right-click on many different objects (such as Databases, Tables, Columns, Views, and more) and select Properties to view the SSMS Properties Dialog for that object. In addition, users can right-click on a database and select Generate Scripts to launch the well-known SSMS Generate Scripts Wizard. |
| Schema Compare Improvements | - Added Exclude/Include Options<br />- Generate Script opens script after being generated<br />- Removed double scroll bars<br />- Formatting and layout improvements<br />- Complete changes can be found [on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+milestone%3A%22June+2019+Release%22+label%3A%22Area%3A+Schema+Compare%22+is%3Aclosed). |
| Moved Messages section to own tab | When users ran SQL queries, results and messages were on stacked panels. Now they are in separate tabs in one panel like in SSMS. |
| SQL Notebook Improvements | - Users can now choose to use their own Python 3 or Anaconda installs in notebooks<br />- Multiple Stabilities + fit/finish fixes<br />- View the full list of improvements [on GitHub](https://github.com/microsoft/azuredatastudio/issues?q=is%3Aissue+milestone%3A%22June+2019+Release%22+is%3Aclosed+label%3A%22Area%3A+Notebooks%22). |
| Visual Studio Code April Release Merge 1.34 | For the latest improvements, see [April 2019 (version 1.34)](https://code.visualstudio.com/updates/v1_34). |
| Resolved bugs and issues. | See [Bugs and issues, on GitHub](https://github.com/microsoft/azuredatastudio/milestone/32?closed=1). |

### Known issues

- Database Administration Tool Extensions for Windows
  - Can't launch properties from disconnected server node
  - Can't launch properties for Azure servers
  - Not all objects have property dialogs
  - Dialogs take a long time to start up
  - Errors launching servers with some types of connections (such as Microsoft Entra ID)
- Notebooks
  - [5838](https://github.com/microsoft/azuredatastudio/issues/5838) Allow users to use system Python for Notebooks
- Schema Compare
  - [5804](https://github.com/microsoft/azuredatastudio/issues/5804) Schema Compare tasks show default cancel context menu, which does nothing

### May 2019

May 8, 2019 / version: 1.7.0

| Change | Details |
| :--- | :--- |
| Release of Schema Compare extension | Schema Compare is a well-known feature in SQL Server Data Tools (SSDT), and its primary use case is to compare and visualize the differences between databases and .dacpac files and to execute actions to make them the same. |
| Moved Task view to Output Window | Users can now view the status of long running tasks like Backup, Restore, and Schema Compare in the Task view in Output window |
| Added Welcome page | - Links to common actions like New Query, New File, New Notebook<br />- Links to documentation and GitHub |
| SQL Notebook Improvements | - Markdown rendering improvements, including better support for notes and tables<br />- Usability improvements to the toolbar<br />- Markdown links for trusted notebooks no longer require Cmd/Ctrl + select and can be selected directly<br />- Improvements in cleaning up Jupyter processes after closing notebooks and reducing errors when starting multiple notebooks concurrently<br />- Improvements to SQL notebook connections to ensure errors don't occur when running two notebooks against the same database<br />- Improvements to notebook autoscrolling to the currently executing cell when selecting the Run Cells button from the toolbar<br />- General stability and performance improvements |
| Resolved bugs and issues. | See [Bugs and issues, on GitHub](https://github.com/microsoft/azuredatastudio/milestone/31?closed=1). |

### April 2019

April 18, 2019 / version: 1.6.0

| Change | Details |
| :--- | :--- |
| Renamed **Servers** tab to **Connections** | |
| Moved Azure Resource Explorer as an Azure viewlet under Connections | Users can now view their Azure SQL instances through Azure viewlet in the Connections view and expand to view objects under each server or database. |
| SQL Notebook Improvements | - Added button on toolbar to clear output for all cells<br />- Added button on toolbar to run all cells<br />- Fixed connection name instead of server name (if set) in the Attach to dropdown list<br />- Fix for images in markdown not rendering when using relative image paths<br />- Improved functionality in notebook grids by adding double-click auto resize column size and improved mousewheel support<br />- Improvements to error handling and python install resiliency when installing python through notebooks<br />- Improvements to "select all" functionality when selecting notebook cells<br />- Improvements to notebook connections to prevent closing a notebook and affecting an object explorer connection<br />- Improved notebook experience to display a message to the user when notebook disconnected and needs a connection to run cells<br />- Improved support for unsaved notebooks to rehydrate in Azure Data Studio when Azure Data Studio is started again |
| Resolved bugs and issues. | See [Bugs and issues, on GitHub](https://github.com/Microsoft/azuredatastudio/milestone/26?closed=1). |

### March 2019 (Hotfix)

March 22, 2019 / version: 1.5.2 / Hotfix release

| Change | Details |
| :--- | :--- |
| Fixed a few issues discovered in 1.5.1. | See [March Hotfix Release, on GitHub](https://github.com/Microsoft/azuredatastudio/milestone/28).<br /><br />- Fixed issue where user couldn't close notebook opened from the "Open Notebook" task in the Dashboard<br />- Fixed issue where Notebook JSON has extra } after save<br />- Fixed issue where notebook grids weren't responding to theme changes<br />- Fixed issue where full notebook path was shown in the tab header. Now only the filename is shown. |

### March 2019

March 18, 2019 / version: 1.5.1

| Change | Details |
| :--- | :--- |
| Added [PostgreSQL extension (Preview)](extensions/postgres-extension.md) | Supported features:<br />- Connection Dialog<br />- Object Explorer<br />- Query Editor<br />- Charting<br />- Dashboards<br />- Snippets<br />- Edit Data<br />- Notebooks |
| Added SQL Notebooks | Added SQL Kernel support to built-in Notebook viewer:<br />- Supports T-SQL<br />- Support PGSQL |
| Added PowerShell Extension | Brings over the [PowerShell extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell) experience from VS Code. |
| Added SQL Server dacpac extension | Removes Data-Tier Application Wizard from SQL Server Import extension into a new extension. |
| Added Community extension QueryPlan.show | Adds integration support to visualize query plans |
| Updated SQL Server 2019 Preview extension | - Jupyter Notebook support, specifically Python3, and Spark kernels, have moved into the core Azure Data Studio tool.<br />- Bug fixes to External Data Wizard |
| Resolved bugs and issues. | See [Bugs and issues, on GitHub](https://github.com/Microsoft/azuredatastudio/milestone/25?closed=1). |

### Known issues

| Issue | Workaround |
| --- | --- |
| [#4427](https://github.com/Microsoft/azuredatastudio/issues/4427): Selecting Run on Cell Before Kernel is Ready for Spark Results in Fatal Error | Wait until kernels are loaded until running any cells |
| [#4493](https://github.com/Microsoft/azuredatastudio/issues/4493): Azure Data Studio launched from SSMS using SQL auth - prompts user for password | Use Windows Authentication for now. |
| [#4494](https://github.com/Microsoft/azuredatastudio/issues/4494): Unable to install SQL notebook feature | Follow workaround steps [on GitHub](https://github.com/Microsoft/azuredatastudio/issues/4494#issuecomment-473043832). |
| [#4503](https://github.com/Microsoft/azuredatastudio/issues/4503): Azure Data Studio can't be Opened Directly from DownloAzure Data Studio Folder (macOS) | Restart computer after unzipping the app. Will be investigated. |
| [#4539](https://github.com/Microsoft/azuredatastudio/issues/4539): Notebook Save As loses connection context | Will be fixed in next release. |
| [#4458](https://github.com/Microsoft/azuredatastudio/issues/4458): Dacpac Extract crashes SqlToolsService if invalid version is used | Restart Azure Data Studio and ensure correct version is used. |
| New Notebook and Open Notebook icons are lost | The legacy connection type is deprecated. We recommend connecting to the SQL Server endpoint and you'll get all the actions (New Notebook, Spark Job) as expected. |

### February 2019

February 13, 2019 / version: 1.4.5

| Change | Details |
| :--- | :--- |
| Added **Admin pack for SQL Server** extension pack. | This makes it easier to install SQL Server admin-related extensions. This includes:<br />- [SQL Server Agent extension (Preview)](extensions/sql-server-agent-extension.md)<br />- [SQL Server Profiler extension (Preview)](extensions/sql-server-profiler-extension.md)<br />- [SQL Server Import extension](extensions/sql-server-import-extension.md) |
| Added filtering extended event support in Profiler extension. | |
| Added Save as XML feature that can save T-SQL results as XML. | |
| Added Data-Tier Application Wizard improvements. | - Added Generate script button<br />- Added view to give warnings of possible data loss during deployment. |
| Updates to the SQL Server 2019 Preview extension. | See [Data Virtualization extension for Azure Data Studio](extensions/data-virtualization-extension.md). |
| Results streaming enabled by default for long running queries. | |
| Resolved bugs and issues. | See [Bugs and issues, on GitHub](https://github.com/Microsoft/azuredatastudio/milestone/23?closed=1). |

### January 2019 (Hotfix)

January 16, 2019 / version: 1.3.9 / Hotfix release

| Change | Details |
| :--- | :--- |
| Fixed a few issues discovered in 1.3.8. | See [January Hotfix Release, on GitHub](https://github.com/Microsoft/azuredatastudio/milestone/24?closed=1).<br /><br />For detailed information, see:<br />- [Change Log, on GitHub](https://github.com/Microsoft/azuredatastudio/blob/main/CHANGELOG.md).<br />- [Releases, on GitHub](https://github.com/Microsoft/azuredatastudio/releases). |

### January 2019

January 09, 2019 / version: 1.3.8

| Change | Details |
| :--- | :--- |
| Added a new user installer for Windows. | Unlike the existing system installer, the new user installer doesn't require administrator privileges. This also enables an easier upgrade experience for non-administrators. |
| Added Microsoft Entra authentication support. | |
| Announcing Idera SQL DM Performance Insights (preview). | |
| Data-Tier Application Wizard support in SQL Server Import extension. | |
| Update to the SQL Server 2019 Preview extension. | See [Data Virtualization extension for Azure Data Studio](extensions/data-virtualization-extension.md). |
| SQL Server Profiler improvements. | |
| Results Streaming for large queries (preview). | |
| Community extensions: `sp_executesql` to sql and New Database. | |
| Resolved bugs and issues. | See [Bugs and issues, on GitHub](https://github.com/Microsoft/azuredatastudio/milestone/19?closed=1). |

## Related content

- [MSSQL extension for Visual Studio Code](/sql/tools/visual-studio-code-extensions/mssql/mssql-extension-visual-studio-code)
- [Download and install Azure Data Studio](download-azure-data-studio.md)
- [Quickstart: Use Azure Data Studio to connect and query SQL Server](quickstart-sql-server.md)
- [Quickstart: Use Azure Data Studio to connect and query Azure SQL Database](quickstart-sql-database.md)
- [Quickstart: Use Azure Data Studio to connect and query data using a dedicated SQL pool in Azure Synapse Analytics](quickstart-sql-dw.md)
- [Azure Data Studio - GitHub repository](https://github.com/Microsoft/azuredatastudio)
