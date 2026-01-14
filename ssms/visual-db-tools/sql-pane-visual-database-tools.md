---
title: SQL Pane
description: "SQL Pane (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "Query Designer [SQL Server], SQL pane"
  - "View Designer, SQL pane"
  - "SQL pane [Visual Database Tools]"
---
# SQL Pane (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can use the SQL pane to create your own SQL statement, or you can use the Criteria pane and Diagram pane to create the statement, in which case the SQL statements are created in the SQL pane. As you build your query, the SQL pane automatically updates and reformats for easy readability.

To open the SQL pane, first open Query and View Designer (with a database object selected in Server Explorer, from the **Database** menu, select **New Query**). Then from the **Query Designer** menu point to **Pane** and select **SQL**.

In the SQL pane you can:

- Create new queries by entering SQL statements.

- Modify the SQL statement created by the Query and View Designer based on settings you make in the Diagram and Criteria panes.

- Enter statements that take advantage of features specific to the database you're using.

> [!NOTE]  
> Be sure you know the rules for identifying database objects in the database you're using. For details, see the documentation for your database management system.

## Statements in the SQL Pane

You can edit the current query directly in the SQL pane. When you move to another pane, the Query and View Designer automatically formats your statement, and then changes the Diagram and Criteria panes to match your statement.

If your statement can't be represented in the Diagram and Criteria panes, and if those panes are visible, Query and View Designer displays an error and then offers you two choices:

- Ignore that the statement cannot be represented in the Diagram and Criteria panes.

- Undo the change that cannot be represented and revert to the most recent version of the SQL statement.

If you choose to ignore that the statement cannot be represented in the Diagram and Criteria panes, the Query and View Designer dims the other panes to indicate that they no longer reflect the contents of the SQL pane.

You can continue to edit the statement and execute it as you would any SQL statement.

> [!NOTE]  
> If you enter a SQL statement, but then make further changes to the query by changing the Diagram and Criteria panes, the Query and View Designer rebuilds and redisplays the SQL statement. In some cases, this action results in a SQL statement that is constructed differently from the one you originally entered (though it always yields the same results). This difference is particularly likely when you're working with search conditions that involve several clauses linked with `AND` and `OR`.

## Related content

- [Create queries (Visual Database Tools)](create-queries-visual-database-tools.md)
- [Run queries (Visual Database Tools)](run-queries-visual-database-tools.md)
- [Design queries and views how-to articles (Visual Database Tools)](design-queries-and-views-how-to-topics-visual-database-tools.md)
- [Diagram pane (Visual Database Tools)](diagram-pane-visual-database-tools.md)
- [Criteria Pane (Visual Database Tools)](criteria-pane-visual-database-tools.md)
- [Results pane (Visual Database Tools)](results-pane-visual-database-tools.md)
