---
title: Collapse Groups of Rows
description: "Collapse Groups of Rows (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "group collapsing [SQL Server]"
  - "collapsing rows"
  - "row collapsing [SQL Server]"
---
# Collapse Groups of Rows (Visual Database Tools)
[!INCLUDE[SQL Server](../includes/applies-to-version/sqlserver.md)]
You can create a query result in which each result row corresponds to an entire group of rows from the original data. When collapsing rows, there are several things to keep in mind:  
  
-   **You can eliminate duplicate rows** Some queries can create result sets in which multiple identical rows appear. For example, you can create a result set in which each row contains the city and state name of a city containing an author - but if a city contains several authors, there will be several identical rows. The resulting SQL might look like this:  
  
    ```  
    SELECT city, state  
    FROM authors  
    ```  
  
    The result set generated by the preceding query is not very useful. If a city contains four authors, the result set will include four identical rows. Since the result set does not include any columns other than city and state, there is no way to distinguish the identical rows from each other. One way to avoid such duplicate rows is to include additional columns that can make the rows different. For example, if you include author name, each row will be different (provided no two like-named authors live within any one city). The resulting SQL might look like this:  
  
    ```  
    SELECT city, state, fname, minit, lname  
    FROM authors  
    ```  
  
    Of course, the preceding query eliminates the symptom, but does not really solve the problem. That is, the result set has no duplicates, but it is no longer a result set about cities. To eliminate duplicates in the original result set, and still have each row describe a city, you can create a query returning only distinct rows. The resulting SQL might look like this:  
  
    ```  
    SELECT DISTINCT city, state  
    FROM authors  
    ```  
  
    For details about eliminating duplicates, see [Exclude Duplicate Rows &#40;Visual Database Tools&#41;](exclude-duplicate-rows-visual-database-tools.md).  
  
-   **You can calculate on groups of rows** That is, you can summarize information in groups of rows. For example, you can create a result set in which each row contains the city and state name of a city containing an author, plus a count of the number of authors contained in that city. The resulting SQL might look like this:  
  
    ```  
    SELECT city, state, COUNT(*)  
    FROM authors  
    GROUP BY city, state  
    ```  
  
    For details about calculating on groups of rows, see [Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) and [Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md).  
  
-   **You can use selection criteria to include groups of rows** For example, you can create a result set in which each row contains the city and state name of a city containing several authors, plus a count of the number of authors contained in that city. The resulting SQL might look like this:  
  
    ```  
    SELECT city, state, COUNT(*)  
    FROM authors  
    GROUP BY city, state  
    HAVING COUNT(*) > 1  
    ```  
  
    For details about applying selection criteria on groups of rows, see [Specify Conditions for Groups &#40;Visual Database Tools&#41;](specify-conditions-for-groups-visual-database-tools.md) and [Use HAVING and WHERE Clauses in the Same Query &#40;Visual Database Tools&#41;](use-having-and-where-clauses-in-the-same-query-visual-database-tools.md).  
  
## See Also  
[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md)  
[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
