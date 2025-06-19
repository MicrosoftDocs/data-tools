---
title: Sort with ORDER BY
description: "Sort with ORDER BY (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "ORDER BY clause [Visual Database Tools]"
---
# Sort with ORDER BY (Visual Database Tools)
[!INCLUDE[SQL Server](../includes/applies-to-version/sqlserver.md)]
You can sort query results by one or more of the columns in the returned rows by using an ORDER BY clause. You can define an ORDER BY clause by choosing options in the Criteria Details pane.  
  
### To sort a query using an ORDER BY clause  
  
1.  Open a query or create a new one.  
  
2.  In the [Criteria Pane](criteria-pane-visual-database-tools.md), click the **Sort Type** column for the row corresponding to the column that you want to use to sort your query results.  
  
3.  Choose *Ascending* or *Descending* from the drop-down list.  
  
> [!NOTE]  
> Clearing the **Sort Type** entry for a column removes that column from the ORDER BY clause.  
  
Notice that as you work in the Criteria pane, your query's UNION clause changes to match your most recent actions.  
  
> [!NOTE]  
> When sorting results by more than one column, specify the order in which columns are searched relative to each other by using the **Sort Order** column. For more information, see **How to: Sort Multiple Columns in Queries**.  
  
## See Also  
[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md)  
[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md)  
[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
