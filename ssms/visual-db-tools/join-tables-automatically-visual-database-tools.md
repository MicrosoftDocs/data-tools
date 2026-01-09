---
title: Join Tables Automatically
description: "Join tables automatically (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "automatic joins"
  - "joins [SQL Server], creating"
  - "joins [SQL Server], automatic"
---
# Join tables automatically (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

When you add two or more tables to a query, the [Query and View Designer Tools (Visual Database Tools)](query-and-view-designer-tools-visual-database-tools.md) attempts to determine if they are related. If they are, the Query and View Designer automatically puts join lines between the rectangles representing the tables or table-structured objects.

The Query and View Designer recognizes tables as joined if:

- The database contains information that specifies that the tables are related.

- If two columns, one in each table, have the same name and data type. The column must be a primary key in at least one of the tables. For example, if you add `employee` and `jobs` tables, if the `job_id` column is the primary key in the `jobs` table, and if each table has a column called `job_id` with the same data type, the Query and View Designer automatically joins the tables.

  > [!NOTE]  
  > The Query and View Designer creates only one join based on columns with the same name and data type. If more than one join is possible, the Query and View Designer stops after creating a join based on the first set of matching columns that it finds.

- The Query and View Designer detects that a search condition (a `WHERE` clause) is actually a join condition. For example, you might add the tables `employee` and `jobs`, then create a search condition that searches for the same value in the `job_id` column of both tables. When you do, the Query and View Designer detects that the search condition results in a join, and then creates a join condition based on the search condition.

If the Query and View Designer has created a join that isn't suitable to your query, you can modify the join or remove it. For details, see [Modify join operators (Visual Database Tools)](modify-join-operators-visual-database-tools.md) and [Remove joins (Visual Database Tools)](remove-joins-visual-database-tools.md).

If the Query and View Designer doesn't automatically join the tables in your query, you can create a join yourself. For details, see [Join tables manually (Visual Database Tools)](join-tables-manually-visual-database-tools.md).

## Related content

- [How the Query and View Designer represents joins (Visual Database Tools)](how-the-query-and-view-designer-represents-joins-visual-database-tools.md)
- [Design queries and views how-to articles (Visual Database Tools)](design-queries-and-views-how-to-topics-visual-database-tools.md)
- [Query with joins (Visual Database Tools)](query-with-joins-visual-database-tools.md)
