---
title: Combine Conditions When AND Has Precedence
description: "Combine Conditions When AND Has Precedence (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: conceptual
ms.collection:
  - data-tools
helpviewer_keywords:
  - "search conditions [SQL Server], combining"
  - "precedence [SQL Server], Criteria pane"
  - "search criteria [SQL Server], combining conditions"
  - "combining search conditions"
  - "AND, Criteria pane"
---

# Combine Conditions When AND Has Precedence (Visual Database Tools)

[!INCLUDE[SQL Server](../includes/applies-to-version/sqlserver.md)]

To combine conditions with AND, you add the column to the query twice--once for each condition. To combine conditions with OR, you put the first one in the Filter column and additional conditions into an **Or...** column.  
  
For example, imagine that you want to find either employees who have been with the company for more than five years in lower-level jobs or employees with middle-level jobs regardless of their hire date. This query requires three conditions, two of them linked with AND:  
  
-   Employees with a hire date earlier than five years ago AND with a job level of 100.  
  
    -or-  
  
-   Employees with a job level of 200.  
  
## To combine conditions when AND has precedence  
  
1.  In the [Criteria pane](criteria-pane-visual-database-tools.md), add the data columns you want to search. If you want to search the same column using two or more conditions linked with AND, you must add the data column name to the grid once for each value you want to search.  
  
2.  In the **Filter** column, enter all the conditions that you want to link with AND. For example, to link conditions with AND that search the `hire_date` and `job_lvl` columns, enter the values `< '1/1/91'` and `= 100`, respectively, in the Filter column.  
  
    These grid entries produce the following WHERE clause in the statement in the [SQL Pane](sql-pane-visual-database-tools.md):  
  
    ```  
    WHERE (hire_date < '01/01/91') AND  
      (job_lvl = 100)  
    ```  
  
3.  In the **Or...** grid column, enter conditions that you want to link with OR. For example, to add a condition that searches for another value in the `job_lvl` column, enter an additional value in the **Or...** column, such as `= 200`.  
  
    Adding a value in the **Or...** column adds another condition to the WHERE clause in the statement in the SQL pane:  
  
    ```  
    WHERE (hire_date < '01/01/91' ) AND  
      (job_lvl = 100) OR   
      (job_lvl = 200)  
    ```  
  
## See Also

[Combine Conditions When OR Has Precedence](combine-conditions-when-or-has-precedence-visual-database-tools.md)  
[Conventions for Combining Search Conditions in the Criteria Pane](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md)  
[Rules for Entering Search Values](rules-for-entering-search-values-visual-database-tools.md)  
[Specify Search Criteria](specify-search-criteria-visual-database-tools.md)
