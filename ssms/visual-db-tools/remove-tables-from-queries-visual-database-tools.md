---
title: Remove Tables from Queries
description: "Remove Tables from Queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "deleting tables"
  - "removing tables"
  - "dropping tables"
  - "queries [SQL Server], tables"
---
# Remove Tables from Queries (Visual Database Tools)
[!INCLUDE[SQL Server](../includes/applies-to-version/sqlserver.md)]
You can remove a table - or any table-valued object - from the query.  
  
> [!NOTE]  
> Removing a table or table-valued object does not delete anything from the database; it only removes it from the current query. For details about removing a table from a database, see [How to: Delete Tables from a Database](/sql/relational-databases/tables/delete-tables-database-engine).  
  
### To remove a table or table-structured object  
  
-   In the **Diagram Pane**, select the table, view, user-defined function, synonym, or query, and then press DELETE, or right-click the object and then choose **Remove** in the resulting dialog box. You can select and remove multiple objects at one time.  
  
    -or-  
  
-   Remove all references to the object in the **SQL Pane.**  
  
When you remove a table or table-valued object, the Query and View Designer automatically removes joins that involve that table or table-valued object and removes references to the object's columns in the **SQL Pane** and **Criteria Pane**. However, if the query contains complex expressions involving the object, the object is not automatically removed until all references to it are removed.  
  
## See Also  
[Add Tables to Queries](add-tables-to-queries-visual-database-tools.md)  
[Create Table Aliases](create-table-aliases-visual-database-tools.md)  
[Specify Search Criteria](specify-search-criteria-visual-database-tools.md)  
[Summarize Query Results](summarize-query-results-visual-database-tools.md)  
[Perform Basic Operations with Queries](perform-basic-operations-with-queries-visual-database-tools.md)  
