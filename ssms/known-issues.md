---
title: Known Issues in SQL Server Management Studio
description: Learn about known issues in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mbarickman, erinstellato
ms.date: 02/11/2026
ms.service: sql-server-management-studio
ms.topic: troubleshooting-general
ms.collection:
  - data-tools
---

# Known issues in SQL Server Management Studio

[!INCLUDE [sql-asdb-asdbmi-asa](includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

This article lists known issues for [!INCLUDE [ssms-22-md](includes/ssms-22-md.md)].

| Feature | Details | Workaround |
| --- | --- | --- |
| Analysis Services | After adding a new role, or when opening properties for an existing role, you can't use **Search by name or email address** to add a user. | Add users with the **Manual Entry** option. |
| Arm64 | There's no support for SSAS and SSIS on Arm64 devices. | Run SSAS or SSIS on a device that isn't Arm64. |
| Arm64 - Data Classification | A LoadLibrary failure error message is displayed if you try to set Microsoft Information Protection Policy. | There's no workaround. |
| Arm64 - Replication | Trying to bring up the "Distributor Properties" form results in an exception. | Run SSMS on a device that isn't Arm64. |
| Available Databases Menu | A transient issue can cause the Available Databases dropdown menu to render incorrectly. | Change context to a different database with `USE <DatabaseName>` in the query editor. |
| Connection | You can't import connections from a previous version. This issue will be resolved in a later release. | There's no workaround. |
| Connection | Trying to connect to a SQL Server instance using Strict encryption through shared memory generates the error `Request is not supported`. See ["Shared Memory Provider, error: 15 - Function not supported" with Encrypt=Strict](https://github.com/dotnet/SqlClient/issues/1956). | Retry the connection. This error will be addressed in a future release of SSMS 22. |
| Extended Events | The Specify Data Storage page is truncated in the Extended Events Wizard. See [Extended Events Wizard is cut off on Specify Data Storage page](https://feedback.azure.com/d365community/idea/e7de428c-76ab-ef11-95f6-000d3a01397d). | Use the **New Session...** option to create an Extended Events session. |
| GitHub Copilot (Preview) | When you set `environment.visualExperience.hideCopilotBadge` to `true` in the `settings.json` file, the Copilot badge isn't hidden. | Select **Hide Copilot** from the Copilot badge. |
| GitHub Copilot (Preview) | GPT-5.1-Codex* models might produce errors or don't respond. | Don't use GPT-5.1-Codex* models. |
| GitHub Copilot (Preview) | A database constitution, created as an extended property for the database with the name `CONSTITUTION.md`, isn't recognized automatically by GitHub Copilot. | Include a direction to use the database constitution explicitly in your prompt. |
| Menu | Opening a folder from **File** > **Recent Projects and Solutions** generates one of the following errors: `System.InvalidOperationException: Can't enqueue project dependencies calculation before starting solution load` or `An exception of type NullReferenceException has been encountered.` if opening the folder also opens one or more files that were open in the editor when the folder was last closed. | Closing the error allows work to continue. Alternatively, close all files in the editor before closing a folder. |
| Offline installation | Installing an offline instance of SQL Server Management Studio 21 silently fails, with a `certificate is invalid` error message in the installation log. | Download and install the Microsoft Windows Code Signing PCA 2024 certificate. For more information, see [Create an offline installation of SQL Server Management Studio](install/install-certificates.md#validate-a-certificate-for-offline-installations). |
| Options | Enabling Per Monitor Awareness (PMA) by checking **Optimize rendering for screens with different pixel densities (requires restart)** within **Tools** > **Options** can cause issues with dialogs not rendering. | Don't enable **Optimize rendering for screens with different pixel densities (requires restart)** within **Tools** > **Options**. |
| Options | Enabling **Unified Settings Experience (requires restart)** within **Tools** > **Options** > **General** > **Preview Features** can cause issues with dialogs not rendering. | Don't enable **Unified Settings Experience (requires restart)** within **Tools** > **Options** > **General** > **Preview Features**. |
| Options | Changing the default value for options within **Tools** > **Options** > **General** > **Preview Features** can cause unpredictable behavior, both in terms of visual display and functionality. | Don't change the default value for any option within **Tools** > **Options** > **General** > **Preview Features**. |
| Query Store | When you use any of the Query Store reports, the Replica dropdown menu option might not populate with the correct replica name when the [Query Store for readable secondary replicas](/sql/relational-databases/performance/query-store-for-secondary-replicas) is enabled. | Use Transact-SQL to query the Query Store data for a readable secondary where the `replica_group_id` for a secondary can be mapped using the [sys.query_store_runtime_stats](/sql/relational-databases/system-catalog-views/sys-query-store-runtime-stats-transact-sql) system catalog view, which has a foreign key relationship with the [sys.query_store_replicas](/sql/relational-databases/system-catalog-views/sys-query-store-replicas) system catalog view. |
| Results Pane | When you switch themes, if the output is set to Results to Text, the Results pane doesn't switch to the new theme. | To apply any theme changes to the Results pane, restart SSMS. |
| SQL Server Integration Services (SSIS) | Maintenance Tasks (including Back Up Database Task, Check Database Integrity Task, Execute SQL Server Agent Job Task, Execute T-SQL Statement Task, History Cleanup Task, and Maintenance Cleanup Task) aren't supported by [Execute Package Utility (dtexecui)](/sql/integration-services/packages/execute-package-utility-dtexecui-ui-reference). | Use [dtexec Utility](/sql/integration-services/packages/dtexec-utility) to run packages including these Maintenance Tasks or use [Execute Package Utility (dtexecui)](/sql/integration-services/packages/execute-package-utility-dtexecui-ui-reference) in SSMS 20. |
| SQL Server Integration Services (SSIS) | SSIS Integration Runtime creation wizard isn't supported. | Use Azure Data Factory portal to [Create an Azure-SSIS integration runtime](/azure/data-factory/create-azure-ssis-integration-runtime-portal?tabs=data-factory). |
| SQL Server Integration Services (SSIS) | Using the Execute Package Utility (dtexecui) to run Integration Packages with Script Task fails. | Manually download and install [Microsoft Visual Studio for Applications 2022](https://www.microsoft.com/download/details.aspx?id=105123) first, before running package execution. |
| Vector | Renaming a vector index using T-SQL or in Object Explorer generates the error `Invalid EXECUTE statement using object "IndexOrStats", method "SetName".` | There's currently no workaround. |

## Related content

- [Install SQL Server Management Studio](install/install.md)
