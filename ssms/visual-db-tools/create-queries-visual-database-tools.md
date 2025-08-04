---
title: Create Queries
description: "Create queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "queries [SQL Server], creating"
---
# Create queries (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

Queries allow you to retrieve data from the tables and views in your database. You create and work with queries in **Query and View Designer**, which is composed of four panes: the [Diagram pane (Visual Database Tools)](diagram-pane-visual-database-tools.md), the [SQL Pane (Visual Database Tools)](sql-pane-visual-database-tools.md), the [Criteria Pane (Visual Database Tools)](criteria-pane-visual-database-tools.md), and the [Results pane (Visual Database Tools)](results-pane-visual-database-tools.md).

## Create a new query

1. In **Object Explorer**, expand the **Tables** node for the database you want to query. Right-click the table you want to query and select **Open Table**.

1. To add more tables to the query, on the Query Designer menu, select **Add Table**.

   > [!NOTE]  
   > If you don't see the **Diagram**, **SQL**, **Criteria**, or **Results** panes, from the Query Designer menu, point to **Pane** and select the pane you want to open.

1. In the **Add Table** dialog box, select the tables you want to query and select **Add** for each one.

1. Once you have added all the tables you want to query, select **Close**.

   To add more tables later, right-click the open space in the **Diagram** pane and from the shortcut menu select **Add Table**.

1. In the **Diagram Pane**, check the boxes in the table-valued objects for each column you want to query.

1. From the Query Designer menu, choose **Execute SQL** to run your query.

To further refine your query, you can change the SQL code in the **SQL Pane** or choose options such as sort order and column aliases in the **Criteria Pane.**

## Related content

- [Save queries (Visual Database Tools)](save-queries-visual-database-tools.md)
- [Types of queries (Visual Database Tools)](types-of-queries-visual-database-tools.md)
- [Specify search criteria (Visual Database Tools)](specify-search-criteria-visual-database-tools.md)
- [Summarize query results (Visual Database Tools)](summarize-query-results-visual-database-tools.md)
- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
