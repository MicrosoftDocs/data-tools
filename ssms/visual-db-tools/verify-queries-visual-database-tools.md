---
title: Verify Queries
description: "Verify Queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
f1_keywords:
  - "vdtsql.chm:100644"
helpviewer_keywords:
  - "verifying queries"
  - "queries [SQL Server], verifying"
  - "checking queries"
---
# Verify Queries (Visual Database Tools)
[!INCLUDE[SQL Server](../includes/applies-to-version/sqlserver.md)]
To avoid problems, you can check the query you have built to ensure its syntax is correct. This option is especially useful when you enter statements in the [SQL pane](sql-pane-visual-database-tools.md).  
  
Some notes to keep in mind about verifying queries:  
  
-   A statement can be valid, and therefore be verified successfully, even if it cannot be represented in the **Diagram Pane** and **Criteria Pane**.  
  
-   SQL Verification can detect some, but not all SQL errors. If a query contains an error not detected during SQL verification, the database will detect the error when you run the query.  
  
-   Queries that contain parameters cannot be verified.  
  
### To verify a SQL statement  
  
-   Right-click in the **SQL Pane**, and select **Verify SQL Syntax** from the shortcut menu.  
  
## See Also  
[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md)  
[Perform Basic Operations with Queries &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md)  
  
