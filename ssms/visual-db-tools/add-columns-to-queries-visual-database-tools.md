---
title: Add Columns to Queries
description: "Add columns to queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "inserting columns"
  - "columns [SQL Server], adding"
  - "queries [SQL Server], columns"
  - "adding columns"
---

# Add columns to queries (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

To use a column in a query, you must add it to the query. You might add a column to display it in query output, to use it for sorting, to search the contents of the column, or to summarize its contents. You can decide which of the columns you use in the query are included in the results pane when the query is run. For more information see [Remove columns from query results](remove-columns-from-query-results-visual-database-tools.md).

> [!NOTE]  
> To view the data type of a column in Query and View Designer; select the table or table-valued object in the **Diagram Pane** and in the properties window select Column List. Then select the **ellipses (...)** to open the **Column List** dialog box.

Wherever you use a column in a query, you can also use an expression that can consist of any combination of columns, literals, operators, and functions.

## Add an individual column

- In the **Diagram Pane**, select the check box next to the column that you want to include.

  -or-

- In the **Criteria Pane**, move to the first blank grid row, select the field in the **Column** column, and select a column name from the dropdown list.

## Add all columns for one table or table-valued object

- In the **Diagram Pane**, select the check box next to **&#42;(All Columns)**.

## Add all columns for all tables and table-structured objects

1. Make sure no join lines in the **Table Operations Pane** are selected.

1. Right-click in the empty space of the Design window and choose **Properties** from the shortcut menu.

1. In the Properties window select **Output all columns** and choose **Yes** or **No** from the dropdown list.

## Related content

- [Remove columns from query results (Visual Database Tools)](remove-columns-from-query-results-visual-database-tools.md)
- [Remove columns from queries (Visual Database Tools)](remove-columns-from-queries-visual-database-tools.md)
- [Specify search criteria (Visual Database Tools)](specify-search-criteria-visual-database-tools.md)
- [Summarize query results (Visual Database Tools)](summarize-query-results-visual-database-tools.md)
- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
