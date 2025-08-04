---
title: Specify the TOP Clause in Queries
description: "Specify the TOP clause in queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "TOP clause, queries"
  - "percentage of rows returned [SQL Server]"
  - "number of rows"
  - "search conditions [SQL Server], TOP clause"
  - "restricting rows returned"
  - "search criteria [SQL Server], limiting rows returned"
  - "inspecting portion of results"
  - "limiting rows returned"
  - "search criteria [SQL Server], TOP clause"
---
# Specify the TOP clause in queries (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

The `TOP` clause returns only the first *n* or *n percent* rows from a query. The `TOP` clause is useful when you want to inspect a portion of your results to find out if your query does what you expect it to do, without taking the resources necessary to return all of the query results.

## Specify the TOP clause in queries

1. Open a query from Solution Explorer or create a new one.

1. From the **View** menu, select **Properties Window**.

1. In the **Properties Window**, locate and expand the **Top Specification** property.

1. Select the **(Top)** child property and set it to **Yes**.

1. In the **Expression** child property, type an expression that has a numeric result (for example, "10" or "2*5").

1. Select the **Percent** child property and indicate whether or not to treat the **Expression** property as a percentage of all rows returned (Yes) or as the absolute number of rows returned (No).

1. If your query uses the `ORDER BY` clause, select the **With Ties** child property and choose **Yes** to display all rows in a group if only part of the group is included or **No** to truncate them.

As you work through the preceding procedure, notice that the `TOP` clause, displayed in the SQL pane, changes to reflect the current settings of the properties.

> [!NOTE]  
> You can also change the values of the child properties of the **Top Specification** by editing the `TOP` clause in the SQL pane.

## Related content

- [Design queries and views how-to articles (Visual Database Tools)](design-queries-and-views-how-to-topics-visual-database-tools.md)
- [Query Properties (Visual Database Tools)](query-properties-visual-database-tools.md)
