---
title: "Hide System Objects in Object Explorer"
description: Learn how to hide system objects in Object Explorer in SQL Server.
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/07/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "hiding system objects"
  - "system objects [SQL Server]"
  - "objects [SQL Server], hiding"
  - "Object Explorer, hiding objects"
---
# Hide system objects in Object Explorer

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This article describes how to hide system objects in Object Explorer in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] by using [!INCLUDE [ssManStudioFull](../includes/ssmanstudiofull-md.md)]. The **Databases** node of Object Explorer contains system objects such as the system databases. Use the **Tools**/**Options** pages to hide the system objects. Some system objects, such as system functions and system data types, aren't affected by this setting.

<a id="SSMSProcedure"></a>

## Use SQL Server Management Studio

1. On the **Tools** menu, select **Options**.

1. On the **Environment/Startup** page, select **Hide system objects in Object Explorer**, and then select **OK**.

1. In the **SQL Server Management Studio** dialog box, select **OK** to acknowledge that SQL Server Management Studio must be restarted for this change to take effect.

1. Close and reopen SQL Server Management Studio.
