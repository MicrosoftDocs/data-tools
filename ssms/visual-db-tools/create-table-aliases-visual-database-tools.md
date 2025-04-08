---
title: Create Table Aliases
description: "Create Table Aliases (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: conceptual
ms.collection:
  - data-tools
helpviewer_keywords:
  - "table aliases [SQL Server]"
  - "aliases [SQL Server], tables"
---
# Create Table Aliases (Visual Database Tools)
[!INCLUDE[SQL Server](../includes/applies-to-version/sqlserver.md)]
Aliases can make it easier to work with table names. Using aliases is helpful when:  
  
-   You want to make the statement in the [SQL Pane](sql-pane-visual-database-tools.md) shorter and easier to read.  
  
-   You refer to the table name often in your query - such as in qualifying column names - and want to be sure you stay within a specific character-length limit for your query. (Some databases impose a maximum length for queries.)  
  
-   You are working with multiple instances of the same table (such as in a self-join) and need a way to refer to one instance or the other.  
  
For example, you can create an alias `"e"` for a table name `employee_information`, and then refer to the table as `"e"` throughout the rest of the query.  
  
### To create an alias for a table or table-valued object  
  
1.  Add the table or table-valued object to your query.  
  
2.  In the **Diagram Pane**, right-click the object for which you want to create an alias, then select **Properties** from the shortcut menu.  
  
3.  In the **Properties** window, enter the alias in the **Alias** field.  
  
## See Also  
[Add Tables to Queries &#40;Visual Database Tools&#41;](add-tables-to-queries-visual-database-tools.md)  
[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md)  
[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md)  
[Perform Basic Operations with Queries &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md)  
  
