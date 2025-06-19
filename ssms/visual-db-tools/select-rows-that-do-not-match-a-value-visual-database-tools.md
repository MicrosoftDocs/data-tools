---
title: Select Rows That Do Not Match a Value
description: "Select Rows That Do Not Match a Value (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "search conditions [SQL Server], rows not matching value"
  - "row not matching value [SQL Server]"
  - "NOT operator [Visual Database Tools]"
  - "search criteria [SQL Server], rows not matching value"
---
# Select Rows That Do Not Match a Value (Visual Database Tools)
[!INCLUDE[SQL Server](../includes/applies-to-version/sqlserver.md)]
To find rows that do not match a value, use the NOT operator.  
  
### To find rows that do not match a value  
  
1.  If you have not done so already, add the columns or expressions that you want to use within your search condition to the [Criteria pane](criteria-pane-visual-database-tools.md).  
  
2.  Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter the NOT operator followed by a search value.  
  
For example, to find all the rows in a `products` table where the values in the product code column begin with a character other than "A," you can enter a search condition such as the following:  
  
```  
NOT LIKE 'A%'  
```  
  
## See Also  
[Rules for Entering Search Values](rules-for-entering-search-values-visual-database-tools.md)  
[Specify Search Criteria](specify-search-criteria-visual-database-tools.md)  
  
