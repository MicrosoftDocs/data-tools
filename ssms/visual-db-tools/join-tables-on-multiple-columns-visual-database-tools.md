---
title: Join Tables on Multiple Columns
description: "Join Tables on Multiple Columns (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "multiple column joins"
  - "joins [SQL Server], multiple columns"
---
# Join Tables on Multiple Columns (Visual Database Tools)
[!INCLUDE[SQL Server](../includes/applies-to-version/sqlserver.md)]
You can join tables with multiple columns. That is, you can create a query that matches rows from the two tables only if they satisfy multiple conditions. If the database contains a relationship matching multiple foreign-key columns in one table to a multicolumn primary key in the other table, you can use this relationship to create a multicolumn join. For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md).  
  
Even if the database contains no multi-column foreign-key relationship, you can create the join manually.  
  
### To manually create a multicolumn join  
  
1.  Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the tables you want to join.  
  
2.  Drag the name of the first join column in the first table window and drop it onto the related column in the second table window. You cannot base a join on text, ntext, or image columns.  
  
    > [!NOTE]  
    > In general, the join columns must be of the same (or compatible) data types. For example, if the join column in the first table is a date, you must relate it to a date column in the second table. On the other hand, if the first join column is an integer, the related join column must also be of an integer data type, but it can be a different size. However, there may be cases where implicit data type conversions can join seemingly incompatible columns will work.  
    >   
    > The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) will not check the data types of the columns you use to create a join, but when you execute the query, the database will display an error if the data types are not compatible.  
  
3.  Drag the name of the second join column in the first table window and drop it onto the related column in the second table window.  
  
4.  Repeat step 3 for each additional pair of join columns in the two tables.  
  
5.  Run the query.  
  
## See Also  
[Query with Joins &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md)  
  
