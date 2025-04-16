---
title: Known Issues in SQL Server Management Studio
description: Learn about known issues in SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan, mbarickman
ms.date: 04/16/2025
ms.service: sql-server-management-studio
ms.topic: troubleshooting-general
ms.collection:
  - data-tools
---

# Known issues in SQL Server Management Studio 21 Preview

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

This page lists known issues for [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)].

| Feature | Details | Workaround |
| --- | --- | --- |
| Arm64 | There's no support for Arm64, and SSMS can't be installed on Arm64 devices. | Run SSMS on a device that isn't Arm64. |
| Designers | Closing the view editor before saving in the View Designer generates the error "Object reference not set to an instance of an object. (SqlEditors)". | Save the new view before closing the editor in the View Designer. |
| Designers | The JSON data type isn't available for columns when creating or editing a table in Table Designer. See [SSMS 21.0 Preview 2.0 - Table Designer missing the "json" datatype](https://feedback.azure.com/d365community/idea/d2e6f106-9fb8-ef11-95f5-6045bdbfaf80). | Use T-SQL to add columns with the JSON data type, this functionality is planned for a later release. |
| Designers | Unable to use SSMS after closing the **New View** pane when the **Add Table** dialog is left open. See [SSMS 21 Preview 1: New View window "Add Table" not aware I closed out of New View](https://feedback.azure.com/d365community/idea/8790c2c0-22a8-ef11-95f6-000d3a01397d). | Close the **Add Table** dialog before closing the view pane. |
| Extended Events | The Specify Data Storage page is truncated in the Extended Events Wizard. See [Extended Events Wizard is cut off on Specify Data Storage page](https://feedback.azure.com/d365community/idea/e7de428c-76ab-ef11-95f6-000d3a01397d). | Use the **New Session...** option to create an Extended Events session. |
| Integration Services | There's currently no support for Integration Services in [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)]. | Use SSMS 20.2 to connect to Integration Services, we'll bring back Integration Services in a future preview. |
| Logins | Unable to map a credential for a login. See [SSMS v21 Preview 1 - Bug in Login Properties for Credentials](https://feedback.azure.com/d365community/idea/e0687671-dca3-ef11-95f6-000d3a059eeb). | Use T-SQL to map a login to a credential. |
| Maintenance Plans | There's currently no support for creating or editing maintenance plans in [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)]. | Use SSMS 20.2 to create or edit maintenance plans, we'll bring back Integration Services in a future preview. |
| Menu | The **File** > **File** menu option isn't available. | Use **File** > **New Query with current connection** or the New Query button to open a new query editor. |
| Menu | Opening a folder from **File** > **Recent Projects and Solutions** generates one of the following errors: "System.InvalidOperationException: Can't enque project dependencies calculation before starting solution load" or "An exception of type NullReferenceException has been encountered." if opening the folder also opens one or more files that were open in the editor when the folder was last closed. | Closing the error allows work to continue. Alternatively, close all files in the editor before closing a folder. |
| Modern Connection Dialog (preview) | Setting `ApplicationIntent` to `ReadOnly` in the **Advanced...** settings isn't applied to the connection. | Use the Classic connection dialog if you need to set `ApplicationIntent` to `ReadOnly`. |
| Modern Connection Dialog (preview) | There's currently no way to create a firewall rule when connecting to an Azure SQL DB with the Modern connection dialog (preview). | Create a firewall rule in the Azure Portal or switch back to the Classic connection dialog. |
| Options | Enabling Per Monitor Awareness (PMA) by checking **Optimize rendering for screens with different pixel densities (requires restart)** within **Tools** > **Options** can cause issues with dialogs not rendering. | Don't enable **Optimize rendering for screens with different pixel densities (requires restart)** within **Tools** > **Options**. |
| Options | Enabling **Unified Settings Experience (requires restart)** within **Tools** > **Options** > **General** > **Preview Features** can cause issues with dialogs not rendering. | Don't enable **Unified Settings Experience (requires restart)** within **Tools** > **Options** > **General** > **Preview Features**. |
| Query Store | When you use any of the Query Store reports, the Replica drop-down menu option may not populate with the correct replica name when the [Query Store for secondary replicas feature](/sql/relational-databases/performance/query-store-for-secondary-replicas) is enabled. | Use Transact-SQL to query the Query Store data for a readable secondary where the `replica_group_I'd` for a secondary can be mapped using the [sys.query_store_runtime_stats system](/sql/relational-databases/system-catalog-views/sys-query-store-runtime-stats-transact-sql) catalog view, which has a foreign key relationship with the [sys.query_store_replicas](/sql/relational-databases/system-catalog-views/sys-query-store-replicas) system catalog view. |
| Results Grid | When you switch themes, if Results Grid is set to Results to Text, the Results component doesn't switch themes, it applies the theme SSMS uses when it originally opens. | To apply any theme changes to the Results component, restart SSMS. |
| Settings | Changing font settings doesn't persist after a restart. See [SSMS 21 Preview 1 - Environment Font Settings Not saving in a particular use-case](https://feedback.azure.com/d365community/idea/0d395829-b5a6-ef11-95f6-000d3a059eeb). | Change the theme at the same time as the font settings. |
| Terminal | Using **Developer PowerShell** or **Developer Command Prompt** from **View** > **Terminal** generates an error. See [SSMS 21 Preview - Visual Studio developer prompt options should probably be hidden or removed](https://feedback.azure.com/d365community/idea/b592405d-cbaa-ef11-95f6-000d3a01397d). | Customize the file that launches through customize what launches in SSMS, through **Tools** > **Options** > **Environment** > **Terminal**. A fix is expected in a future preview. |

## Related content

- [Install SQL Server Management Studio 21 Preview](../install/install.md)
