---
title: Known Issues in SQL Server Management Studio (SSMS) 22 Preview
description: Learn about known issues in SQL Server Management Studio (SSMS) 22 Preview.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, mbarickman
ms.date: 10/14/2025
ms.service: sql-server-management-studio
ms.topic: troubleshooting-general
ms.collection:
  - data-tools
---

# Known issues in SQL Server Management Studio 22 Preview

[!INCLUDE [sql-asdb-asdbmi-asa](includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

This article lists known issues for [!INCLUDE [ssms-22-md](includes/ssms-22-md.md)] Preview.

| Feature | Details | Workaround |
| --- | --- | --- |
| Arm64 | There isn't support for SSAS, SSRS, and SSIS on Arm64 devices. | Run SSAS, SSRS, or SSIS on a device that isn't Arm64. |
| Arm64 - Profiler | Trying to run Profiler results in an exception. | Run Profiler on a device that isn't Arm64. |
| Arm64 - Replication | Trying to bring up the "Distributor Properties" form results in an exception. | Run SSMS on a device that isn't Arm64. |
| Connection | You can't import connections from a previous version. This issue is scheduled to be resolved in a later preview. | There's no workaround. |
| Designers | The JSON data type isn't available for columns when creating or editing a table in Table Designer. See [SSMS 21.0 Preview 2.0 - Table Designer missing the "json" datatype](https://feedback.azure.com/d365community/idea/d2e6f106-9fb8-ef11-95f5-6045bdbfaf80). | Use T-SQL to add columns with the JSON data type, this functionality is planned for a later release. |
| Designers | Unable to use SSMS after closing the **New View** pane when the **Add Table** dialog is left open. See [SSMS 21 Preview 1: New View window "Add Table" not aware I closed out of New View](https://feedback.azure.com/d365community/idea/8790c2c0-22a8-ef11-95f6-000d3a01397d). | Close the **Add Table** dialog before closing the view pane. |
| Extended Events | The Specify Data Storage page is truncated in the Extended Events Wizard. See [Extended Events Wizard is cut off on Specify Data Storage page](https://feedback.azure.com/d365community/idea/e7de428c-76ab-ef11-95f6-000d3a01397d). | Use the **New Session...** option to create an Extended Events session. |
| Menu | Opening a folder from **File** > **Recent Projects and Solutions** generates one of the following errors: `System.InvalidOperationException: Can't enqueue project dependencies calculation before starting solution load` or `An exception of type NullReferenceException has been encountered.` if opening the folder also opens one or more files that were open in the editor when the folder was last closed. | Closing the error allows work to continue. Alternatively, close all files in the editor before closing a folder. |
| Modern Connection Dialog (Preview) | Trying to change the password for a newly created SQL login with the `MUST_CHANGE` property enabled generates the error "Login failed for user. Reason: The password of the account must be changed. (Microsoft SQL Server, Error: 18488)". See [Instead of Change password dialog an error pops up](https://developercommunity.visualstudio.com/t/Instead-of-Chage-password-dialog-an-erro/10899416). | Use the Classic connection dialog to change the password. |
| Offline installation | Installing an offline instance of SQL Server Management Studio 21 silently fails, with a `certificate is invalid` error message in the installation log. | Download and install the Microsoft Windows Code Signing PCA 2024 certificate. For more information, see [Create an offline installation of SQL Server Management Studio](install/create-offline.md#validate-a-certificate-for-offline-installations). |
| Options | Enabling Per Monitor Awareness (PMA) by checking **Optimize rendering for screens with different pixel densities (requires restart)** within **Tools** > **Options** can cause issues with dialogs not rendering. | Don't enable **Optimize rendering for screens with different pixel densities (requires restart)** within **Tools** > **Options**. |
| Options | Enabling **Unified Settings Experience (requires restart)** within **Tools** > **Options** > **General** > **Preview Features** can cause issues with dialogs not rendering. | Don't enable **Unified Settings Experience (requires restart)** within **Tools** > **Options** > **General** > **Preview Features**. |
| Options | Changing the default value for options within **Tools** > **Options** > **General** > **Preview Features** can cause unpredictable behavior, both in terms of visual display and functionality. | Don't change the default value for any option within **Tools** > **Options** > **General** > **Preview Features**. |
| Query Store | When you use any of the Query Store reports, the Replica dropdown list menu option might not populate with the correct replica name when the [Query Store for readable secondaries](/sql/relational-databases/performance/query-store-for-secondary-replicas) is enabled. | Use Transact-SQL to query the Query Store data for a readable secondary where the `replica_group_id` for a secondary can be mapped using the [sys.query_store_runtime_stats system](/sql/relational-databases/system-catalog-views/sys-query-store-runtime-stats-transact-sql) catalog view, which has a foreign key relationship with the [sys.query_store_replicas](/sql/relational-databases/system-catalog-views/sys-query-store-replicas) system catalog view. |
| Results Pane | When switching themes, if the output is set to Results to Text, the Results pane doesn't switch themes. The original theme is still applied. | To apply any theme changes to the Results pane, restart SSMS. |
| SQL Server Integration Services (SSIS) | Maintenance Tasks (including Back Up Database Task, Check Database Integrity Task, Execute SQL Server Agent Job Task, Execute T-SQL Statement Task, History Cleanup Task, and Maintenance Cleanup Task) aren't supported by [Execute Package Utility (dtexecui)](/sql/integration-services/packages/execute-package-utility-dtexecui-ui-reference). | Use [dtexec Utility](/sql/integration-services/packages/dtexec-utility) to run packages including these Maintenance Tasks or use [Execute Package Utility (dtexecui)](/sql/integration-services/packages/execute-package-utility-dtexecui-ui-reference) in SSMS 20. |
| SQL Server Integration Services (SSIS) | SSIS Integration Runtime creation wizard isn't supported. | Use Azure Data Factory portal to [Create an Azure-SSIS integration runtime](/azure/data-factory/create-azure-ssis-integration-runtime-portal?tabs=data-factory). |

## Related content

- [Install SQL Server Management Studio 22 Preview](install/install-preview.md)
