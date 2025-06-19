---
title: Map Many-to-Many Relationships
description: "Map Many-to-Many Relationships (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "relationships [SQL Server], many-to-many"
  - "junction tables [SQL Server]"
  - "many-to-many relationships [SQL Server]"
  - "mapping many-to-many relationships [SQL Server]"
  - "database diagrams [SQL Server], relationships"
---
# Map Many-to-Many Relationships (Visual Database Tools)

[!INCLUDE[SQL Server Azure SQL Database PDW](../includes/applies-to-version/sql-asdb-asdbmi-pdw.md)]

Many-to-many relationships let you relate each row in one table to many rows in another table, and vice versa. For example, you could create a many-to-many relationship between the `authors` table and the `titles` table to match each author to all of their books and to match each book to all of its authors. Creating a one-to-many relationship from either table would incorrectly indicate that every book can have only one author, or that every author can write only one book.  
  
Many-to-many relationships between tables are accommodated in databases by means of junction tables. A junction table contains the primary key columns of the two tables you want to relate. You then create a relationship from the primary key columns of each of those two tables to the matching columns in the junction table. In the pubs database, the `titleauthor` table is a junction table.  
  
### To create a many-to-many relationship between tables  
  
1.  In your database diagram, add the tables that you want to create a many-to-many relationship between.  
  
2.  Create a third table by right-clicking the diagram and choosing **New Table** from the shortcut menu. This will become the junction table.  
  
3.  In the **Choose Name** dialog box, change the system-assigned table name. For example, the junction table between the `titles` table and the `authors` table is now named `titleauthors`.  
  
4.  Copy the primary key columns from each of the other two tables to the junction table. You can add other columns to this table, just as you can to any other table.  
  
5.  In the junction table, set the primary key to include all the primary key columns from the other two tables. For details, see [How to: Create Primary Keys](/sql/relational-databases/tables/create-primary-keys).  
  
6.  Define a one-to-many relationship between each of the two primary tables and the junction table. The junction table should be at the "many" side of both of the relationships you create. For details, see [How to: Create Relationships Between Tables](/sql/relational-databases/tables/create-foreign-key-relationships).  
  
    > [!NOTE]  
    > The creation of a junction table in a database diagram does not insert data from the related tables into the junction table. For information about inserting data into a table, see [Create Insert Results Queries &#40;Visual Database Tools&#41;](create-insert-results-queries-visual-database-tools.md).  
  
## See Also  
[Work with Database Diagrams &#40;Visual Database Tools&#41;](work-with-database-diagrams-visual-database-tools.md)  
