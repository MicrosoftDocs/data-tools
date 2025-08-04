---
title: Rules for Updating Results
description: "Rules for updating results (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "View Designer, Results pane"
  - "updating query results"
  - "Query Designer [SQL Server], Results pane"
  - "Results pane"
---
# Rules for updating results (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

In many cases, you can update the result set displayed in the [Results pane (Visual Database Tools)](results-pane-visual-database-tools.md). However, in some cases you can't.

In general, in order to update results, the [Query and View Designer Tools (Visual Database Tools)](query-and-view-designer-tools-visual-database-tools.md) must have sufficient information to uniquely identify the row in the table. An example is if the query includes a primary key in the output list. In addition, you must have sufficient permission to update the database.

If your query is based on a view, you might be able to update it. The same guidelines apply, except that they apply to the underlying tables in the view, not just to the view itself.

> [!NOTE]  
> The Query and View Designer can't determine in advance whether you can update a result set based on a view. Therefore, it displays all views, even though you might not be able to update them.

The following table summarizes specific instances in which you might and might not be able to update query results in the Results pane. In many cases, the database you're using dictates whether you can update query results.

| Query | Can results be updated? |
| --- | --- |
| Query based on one table with primary key in the output list | Yes (except as listed below). |
| Query based on a table with no unique index and without a primary key | Depends on query and database. Some databases allow updates if sufficient information is available to uniquely identify records. |
| Query based on multiple tables which aren't joined | No. |
| Query based on data marked as read-only in the database | No. |
| Query based on a view that involves one table with no constraints | Yes (except as listed below). |
| Query based on tables joined with a one-to-one relationship | Yes (except as listed below). |
| Query based on tables joined with a one-to-many relationship | Usually. |
| Query based on three or more tables in which there's a many-to-many relationship | No. |
| Query based on a table for which update permission isn't granted | Can delete but not update. |
| Query based on a table for which delete permission isn't granted | Can update but not delete. |
| Aggregate query | No. |
| Query based on a subquery that contains totals or aggregate functions | No. |
| Query that includes the `DISTINCT` keyword to exclude duplicate rows | No. |
| Query whose `FROM` clause includes a user-defined function that returns a table and the user-defined function contains multiple select statements | No. |
| Query whose `FROM` clause includes an inline user-defined function | Yes. |

In addition, you might not be able to update specific columns in the query results. The following list summarizes specific types of columns that you can't update in the Results pane.

- Columns based on expressions
- Columns based on scalar user-defined functions
- Rows or columns deleted by another user
- Rows or columns locked by another user (locked rows can usually be updated as soon as they are unlocked)
- Timestamp or BLOB columns

## Related content

- [Design queries and views how-to articles (Visual Database Tools)](design-queries-and-views-how-to-topics-visual-database-tools.md)
