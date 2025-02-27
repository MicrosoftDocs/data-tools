---
title: "Connection Pooling in SQL Server Management Studio"
description: Understand how SQL Server Management Studio manages connections.
author: Charles-Gagnon
ms.author: chgagnon
ms.reviewer: randolphwest
ms.date: 03/11/2025
ms.service: sql-server-management-studio
ms.topic: conceptual
helpviewer_keywords:
  - "SQL Server Management Studio [SQL Server], connection pooling"
---

# Connection pooling in SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

Opening connections to a [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] can be an expensive operation, therefore [!INCLUDE [ssManStudioFull](includes/ssmanstudiofull-md.md)] utilizes the Connection Pooling feature of the ADO.NET SqlClient driver. For more information, see [SQL Server connection pooling (ADO.NET)](/sql/connect/ado-net/sql-server-connection-pooling).

This article provides more information on connection pooling in [!INCLUDE [ssManStudioFull](includes/ssmanstudiofull-md.md)], and ways to mitigate the effect it can have on your server.

## Usage and benefits

[!INCLUDE [ssManStudioFull](includes/ssmanstudiofull-md.md)] is a complex application with numerous features, many of which require information from a database or server. Much of this information is loaded on-demand to avoid overhead when making an initial connection, and to avoid unnecessary work if a feature isn't being used.

Connection pooling can help reduce the overhead of retrieving this information. Features in [!INCLUDE [ssManStudioFull](includes/ssmanstudiofull-md.md)] generally use the same base connection entered by the user in the connection dialog, and different features can reuse the same physical connection instead of opening a new one.

## Non-pooled connections

Not all connections in [!INCLUDE [ssManStudioFull](includes/ssmanstudiofull-md.md)] are pooled. Some, such as the connection used for each query editor, are explicitly not pooled. There are several reasons for this, including the need to keep a specific session ID (SPID) associated with the feature, or to ensure that changes made to the connection properties stay consistent across usage.

## Control open connections

While connection pooling improves performance, it also results in connections staying open for longer than might seem necessary. When a connection is returned to the pool, it stays open, but in an idle (or sleeping) state. This state can prevent actions from being taken that require all connections to be closed, such as dropping or altering a database.

There are a few options available to close these idle connections:

1. Wait until ADO.NET closes the connections. This happens for connections which haven't been used for between four and eight minutes.

1. Some operations in [!INCLUDE [ssManStudioFull](includes/ssmanstudiofull-md.md)] (such as `DROP DATABASE`) provide the option to close all existing connections before performing the operation.

1. Use the **Close Idle SQL Connections** command under the **Help** menu. This option immediately closes all idle connections for the current instance of [!INCLUDE [ssManStudioFull](includes/ssmanstudiofull-md.md)]. Active connections aren't affected except for immediately being closed when they're done being used instead of being returned to the pool.

   > [!NOTE]  
   > Closing idle connections can result in decreased performance the next time a new connection to the server is needed, because the connection needs to be reestablished.

1. Close [!INCLUDE [ssManStudioFull](includes/ssmanstudiofull-md.md)]. Closing [!INCLUDE [ssManStudioFull](includes/ssmanstudiofull-md.md)] immediately closes all open connections associated with that database or instance.

1. Run the [KILL](/sql/t-sql/language-elements/kill-transact-sql) statement to close any sessions that are blocking your operation.

## Related content

- [SQL Server connection pooling (ADO.NET)](/sql/connect/ado-net/sql-server-connection-pooling)
