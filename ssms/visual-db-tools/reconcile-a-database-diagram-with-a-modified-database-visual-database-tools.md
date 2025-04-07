---
title: Reconcile a Database Diagram with a Modified Database
description: "Reconcile a Database Diagram with a Modified Database (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: conceptual
ms.collection:
  - data-tools
helpviewer_keywords:
  - "updating diagram to match database"
  - "reconciling database diagrams"
  - "diagrams [SQL Server], reconciling changes"
  - "updating database to match diagram"
  - "database diagrams [SQL Server], reconciling changes"
---
# Reconcile a Database Diagram with a Modified Database (Visual Database Tools)

[!INCLUDE[SQL Server Azure SQL Database PDW](../includes/applies-to-version/sql-asdb-asdbmi-pdw.md)]

You save your database diagram when you are ready to update the database to match your diagram. However, if other users have updated the database since you opened your diagram, their changes might affect your diagram and vice versa.  
  
Saving your diagram will reconcile the database with your diagram by overwriting other users' changes so that the database will match your diagram.  
  
### To update a database to match your diagram  
  
1.  Save your database diagram.  
  
    If you have not previously saved your diagram, type a name for the diagram in the **Save New Database Diagram** dialog box and choose **OK**.  
  
2.  The **Save** dialog box lists the tables that will be affected when you save your diagram. Choose **Yes** to continue.  
  
3.  The **Database Changes Detected** dialog box lists the objects that were modified and will be changed to match your diagram. Choose **Yes** to save the diagram and accept the list of changes.  
  
    > [!NOTE]  
    > If your diagram contains tables and columns that were deleted in the database, only their definitions are recreated in the database when you save your diagram. This process does not restore any data that existed in these objects before their deletion.  
  
### To update your diagram to match a modified database  
  
1.  Close your diagram without saving changes.  
  
2.  Right-click the diagram in Object Explorer.  
  
3.  From the shortcut menu click **Refresh**.  
  
4.  Reopen the diagram.  
  
## See Also  
[Work with Database Diagrams &#40;Visual Database Tools&#41;](work-with-database-diagrams-visual-database-tools.md)  
  
