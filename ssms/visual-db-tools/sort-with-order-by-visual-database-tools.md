---
title: Sort with ORDER BY
description: "Sort with ORDER BY (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "ORDER BY clause [Visual Database Tools]"
---
# Sort with ORDER BY (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can sort query results by one or more of the columns in the returned rows by using an `ORDER BY` clause. You can define an `ORDER BY` clause by choosing options in the Criteria Details pane.

## Sort a query using an ORDER BY clause

1. Open a query or create a new one.

1. In the [Criteria Pane (Visual Database Tools)](criteria-pane-visual-database-tools.md), select the **Sort Type** column for the row corresponding to the column that you want to use to sort your query results.

1. Choose *Ascending* or *Descending* from the dropdown list.

> [!NOTE]  
> Clearing the **Sort Type** entry for a column removes that column from the `ORDER BY` clause.

As you work in the Criteria pane, your query's `UNION` clause changes to match your most recent actions.

> [!NOTE]  
> When sorting results by more than one column, specify the order in which columns are searched relative to each other by using the **Sort Order** column. For more information, see **How to: Sort Multiple Columns in Queries**.

## Related content

- [Sort and group query results (Visual Database Tools)](sort-and-group-query-results-visual-database-tools.md)
- [Summarize query results (Visual Database Tools)](summarize-query-results-visual-database-tools.md)
- [Design queries and views how-to articles (Visual Database Tools)](design-queries-and-views-how-to-topics-visual-database-tools.md)
