---
title: "Add a Custom Report to Management Studio"
description: "Add a Custom Report to Management Studio"
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/07/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Management Studio [SQL Server], custom reports"
---
# Add a custom report to SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Azure SQL Managed Instance Synapse Analytics PDW Fabric SE Fabric DW Fabric SQL DB](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw-fabricse-fabricdw-fabricsqldb.md)]

This article describes how to create a basic [!INCLUDE [ssRSnoversion](../includes/ssrsnoversion-md.md)] report that is saved as an `.rdl` file, and then add that `.rdl` file to [!INCLUDE [ssManStudioFull](../includes/ssmanstudiofull-md.md)] as a custom report. [!INCLUDE [ssRS](../includes/ssrs.md)] can create a wide variety of sophisticated reports. To create a report by using this article, [!INCLUDE [ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] must be installed on the computer. You don't have to install [!INCLUDE [ssRS](../includes/ssrs.md)] on [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] to run a custom report using [!INCLUDE [ssManStudio](../includes/ssmanstudio-md.md)].

## Create a basic report saved as an `.rdl` file

1. Select **Start**, point to **Programs**, point to **Microsoft SQL Server**, and then select **SQL Server Data Tools**.

1. On the **File** menu, point to **New**, and then select **Project**.

1. In the **Project Types** list, select **Business Intelligence Projects**.

1. In the **Templates** list, select **Report Server Project Wizard**.

1. In **Name**, type **ConnectionsReport**, and then select **OK**.

1. On the **Report Wizard** introduction page, select **Next**.

1. On the **Select the Data Source** page, in the Name box type a name for this connection to your [!INCLUDE [ssDE](../includes/ssde-md.md)], and then select **Edit**.

1. In the **Connection Properties** dialog box, in the **Server name** box, type the name of your instance of the [!INCLUDE [ssDE](../includes/ssde-md.md)].

1. In the **Select or enter a database name** box, type the name of any database on your [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)], such as [!INCLUDE [ssSampleDBobject](../includes/sssampledbobject-md.md)], and then select **OK**.

1. On the **Select the Data Source** page, select **Next**.

1. On the **Design the Query** page, in the **Query string** box, type the following [!INCLUDE [tsql](../includes/tsql-md.md)] statement that lists the current connections to your [!INCLUDE [ssDE](../includes/ssde-md.md)], and then select **Next**. The Report Wizard Query string box doesn't accept report parameters. More complex custom reports must be created manually.

   ```sql
   SELECT session_id,
          net_transport
   FROM sys.dm_exec_connections;
   ```

1. On the **Select the Report Type** page, select **Tabular**, and then select **Finish**.

1. On the **Completing the Wizard** page, in the **Report name** box, type `ConnectionsReport`, and then select **Finish** to create and save the report.

1. Close [!INCLUDE [ssBIDevStudio](../includes/ssbidevstudio-md.md)].

1. Copy `ConnectionsReport.rdl` to a folder that you created on the database server for custom reports.

## Add a report to Management Studio

- In [!INCLUDE [ssManStudio](../includes/ssmanstudio-md.md)], right-click a node in Object Explorer, point to **Reports**, select **Custom Reports**. In the **Open File** dialog box, locate the custom reports folder and select the `ConnectionsReport.rdl` file, and then select **Open**.

  When a new custom report is first opened from an Object Explorer node, the custom report is added to the most recently used list under **Custom Reports** on the shortcut menu of that node. When a standard report is opened for the first time, it also appears on the most recently used list under **Custom Reports**. If a custom report file is deleted, the next time that the item is selected, a prompt will appear to delete the item from the most recently used list.

  1. To change the number of files that are displayed on the recently used list, on the **Tools** menu, select **Options,** expand the **Environment** folder, and then select **General**.

  1. Adjust the number for **Display files in recently used list**.

## Related content

- [Custom reports in SQL Server Management Studio](custom-reports-in-management-studio.md)
- [Use custom reports with Object Explorer node properties](use-custom-reports-with-object-explorer-node-properties.md)
- [Unsuppress run custom report warnings](unsuppress-run-custom-report-warnings.md)
- [What is SQL Server Reporting Services (SSRS)?](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)
