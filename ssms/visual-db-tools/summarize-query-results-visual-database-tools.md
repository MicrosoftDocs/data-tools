---
title: Summarize Query Results
description: "Summarize Query Results (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "summarizing query results"
  - "queries [SQL Server], results"
  - "aggregate queries [SQL Server]"
---
# Summarize Query Results (Visual Database Tools)
[!INCLUDE[SQL Server](../includes/applies-to-version/sqlserver.md)]
When you create aggregate queries, certain logical principles apply. For example, you cannot display the contents of individual rows in a summary query. The Query and View Designer helps you comply with these principles in the way the [Diagram pane](diagram-pane-visual-database-tools.md) and [Criteria pane](criteria-pane-visual-database-tools.md) behave.  
  
By understanding the principles of aggregate queries and the Query and View Designer's behavior, you can create logically correct aggregate queries. The overriding principle is that aggregate queries can result only in summary information. Thus, most of the principles that follow describe the ways that you can reference individual data columns within an aggregate query.  
  
## In This Section  
[Work with Columns in Aggregate Queries &#40;Visual Database Tools&#41;](work-with-columns-in-aggregate-queries-visual-database-tools.md)  
Describes concepts about grouping and summarizing columns with the GROUP BY, WHERE, and HAVING clauses.  
  
[Count Rows in a Table &#40;Visual Database Tools&#41;](count-rows-in-a-table-visual-database-tools.md)  
Provides steps for counting the number of rows in a table or the number of rows in a table that meet a set of criteria.  
  
[Summarize or Aggregate Values for All Rows in a Table &#40;Visual Database Tools&#41;](summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md)  
Provides steps for summarizing all rows rather than for a set of grouped rows.  
  
[Summarize or Aggregate Values Using Custom Expressions &#40;Visual Database Tools&#41;](summarize-or-aggregate-values-using-custom-expressions-visual-database-tools.md)  
Provides steps for using expressions to summarize or aggregate rather than using the predefined clauses.  
  
## Related Sections  
[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md)  
Provides links to topics covering how to use the Query and View Designer.  
  
