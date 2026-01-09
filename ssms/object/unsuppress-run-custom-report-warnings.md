---
title: "Unsuppress Run Custom Report Warnings"
description: "Unsuppress Run Custom Report Warnings"
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
# Unsuppress run custom report warnings

[!INCLUDE [SQL Server Azure SQL Database Azure SQL Managed Instance Synapse Analytics PDW Fabric SE Fabric DW Fabric SQL DB](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw-fabricse-fabricdw-fabricsqldb.md)]

There are two warning dialog boxes for custom reports. This article describes how to unsuppress the display of these boxes in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] by using [!INCLUDE [ssManStudioFull](../includes/ssmanstudiofull-md.md)].

By default, the **Run Custom Reports** dialog box appears before a custom report runs. If you select the **Please don't show this warning again** check box, the dialog box no longer appears. Also by default, the **Run Custom Reports** dialog box appears when you open a custom report and then select a link to open another custom report. This dialog box displays the fill path to the drill-through custom report file. If you select the **Please don't show this warning again** check box, the dialog box no longer appears.

<a id="SSMSProcedure"></a>

## Use SQL Server Management Studio

### Unsuppress the main custom report warning dialog box

1. Connect to `<server>\<share or drive>\Documents and Settings\<UserProfile>\Application Data\Microsoft\Microsoft SQL Server\130\Tools\Shell\reports.xml`.

1. Right-click `reports.xml`, and then select **Edit**.

1. Change `<SuppressWarning>true</SuppressWarning>` to `<SuppressWarning>false</SuppressWarning>`.

1. Restart SQL Server Management Studio.

### Unsuppress the drill-through custom report warning dialog box

1. Connect to `<server>\<share or drive>\Documents and Settings\<UserProfile>\Application Data\Microsoft\Microsoft SQL Server\130\Tools\Shell\reports.xml`.

1. Right-click `reports.xml`, and select **Edit**.

1. Change `<SuppressDrillthroughWarning>true</SuppressDrillthroughWarning>` to `<SuppressDrillthroughWarning>false</SuppressDrillthroughWarning>`.

1. Restart SQL Server Management Studio.

## Related content

- [Custom reports in SQL Server Management Studio](custom-reports-in-management-studio.md)
- [Add a custom report to SQL Server Management Studio](add-a-custom-report-to-management-studio.md)
- [Use custom reports with Object Explorer node properties](use-custom-reports-with-object-explorer-node-properties.md)
