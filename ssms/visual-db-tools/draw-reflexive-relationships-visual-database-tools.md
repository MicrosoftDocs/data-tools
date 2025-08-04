---
title: Draw Reflexive Relationships
description: "Draw reflexive relationships (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "drawing reflexive relationships"
  - "reflexive relationships"
  - "database diagrams [SQL Server], relationships"
---
# Draw reflexive relationships (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You create a reflexive relationship to link a column or columns in a table with another column or columns in the same table. For example, suppose the `employee` table has an `emp_id` column and a `mgr_id` column. Because each manager is also an employee, you relate these two columns by drawing a relationship line from the table to itself. This relationship ensures each manager ID that is added to the table matches an existing employee ID.

Before you create a relationship, you must first define a primary key or unique constraint for your table. You then relate the primary key column to a matching column. Once you create the relationship, the matching column becomes a foreign key of the table.

## Draw a reflexive relationship

1. In your database diagram, select the row selector for the database column that you want to relate to another column and drag the pointer outside the table until a line appears.

1. Drag the line back to the selected table.

1. Release the mouse button. The **Tables and Columns** dialog box appears.

1. Select the foreign key column and the primary key table and column with which you want form a relationship.

1. Choose **OK** twice to create the relationship.

When you run queries against a table, you can use a reflexive relationship to create a self-join. For information about querying tables with joins, see [Query with joins](query-with-joins-visual-database-tools.md).

## Related content

- [Query with joins (Visual Database Tools)](query-with-joins-visual-database-tools.md)
