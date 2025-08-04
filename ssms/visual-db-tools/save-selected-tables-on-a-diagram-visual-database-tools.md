---
title: Save Selected Tables on a Diagram
description: "Save selected tables on a diagram (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "saving tables"
---
# Save selected tables on a diagram (Visual Database Tools)

[!INCLUDE [SQL Server Azure SQL Database PDW](../includes/applies-to-version/sql-asdb-asdbmi-pdw.md)]

You can save a specific table or a set of tables if you don't want to save all the changes you made in a database diagram.

## Save selected tables

1. In your database diagram, select the tables you want to save.

1. From the **File** menu, choose **Save Selection**.

1. The **Save** dialog box displays the list of tables that are updated in the database when you save your selection.

   Choose **Save Text File** if you want to save the list of tables in a text file in the project directory before continuing.

1. In the **Save** dialog box, confirm the list of tables and choose **Yes** to save these tables.

   > [!NOTE]  
   > The list of tables might contain tables in addition to those selected. For example, if you change the data type of a column that participates in a relationship with another table, both tables are included in this list.

## Related content

- [Work with database diagrams (Visual Database Tools)](work-with-database-diagrams-visual-database-tools.md)
