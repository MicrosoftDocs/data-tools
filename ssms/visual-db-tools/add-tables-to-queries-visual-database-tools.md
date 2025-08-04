---
title: Add Tables to Queries
description: "Add tables to queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "inserting tables"
  - "adding tables"
  - "queries [SQL Server], tables"
---

# Add tables to queries (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

When you create a query, you're retrieving data from a table or other objects structured like tables - views and certain user-defined functions. To work with any of these objects in your query, you add them to the **Diagram Pane**.

## Add a table or table-valued object to a query

1. In the **Diagram pane** of the Query and View Designer, right-click the background and choose **Add Table** from the shortcut menu.

1. In the **Add Table** dialog box, select the tab for the type of object you want to add to the query.

1. In the list of items, double-click each item you want to add.

1. When you finish adding items, select **Close**.

   The Query and View Designer updates the **Diagram Pane**, **Criteria Pane**, and **SQL Pane** accordingly.

Tables and views are automatically added to the query when you reference them in the statement in the SQL pane.

The Query and View Designer doesn't display data columns for a table or table-structured object if you don't have sufficient access rights to it or if the provider can't return information about it. In such cases, only a title bar and the * (All Columns) check box are displayed for the table or table-valued object.

## Add an existing query to a new query

1. Make sure the **SQL Pane** is displayed in the new query you're creating.

1. In the **SQL Pane**, type a right and left parentheses () after the word `FROM`.

1. Open the Query Designer for the existing query. (You now have two Query Designers open.)

1. Display the **SQL Pane** for the inner query - the existing query you're including in the new, outer query.

1. Select all the text in the **SQL Pane**, and copy it to the Clipboard.

1. Select in the **SQL Pane** of the new query, situate the cursor between the parentheses you added, and paste the contents of the Clipboard.

1. Still in the **SQL Pane**, add an alias after the right parenthesis.

## Related content

- [Create table aliases (Visual Database Tools)](create-table-aliases-visual-database-tools.md)
- [Remove tables from queries (Visual Database Tools)](remove-tables-from-queries-visual-database-tools.md)
- [Specify search criteria (Visual Database Tools)](specify-search-criteria-visual-database-tools.md)
- [Summarize query results (Visual Database Tools)](summarize-query-results-visual-database-tools.md)
- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
