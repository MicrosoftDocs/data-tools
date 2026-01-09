---
title: "Custom Reports in Management Studio"
description: Learn about custom reports available in SQL Server Management Studio.
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/07/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.summary.new.custom.report.f1"
  - "sql13.swb.summary.render.custom.report.f1"
helpviewer_keywords:
  - "SQL Server Management Studio [SQL Server], custom reports"
---

# Custom reports in SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Azure SQL Managed Instance Synapse Analytics PDW Fabric SE Fabric DW Fabric SQL DB](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw-fabricse-fabricdw-fabricsqldb.md)]

In [!INCLUDE [ssManStudioFull](../includes/ssmanstudiofull-md.md)], many Object Explorer nodes display a set of standard reports that are created by [!INCLUDE [msCoName](../includes/msconame-md.md)]. These reports summarize typically requested server information. Administrators can run custom reports that were created in [!INCLUDE [ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] from [!INCLUDE [ssManStudio](../includes/ssmanstudio-md.md)].

## Implementation

Custom reports are stored as report definition (`.rdl`) files and are created by using Report Definition Language (RDL). RDL contains data retrieval and layout information for a report in an XML format. RDL is an open schema. Developers can extend RDL with extra attributes and elements. Reports can execute any valid [!INCLUDE [tsql](../includes/tsql-md.md)] statement within the report.

If Object Explorer is connected to a server, custom reports can execute in the context of the current Object Explorer selection if the reports reference report parameters of that node. This enables a report to use the current context, such as the current database; or a consistent context, such as specifying a designated database as part of the [!INCLUDE [tsql](../includes/tsql-md.md)] statement that is contained in the custom report.

## Run a custom report

You can run a custom report in [!INCLUDE [ssManStudio](../includes/ssmanstudio-md.md)] in the following ways:

- Right-click a node in Object Explorer, go to **Reports** > **Custom Reports**. In the **Open File** dialog box, locate a folder that contains `.rdl` files, and then open the appropriate report file.

- Right-click a node in Object Explorer, go to **Reports** > **Custom Reports**, and then select a custom report from the most recently used file list.

## Limitations

When you work with custom reports, consider the following limitations:

- To prevent the unintended execution of malicious code, [!INCLUDE [ssManStudio](../includes/ssmanstudio-md.md)] can't be configured to automatically run a report, even if the file system is configured to associate `.rdl` files with [!INCLUDE [ssManStudio](../includes/ssmanstudio-md.md)]. Reports can't be programmatically executed in [!INCLUDE [ssManStudio](../includes/ssmanstudio-md.md)] and can't run from the command line through [!INCLUDE [ssManStudio](../includes/ssmanstudio-md.md)].

- You can run custom reports in a context that doesn't produce the expected values. For example, you can run a report about replication in the context of a database that isn't involved in replication, or run a report as a user who doesn't have permission to access information that is required to generate an accurate report. The creator of the custom report is responsible for the validity of the report structure and its context.

- You can't add a custom report to the list of standard reports.

- The code processed by the report might affect server performance.

- Custom reports don't support subreports.

- The command text for each query within the report must not be defined through an expression.

- Any query parameter that is used in a command (query) can only reference a single report parameter and can't use any expression operators.

- Only Text and Stored Procedure command types are supported for report commands (queries).

- The report framework doesn't provide any parameter escaping for the queries. Query authors must make sure that their queries are free from SQL injection attacks.

## Manage custom reports

We recommend that users who have many custom reports organize them by using file system folders that have appropriate NTFS file system permissions.

## Permissions

Custom reports run by using the permissions of the current user. To prevent a malicious user from changing the queries run by the report, permissions on the file system folder that contains the report files should be set to restrict access.

Both the user and the account that is used by the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] service require read access to the file system folder that contains the report files.

Any valid [!INCLUDE [dnprdnshort](../includes/dnprdnshort-md.md)] command can be embedded in a report, but the command isn't executed.

> [!CAUTION]  
> Any valid [!INCLUDE [tsql](../includes/tsql-md.md)] statement can be embedded in and executed from a report. Running a report under a high-privileged user account makes it possible for any of these embedded instructions to execute without challenge.

## Related content

- [Add a custom report to SQL Server Management Studio](add-a-custom-report-to-management-studio.md)
- [Unsuppress run custom report warnings](unsuppress-run-custom-report-warnings.md)
- [Use custom reports with Object Explorer node properties](use-custom-reports-with-object-explorer-node-properties.md)
