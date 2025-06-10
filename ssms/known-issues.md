---
title: Known Issues in SQL Server Management Studio
description: Learn about known issues in SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan, mbarickman
ms.date: 06/10/2025
ms.service: sql-server-management-studio
ms.topic: troubleshooting-general
ms.collection:
  - data-tools
---

# Known issues in SQL Server Management Studio

[!INCLUDE [sql-asdb-asdbmi-asa](includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

This page lists known issues for [!INCLUDE [ssms-21-md](includes/ssms-21-md.md)].

| Feature | Details | Workaround |
| --- | --- | --- |
| Arm64 | SSMS isn't currently supported on Arm64. | Run SSMS on a device that isn't Arm64. |
| Designers | The JSON data type isn't available for columns when creating or editing a table in Table Designer. See [SSMS 21.0 Preview 2.0 - Table Designer missing the "json" datatype](https://feedback.azure.com/d365community/idea/d2e6f106-9fb8-ef11-95f5-6045bdbfaf80). | Use T-SQL to add columns with the JSON data type, this functionality is planned for a later release. |
| Designers | Unable to use SSMS after closing the **New View** pane when the **Add Table** dialog is left open. See [SSMS 21 Preview 1: New View window "Add Table" not aware I closed out of New View](https://feedback.azure.com/d365community/idea/8790c2c0-22a8-ef11-95f6-000d3a01397d). | Close the **Add Table** dialog before closing the view pane. |
| Extended Events | The Specify Data Storage page is truncated in the Extended Events Wizard. See [Extended Events Wizard is cut off on Specify Data Storage page](https://feedback.azure.com/d365community/idea/e7de428c-76ab-ef11-95f6-000d3a01397d). | Use the **New Session...** option to create an Extended Events session. |
| SQL Server Integration Services (SSIS) | If a data source other than Microsoft OLEDB Provider for SQL Server is selected in the Import and Export Wizard, an error is generated. | Add `dependentAssembly` inside the `<assemblyBinding>` section of `C:\Program Files\Microsoft SQL Server Management Studio 21\Release\Common 7\IDE\CommonExtensions\Microsoft\SSIS\170\Binn\default.applocal.config` as follows: `<dependentAssembly><assemblyIdentity name="Microsoft.SqlServer.BatchParser"publicKeyToken="89845dcd8080cc91"culture="neutral"/><bindingRedirect oldVersion="17.0.0.0" newVersion="17.100.0.0"/><codeBase version="17.100.0.0"href="{0}\Microsoft.SqlServer.BatchParser.dll"/></dependentAssembly>.` |
| SQL Server Integration Services (SSIS) | Use of the [Execute package utility (dtexecui)](/sql/integration-services/packages/execute-package-utility-dtexecui-ui-reference) isn't currently supported. | Use an earlier version of SSMS to access the Execute package utility. |
| SQL Server Integration Services (SSIS) | Support for legacy [Integration Services service](/sql/integration-services/service/integration-services-service-ssis-service#manage-the-service) isn't available for SQL Server 2022. | To manage the legacy Integration Services Service for SQL Server 2022, use SSMS 20.2.1 or SSMS 19.3. |
| Logins | Unable to map a credential for a login. See [SSMS v21 Preview 1 - Bug in Login Properties for Credentials](https://feedback.azure.com/d365community/idea/e0687671-dca3-ef11-95f6-000d3a059eeb). | Use T-SQL to map a login to a credential. |
| Menu | Opening a folder from **File** > **Recent Projects and Solutions** generates one of the following errors: "System.InvalidOperationException: Can't enqueue project dependencies calculation before starting solution load" or "An exception of type NullReferenceException has been encountered." if opening the folder also opens one or more files that were open in the editor when the folder was last closed. | Closing the error allows work to continue. Alternatively, close all files in the editor before closing a folder. |
| Modern Connection Dialog (Preview) | Trying to change the password for a newly created SQL login with the MUST_CHANGE property enabled generates the error "Login failed for user. Reason: The password of the account must be changed. (Microsoft SQL Server, Error: 18488)". See [Instead of Change password dialog an error pops up](https://developercommunity.visualstudio.com/t/Instead-of-Chage-password-dialog-an-erro/10899416). | Use the Classic connection dialog to change the password. |
| Modern Connection Dialog (Preview) | Importing connection history for the new connection dialog generates the error "An error occurred while importing the connection history from the classic connection dialog. The given key was not present in the dictionary." | The error occurs when there are corrupted connections in your history, and they aren't imported into the new dialog. The error can be safely ignored. |
| Modern Connection Dialog (Preview) | Upon first use, when importing saved connections to the Modern connection dialog (Preview), saved passwords are lost. | Manually enter your passwords to save them to your connection profiles in the Modern connection dialog (Preview). |
| Options | Enabling Per Monitor Awareness (PMA) by checking **Optimize rendering for screens with different pixel densities (requires restart)** within **Tools** > **Options** can cause issues with dialogs not rendering. | Don't enable **Optimize rendering for screens with different pixel densities (requires restart)** within **Tools** > **Options**. |
| Options | Enabling **Unified Settings Experience (requires restart)** within **Tools** > **Options** > **General** > **Preview Features** can cause issues with dialogs not rendering. | Don't enable **Unified Settings Experience (requires restart)** within **Tools** > **Options** > **General** > **Preview Features**. |
| Query Store | When you use any of the Query Store reports, the Replica dropdown list menu option might not populate with the correct replica name when the [Query Store for readable secondaries](/sql/relational-databases/performance/query-store-for-secondary-replicas) is enabled. | Use Transact-SQL to query the Query Store data for a readable secondary where the `replica_group_I'd` for a secondary can be mapped using the [sys.query_store_runtime_stats system](/sql/relational-databases/system-catalog-views/sys-query-store-runtime-stats-transact-sql) catalog view, which has a foreign key relationship with the [sys.query_store_replicas](/sql/relational-databases/system-catalog-views/sys-query-store-replicas) system catalog view. |
| Results Pane | When switching themes, if the output is set to Results to Text, the Results pane doesn't switch themes. The original theme is still applied. | To apply any theme changes to the Results pane, restart SSMS. |

## Related content

- [Install SQL Server Management Studio](install/install.md)
