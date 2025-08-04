---
title: Results Pane
description: "Results pane (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "View Designer, Results pane"
  - "result sets [SQL Server], queries"
  - "synchronization [SQL Server], query results with definition"
  - "displaying query results in grid"
  - "grid showing query results [SQL Server]"
  - "showing query results in grid"
  - "Query Designer [SQL Server], Results pane"
  - "results [SQL Server], query"
  - "viewing query results"
  - "queries [SQL Server], results"
  - "Results pane"
---
# Results pane (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

The Results pane shows the results of the most recently executed `SELECT` query. (The results of other query types are displayed in message boxes.) To open the Results pane, open or create a query or view or return a table's data. If the Results pane doesn't show by default, from the **Query Designer** menu, point to **Pane**, and then select **Results**.

## What You Can Do in the Results pane

- View the result set for the most recently executed `SELECT` query in a spreadsheet-like grid.

- For queries or views that show data from a single table or view, you can edit the values in individual columns in the result set, add new rows, and delete existing rows.

## Limitations in the Results pane

- Results returned by table-valued functions can only be updated in some cases.

- Queries or views that include columns from more than one table or view can't be updated.

- Results returned by a stored procedure can't be updated.

- Queries or views using the `GROUP BY` or `DISTINCT` clauses aren't updatable.

## Navigate in the Results pane

You can quickly navigate through the records using the navigation bar at the bottom of the Results pane.

There are buttons for going to the first and last records, the next and previous records, and for going to a particular record.

To go to a particular record, type the number of the row in the text box in the navigation bar and then press ENTER.

For information about using keyboard shortcuts in the Query and View Designer see [Navigate in the Query and View Designer (Visual Database Tools)](navigate-in-the-query-and-view-designer-visual-database-tools.md).

## Keep the results set synchronized with the query definition

While you're working on the results of a query or view it's possible for the records in the Results pane to get out of synchronization with the query's definition. For example, if you run a query for four out of five columns in a table, and then use the Diagram pane to add the fifth column to the definition of the query, that fifth column's data isn't automatically be added to the Results pane. To make the Results pane reflect the new query definition, run the query again.

If a query changes, an alert icon and the text "Query Changed" appears in the lower-right corner of the Results pane. The icon is repeated in the upper-left corner of the pane.

## Related content

- [Create queries (Visual Database Tools)](create-queries-visual-database-tools.md)
- [Run queries (Visual Database Tools)](run-queries-visual-database-tools.md)
- [Design queries and views how-to articles (Visual Database Tools)](design-queries-and-views-how-to-topics-visual-database-tools.md)
- [Diagram pane (Visual Database Tools)](diagram-pane-visual-database-tools.md)
- [Criteria Pane (Visual Database Tools)](criteria-pane-visual-database-tools.md)
- [Work with data in the Results pane (Visual Database Tools)](work-with-data-in-the-results-pane-visual-database-tools.md)
