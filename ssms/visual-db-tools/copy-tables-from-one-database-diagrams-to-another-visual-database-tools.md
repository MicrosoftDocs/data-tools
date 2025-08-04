---
title: Copy Tables from One Database Diagram to Another
description: "Copy tables from one database diagram to another (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "copying tables"
  - "duplicating tables"
---
# Copy tables from one database diagram to another (Visual Database Tools)

[!INCLUDE [SQL Server Azure SQL Database PDW](../includes/applies-to-version/sql-asdb-asdbmi-pdw.md)]

You can copy a table from one database diagram to another in the same database.

Copying a table from one database diagram to another diagram adds a reference to the table in the second diagram. The table isn't duplicated in your database. For example, if you copy the `authors` table from one database diagram to another, each diagram references the same `authors` table in the database.

## Copy a table from another database diagram

1. Make sure you're connected to the database whose table you want to copy.

1. Open the source and target database diagrams and within the source diagram, select the table that you want to copy to the target diagram.

1. Select the **Copy** button on the toolbar. This action places the selected table definition on the Clipboard.

1. Switch to the target diagram. This diagram must be in the same database as the source diagram.

1. Select the **Paste** button on the toolbar. The Clipboard contents appear at the new location and remain highlighted until you select elsewhere. If relationships exist between the selected tables and other tables in the target diagram, relationship lines are automatically drawn.

When you edit the table in either diagram, your changes are reflected in both diagrams. Similarly, once you save the table in either diagram, the table is no longer considered "modified" in either diagram.

## Related content

- [Work with database diagrams (Visual Database Tools)](work-with-database-diagrams-visual-database-tools.md)
- [Add tables to diagrams (Visual Database Tools)](add-tables-to-diagrams-visual-database-tools.md)
