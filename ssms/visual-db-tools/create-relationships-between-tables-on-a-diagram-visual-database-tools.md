---
title: Create Relationships Between Tables on a Diagram
description: "Create relationships between tables on a diagram (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "diagrams [SQL Server], designing"
---
# Create relationships between tables on a diagram (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can create relationships between columns in different tables in the Diagram Designer by dragging columns between tables.

## Create a relationship graphically

1. In Database Designer, select the row selector for one or more database columns that you want to relate to a column in another table.

1. Drag the selected columns to the related table.

1. Two dialog boxes appear: **Foreign Key Relationship** and **Tables and Columns**, with the latter appearing in the foreground.

1. **Relationship name** has a system-provided name in the format FK_*localtable*\_*foreigntable*. You might change this value.

1. Verify that **Primary key table** specifies the correct table.

1. The grid lists the local columns and their matching foreign columns. You can add or remove table columns or change mappings.

1. Choose **OK**.

   The **Foreign Key Relationship** dialog box appears. **Selected Relationship** shows the relationship you have created.

1. Change properties for the relationship in the grid.

1. Choose **OK** to create the relationship.

   Database Designer shows a relationship between the columns you chose.

## Related content

- [Unique constraints and check constraints](/sql/relational-databases/tables/unique-constraints-and-check-constraints)
- [Work with tables in database diagrams (Visual Database Tools)](work-with-tables-in-database-diagram-visual-database-tools.md)
