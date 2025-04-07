---
title: Create Full-Text Search Queries
description: "Create Full-Text Search Queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: conceptual
ms.collection:
  - data-tools
helpviewer_keywords:
  - "CONTAINS predicate (Transact-SQL)"
  - "queries [full-text search], creating"
  - "full-text queries [SQL Server], creating"
---
# Create Full-Text Search Queries (Visual Database Tools)
[!INCLUDE[SQL Server](../includes/applies-to-version/sqlserver.md)]
Full-text searches use the CONTAINS predicate to locate rows that have specified text in a given column. Full-Text searches are only possible on columns that have active full-text indexes. If you attempt to use the CONTAINS clause on a column that does not have a currently active full-text index, you will receive an error. For more information on full-text indexes and the CONTAINS clause, see [Full-Text Search (SQL Server)](/sql/relational-databases/search/full-text-search) and [CONTAINS (Transact-SQL)](/sql/t-sql/queries/contains-transact-sql).  
  
### To create a full-text search query  
  
1.  Open a query from Solution Explorer or create a new one.  
  
2.  In the WHERE clause of your query, use the CONTAINS function to search a full-text column.  
  
## See Also  
[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md)  
[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md)  
[Perform Basic Operations with Queries &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md)  
