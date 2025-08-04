---
title: Specify Conditions for Groups
description: "Specify conditions for groups (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "HAVING clause, query groups"
  - "group query conditions [SQL Server]"
---
# Specify conditions for groups (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can limit the groups that appear in a query by specifying a condition that applies to groups as a whole - a `HAVING` clause. After the data has been grouped and aggregated, the conditions in the `HAVING` clause are applied. Only the groups that meet the conditions appear in the query.

For example, you might want to see the average price of all books for each publisher in a `titles` table, but only if the average price exceeds $10.00. In that case, you could specify a `HAVING` clause with a condition such as `AVG(price) > 10`.

> [!NOTE]  
> In some instances, you might want to exclude individual rows from groups before applying a condition to groups as a whole. For details, see [Use HAVING and WHERE clauses in the same query (Visual Database Tools)](use-having-and-where-clauses-in-the-same-query-visual-database-tools.md).

You can create complex conditions for a `HAVING` clause by using `AND` and `OR` to link conditions. For details about using `AND` and `OR` in search conditions, see [Specify multiple search conditions for one column (Visual Database Tools)](specify-multiple-search-conditions-for-one-column-visual-database-tools.md).

## Specify a condition for a group

1. Specify the groups for your query. For details, see [Group Rows in Query Results (Visual Database Tools)](group-rows-in-query-results-visual-database-tools.md).

1. If it's not already in the [Criteria Pane (Visual Database Tools)](criteria-pane-visual-database-tools.md), add the column on which you want to base the condition. (Most often the condition involves a column that is already a group or summary column.) You can't use a column that isn't part of an aggregate function or of the `GROUP BY` clause.

1. In the **Filter** column, specify the condition to apply to the group.

   The [Query and View Designer Tools (Visual Database Tools)](query-and-view-designer-tools-visual-database-tools.md) automatically creates a `HAVING` clause in the statement in the [SQL Pane (Visual Database Tools)](sql-pane-visual-database-tools.md), such as in the following example:

   ```sql
   SELECT pub_id,
          AVG(price)
   FROM titles
   GROUP BY pub_id
   HAVING (AVG(price) > 10);
   ```

1. Repeat steps 2 and 3 for each additional condition you want to specify.

## Related content

- [Sort and group query results (Visual Database Tools)](sort-and-group-query-results-visual-database-tools.md)
