---
title: Specify Multiple Search Conditions for Multiple Columns
description: "Specify Multiple Search Conditions for Multiple Columns (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: conceptual
ms.collection:
  - data-tools
helpviewer_keywords:
  - "search criteria [SQL Server], multiple conditions"
  - "multiple search conditions"
  - "search conditions [SQL Server], multiple"
  - "OR operator"
  - "AND, Criteria pane"
---
# Specify Multiple Search Conditions for Multiple Columns (Visual Database Tools)
[!INCLUDE[SQL Server](../includes/applies-to-version/sqlserver.md)]
You can expand or narrow the scope of your query by including several data columns as part of your search condition. For example, you might want to:  
  
-   Search for employees who either have worked more than five years at the company or who hold certain jobs.  
  
-   Search for a book that is both published by a specific publisher and pertains to cooking.  
  
To create a query that searches for values in either of two (or more) columns, you specify an OR condition. To create a query that must meet all conditions in two (or more) columns, you specify an AND condition.  
  
## Specifying an OR Condition  
To create multiple conditions linked with OR, you put each separate condition in a different column of the Criteria pane.  
  
#### To specify an OR condition for two different columns  
  
1.  In the [Criteria Pane](criteria-pane-visual-database-tools.md), add the columns you want to search.  
  
2.  In the **Filter** column for the first column to search, specify the first condition.  
  
3.  In the **Or...** column for the second data column to search, specify the second condition, leaving the **Filter** column blank.  
  
    The Query and View Designer creates a WHERE clause that contains an OR condition such as the following:  
  
    ```  
    SELECT job_lvl, hire_date  
    FROM employee  
    WHERE (job_lvl >= 200) OR   
      (hire_date < '01/01/1998')  
    ```  
  
4.  Repeat Steps 2 and 3 for each additional condition you want to add. Use a different **Or...** column for each new condition.  
  
## Specifying an AND Condition  
To search different data columns using conditions linked with AND, you put all the conditions in the **Filter** column of the grid.  
  
#### To specify an AND condition for two different columns  
  
1.  In the [Criteria Pane](criteria-pane-visual-database-tools.md), add the columns you want to search.  
  
2.  In the **Filter** column for the first data column to search, specify the first condition.  
  
3.  In the **Filter** column for the second data column, specify the second condition.  
  
    The Query and View Designer creates a WHERE clause that contains an AND condition such as the following:  
  
    ```  
    SELECT pub_id, title  
    FROM titles  
    WHERE (pub_id = '0877') AND (title LIKE '%Cook%')  
    ```  
  
4.  Repeat Steps 2 and 3 for each additional condition you want to add.  
  
## See Also  
[Combine Conditions When AND Has Precedence](combine-conditions-when-and-has-precedence-visual-database-tools.md)  
[Combine Conditions When OR Has Precedence](combine-conditions-when-or-has-precedence-visual-database-tools.md)  
[Conventions for Combining Search Conditions in the Criteria Pane](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md)  
[Specify Search Criteria](specify-search-criteria-visual-database-tools.md)  
  
