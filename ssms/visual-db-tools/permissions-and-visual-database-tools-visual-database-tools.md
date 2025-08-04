---
title: Permissions and Visual Database Tools
description: "Permissions and Visual Database Tools (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "multiuser environments [Visual Database Tools]"
---
# Permissions and Visual Database Tools (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

Permissions, which allow users access to data source objects, are granted in the data source, not in Visual Database Tools. The access permissions granted on data source objects is controlled by your installation's security policy. If you don't have permission to access certain database objects, you should contact your database administrator.

If the database permissions let you view but not modify the database structure, you can use change scripts to design your modifications without transmitting them to the database.

## Related content

- [Multiuser Environments (Visual Database Tools)](multiuser-environments-visual-database-tools.md)
