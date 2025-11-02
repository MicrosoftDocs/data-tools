---
title: Add Tables to Diagrams
description: "Add tables to diagrams (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "inserting tables"
  - "adding tables"
---

# Add tables to diagrams (Visual Database Tools)

[!INCLUDE [SQL Server Azure SQL Database PDW](../includes/applies-to-version/sql-asdb-asdbmi-pdw.md)]

You can add a table to your database diagram to edit its structure or relate it to other tables in your diagram. You can either add existing database tables to a diagram or insert a new table that hasn't yet been defined in the database.

## Insert a new table into a diagram

1. Make sure you're connected to the database in which you want to create the table.

   To create a table in your current diagram, select the **New Table** button on the toolbar.

   -or-

   Right-click in the diagram and select **New Table**.

1. Modify or accept the system-assigned table name, in the **Choose Name** dialog box, and then choose **OK**.

   A new table appears in the diagram in Standard view.

1. In the first cell of the new table, type a column name. Then press the **Tab** key to move to the next cell.

1. Under **Data Type**, select a data type for the column. Each column must have a name and data type.

   You can set the column's other properties in Table Designer.

1. Repeat steps 3 and 4 for each column you want to add to the table.

> [!NOTE]  
> When you save your database diagram, the new table is added to your database.

## Add an existing table to a diagram

1. Make sure you're connected to the database whose tables you want to edit.

1. Select a table in the **Tables** folder.

1. Drag the table into your database diagram.

1. Release the mouse button.

> [!NOTE]  
> If relationships exist between the selected table and other tables in your diagram, relationship lines are automatically drawn.

## Add related tables to a diagram

1. Select one or more tables with foreign key constraints in the database diagram.

1. Right-click any of the selected tables and choose **Add Related Tables**.

> [!NOTE]  
> Both those tables referenced by a foreign key constraint from the selected tables and those referencing the selected tables with a foreign key constraint are added to the diagram.

## Related content

- [Work with database diagrams (Visual Database Tools)](work-with-database-diagrams-visual-database-tools.md)
- [Work with tables in database diagrams (Visual Database Tools)](work-with-tables-in-database-diagram-visual-database-tools.md)
