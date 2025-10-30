---
title: Remove Tables from Database Diagrams
description: "Remove tables from database diagrams (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "deleting tables"
  - "removing tables"
  - "dropping tables"
---
# Remove tables from database diagrams (Visual Database Tools)

[!INCLUDE [SQL Server Azure SQL Database PDW](../includes/applies-to-version/sql-asdb-asdbmi-pdw.md)]

You can remove a table from your database diagram. Removing a table doesn't alter your database. The table and its relationships to other tables continue to exist in the database.

## Remove a table from a database diagram

1. In your database diagram, select the table you want to remove.

1. Right-click the table and choose **Remove Table from Diagram** from the shortcut menu.

   -or-

   Press the **Esc** key.

   If the table has unsaved changes as a result of edits you made in the database diagram, a message prompts you to save the table before removing it.

The table is removed from your diagram but it continues to exist in the database.

## Related content

- [Work with database diagrams (Visual Database Tools)](work-with-database-diagrams-visual-database-tools.md)
