---
title: Multiuser Environments
description: "Multiuser Environments (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "users [SQL Server], multiuser environments"
  - "conflict resolution [Visual Database Tools]"
  - "multiple users making database changes"
  - "multiuser environments [Visual Database Tools]"
  - "database modifications [SQL Server]"
  - "version control [Visual Database Tools]"
  - "Visual Database Tools [SQL Server], multiuser environments"
---
# Multiuser Environments (Visual Database Tools)
[!INCLUDE[SQL Server](../includes/applies-to-version/sqlserver.md)]
A multiuser environment is one in which other users can connect and make changes to the same database that you are working with. As a result, several users might be working with the same database objects at the same time. Thus, a multiuser environment introduces the possibility of the database being affected by changes made by other users while you are making changes, and vice versa.  
  
A key issue when working with databases in a multiuser environment is access permissions. The permissions you have for the database determine the extent of the work you can do with the database. For example, to make changes to objects in a database, you must have the appropriate write permissions for the database. For more information about permissions in your database, see your database documentation. For more information see [Permissions and Visual Database Tools (Visual Database Tools)](permissions-and-visual-database-tools-visual-database-tools.md).  
  
When you save changes made to tables, Table Designer verifies that the database has not been modified since you last saved changes. If another user has made changes, you will be notified that the database has been modified. You may need to reconcile these changes. For more information, see [Reconcile Changes Made by Multiple Users (Visual Database Tools)](reconcile-changes-made-by-multiple-users-visual-database-tools.md).  
  
In a multiuser environment there are special considerations to keep in mind to avoid conflicting changes. For more information, see [Visual Database Tools](visual-database-tools.md).  
  
One way to avoid problems is to work in a copy of the database, such as a test database, when you make changes, then you can create a change script that you can run to make those changes on the original database after resolving conflicts offline. For more information see [Visual Database Tools](visual-database-tools.md).  
  
