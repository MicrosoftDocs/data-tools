---
title: Open and Configure Object Explorer
description: Learn how to access and configure Object Explorer to browse Microsoft SQL Database Engine servers and databases.
author: rwestMSFT
ms.author: randolphwest
ms.date: 03/18/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---
# Open and configure Object Explorer

[!INCLUDE [SQL Server Azure SQL Database Azure SQL Managed Instance Synapse Analytics PDW Fabric SE Fabric DW Fabric SQL DB](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw-fabricse-fabricdw-fabricsqldb.md)]

Object Explorer is the primary tool window in SQL Server Management Studio (SSMS) for browsing servers and databases. From Object Explorer you can create and locate objects, manage data sources, and view logs.

## View Object Explorer

The Object Explorer tool window is available when you connect to a SQL database. If you don't see Object Explorer, select **View** > **Object Explorer**, or select `F8`.

## Configure Object Explorer options

By default, Object Explorer opens when you start SSMS. You can change this behavior in **Tools** > **Options** > **Environment** > **Startup**.

To configure Object Explorer settings, including scripting behavior, go to **Tools** > **Options** > **SQL Server Object Explorer**.

Within Object Explorer, objects are grouped by type (table, stored procedure) by default. Starting with SSMS 22.4.1, objects can be grouped by schema for any SQL database. Use the group by schema icon to toggle the setting, and you can change the default behavior in **Tools** > **Options** > **SQL Server Object Explorer** > **General** > **Group objects by Schema**.

## Related content

- [Object Explorer](object-explorer.md)
- [Connect with SQL Server Management Studio](../quickstarts/ssms-connect.md)
- [Manage objects using Object Explorer](manage-objects-by-using-object-explorer.md)
- [Object Explorer Details pane](object-explorer-details-pane.md)
- [Custom reports in SQL Server Management Studio](custom-reports-in-management-studio.md)
