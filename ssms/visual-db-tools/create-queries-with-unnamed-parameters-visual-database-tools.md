---
title: Create Queries with Unnamed Parameters
description: "Create Queries with Unnamed Parameters (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: conceptual
ms.collection:
  - data-tools
helpviewer_keywords:
  - "unnamed parameters"
  - "parameters [SQL Server], unnamed"
---
# Create Queries with Unnamed Parameters (Visual Database Tools)
[!INCLUDE[SQL Server](../includes/applies-to-version/sqlserver.md)]
You can create a query with an unnamed parameter by specifying a question mark (?) as a placeholder for a literal value. Query and View Designer will give it a temporary name. You can specify as many unnamed parameters in the query as you need.  
  
When you run the query in the Query and View Designer, the Query Parameters Dialog Box is displayed with the temporary name.  
  
### To specify an unnamed parameter  
  
1.  Add the columns or expressions that you want to search to the [Criteria pane](criteria-pane-visual-database-tools.md). If you do not want the search columns or expressions to appear in the query output, remove them as output columns.  
  
2.  Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter a question mark (?).  
  
    By default, the Query and View Designer adds the "=" operator. However, you can edit the cell to substitute ">", "<", or any other SQL comparison operator.  
  
## See Also  
[Query with Parameters &#40;Visual Database Tools&#41;](query-with-parameters-visual-database-tools.md)  
  
