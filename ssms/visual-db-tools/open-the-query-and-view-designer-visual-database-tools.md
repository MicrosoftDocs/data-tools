---
title: Open the Query and View Designer
description: Open the Query and View Designer (Visual Database Tools)
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "opening View Designer"
  - "View Designer, opening"
  - "Query Designer [SQL Server], opening"
  - "opening Query Designer"
---

# Open the Query and View Designer (Visual Database Tools)

[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../includes/applies-to-version/sql-asdb-asdbmi.md)]

The Query and View Designer opens when you open the definition of a view, show the results for a query or view, or create or open a query. It consists of four separate panes:  
  
-   The Diagram pane presents a graphic display of the tables or table-valued objects you have selected from the data connection. It also shows any join relationships among them.  
  
-   The Criteria pane allows you to specify query options - such as which data columns to display, how to order the results, and what rows to select - by entering your choices into a spreadsheet-like grid.  
  
-   You can use the SQL pane to create your own SQL statement, or you can use the Criteria pane and Diagram pane to create the statement, in which case the SQL statements will be created in the SQL pane. As you build your query, the SQL pane automatically updates and reformats to be easily read.  
  
-   The Results pane shows the results of the most recently executed Select query. (The results of other query types are displayed in message boxes.)  
  
-   These panes are useful for working with both queries and views.  
  
-   When you open a view or query some or all of the panes open with it. Which ones open depend on the settings in the **Options** dialog box and what database management system you're connected to. The default is that all four open.  
  
### To open the Query and View Designer for a view  
  
1.  In Object Explorer, right-click the view you want to open and click **Design** or **Open View**.  
  
    If you chose **Design**, the Query and View Designer panes open as dictated by the options selected in the **Options** dialog box. If you chose **Open View**, only the Results pane opens by default.  
  
### To open the Query and View Designer for an existing query  
  
1.  In Solution Explorer, expand the **Queries** folder.  
  
2.  Double-click the query you want to open.  
  
3.  Highlight the query statement(s), right-click the highlighted area and click **Design Query in Editor**.  
  
## See Also  
[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md)  
[Query and View Designer Tools &#40;Visual Database Tools&#41;](query-and-view-designer-tools-visual-database-tools.md)  
  
