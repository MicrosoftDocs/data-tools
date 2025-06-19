---
title: Development, Test, and Production Databases
description: "Development, Test, and Production Databases (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "production databases [SQL Server]"
  - "testing databases"
  - "database testing [SQL Server]"
---
# Development, Test, and Production Databases (Visual Database Tools)
[!INCLUDE[SQL Server](../includes/applies-to-version/sqlserver.md)]
If you have two databases with identical structure, you can make changes in one database and propagate those changes to the other. For example, if you have a personal development database and a group-wide test database, you can modify the development database, then propagate those changes to the test database.  
  
To accomplish this, perform all the modifications in a single session with the development database, create a Change Script of your session and later run the script on the test database.  
  
## See Also  
[Multiuser Environments &#40;Visual Database Tools&#41;](multiuser-environments-visual-database-tools.md)  
  
