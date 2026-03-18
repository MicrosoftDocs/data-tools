---
title: Query Results in SQL Server Management Studio
titleSuffix: SQL Server Management Studio
description: Understand options for query results in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: erinstellato
ms.date: 03/18/2026
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
helpviewer_keywords:
  - "query results [SQL Server Management Studio]"
  - "results to grid [SQL Server Management Studio]"
  - "results to text [SQL Server Management Studio]"
  - "results to file [SQL Server Management Studio]"
  - "results to JSON [SQL Server Management Studio]"
  - "results to CSV [SQL Server Management Studio]"
  - "results to Excel [SQL Server Management Studio]"
dev_langs:
  - TSQL
---

# Query results in SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Azure SQL Managed Instance Synapse Analytics PDW Fabric SE Fabric DW Fabric SQL DB](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw-fabricse-fabricdw-fabricsqldb.md)]

When you run Transact-SQL (T-SQL) statements in the Query Editor in SQL Server Management Studio (SSMS), you can control the output of the query results. You can also export the results to different file formats, depending on your requirements.

## Choose a query results destination

The results destination applies to the current Query Editor window. By default, results appear in the grid, but you can choose to send them to text, or to a file. When you select a different option, SSMS uses it the next time you execute a query in that window.

Select a destination in one of the following ways:

- On the SQL Editor toolbar, select **Results to Grid**, **Results to Text**, or **Results to File**.

- In the Query Editor, open the context menu and select **Results** > **Results to Grid**, **Results to Text**, or **Results to File**.

- Use the keyboard shortcuts listed in the [Keyboard shortcuts](#keyboard-shortcuts) section.

Change the default output for results in **Tools** > **Options** > **Query Results** > **SQL Server** > **General** using the **Default destination for results** dropdown list.

## Results to grid

**Results to grid** returns query results as one or more tabular grids in the **Results** window. This option is the default for new Query Editor windows.

Use grid results when you want to:

- View data in a tabular format with column headers.
- Copy selected rows, columns, or the full result set, with or without headers.
- Save the grid contents to a file from the grid context menu.

To send results to a grid:

1. On the SQL Editor toolbar, select **Results to Grid**.
1. Or, in the Query Editor context menu, select **Results** > **Results to Grid**.
1. Execute the query.

By default, the grid appears in the lower pane of the Query Editor window. If the query returns multiple result sets, each result set appears in its own grid tab.

### Export results

If you don't save results directly to a file, you can choose to export them to a file from the results grid. Right-click anywhere in the results grid and select **Save Results As...**. In the **Save Grid Results** dialog, enter a file name and select the **Save as type** dropdown list to select the file type for the results.

In SSMS 22.3.3 and earlier versions, you can export results to CSV and TXT file types.

Starting in SSMS 22.4.1, you can also export results to JSON, XML, Excel, and Markdown file types.

You can change the default location used when you export results in **Tools** > **Options** > **Query Results** > **SQL Server** > **General** > **Query results directory**. This default location is the same location used when saving results to a file.

## Results to text

**Results to text** returns query results as plain text in the **Results** window. Each column is separated by a delimiter, and rows appear as lines of text.

Use text results when you want to:

- Quickly scan smaller result sets without grid features.
- Copy results as formatted text into emails, issue descriptions, or scripts.
- Compare textual output more easily with tools that expect plain text.

To send results to text:

1. On the SQL Editor toolbar, select **Results to Text**.
1. Or, in the Query Editor context menu, select **Results** > **Results to Text**.
1. Execute the query.

You can change text output formatting, such as column separator and maximum column width, in **Tools** > **Options** > **Query Results** > **SQL Server** > **Results to Text**.

## Results to file

**Results to file** writes query results directly to a file instead of displaying them in the **Results** window.

Use file results when you want to:

- Capture large result sets without rendering them in the UI.
- Save results for later analysis or archiving.
- Share result data as a file.

To send results to a file:

1. On the SQL Editor toolbar, select **Results to File**.
1. Or, in the Query Editor context menu, select **Results** > **Results to File**.
1. Execute the query.
1. In the **Save Results** dialog box, in **Save in**, select the folder where you want to save the file.
1. In **File name**, enter a file name.
1. In **Save as type**, choose the output file format.
1. Select **Save**.

By default, SSMS saves results as a report file with the `.rpt` extension. For advanced options, select the down arrow on the **Save** button, and then select **Save with Encoding**.

You can change the default location for saving results in **Tools** > **Options** > **Query Results** > **SQL Server** > **General** > **Query results directory**.

## Keyboard shortcuts

The following keyboard shortcuts change the results destination for the active Query Editor window.

| Destination | Keyboard shortcut |
| --- | --- |
| Results to grid | <kbd>Ctrl</kbd>+<kbd>D</kbd> |
| Results to text | <kbd>Ctrl</kbd>+<kbd>T</kbd> |
| Results to file | <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>F</kbd> |

After you select a destination with a shortcut, execute the query (for example, by pressing <kbd>F5</kbd>) to send the results to the chosen target.

## Related content

- [Query Editor (SQL Server Management Studio)](../f1-help/database-engine-query-editor-sql-server-management-studio.md)
