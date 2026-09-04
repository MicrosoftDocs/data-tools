---
title: Server Properties (Connections Page)
titleSuffix: SQL Server Management Studio
description: View and modify connection options, default connection settings, and remote server connections by using the Connections page of the Server Properties window.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mbarickman
ms.date: 09/03/2026
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.serverproperties.connections.f1"
ai-usage: ai-assisted
---
# Server Properties (Connections page)

[!INCLUDE [sql-asdbmi](../includes/applies-to-version/sql-asdbmi.md)]

Use this page to view or modify connection options.

## Connections

### Maximum number of concurrent connections (0 = unlimited)

If you set this value to something other than zero, it limits the number of connections that the [!INCLUDE [ssdenoversion-md](../includes/ssdenoversion-md.md)] supports.

> [!CAUTION]  
> Setting this value to a small number, such as `1` or `2`, can prevent administrators from connecting to administer the server. However, the Dedicated Admin Connection can always connect.

### Use query governor to prevent long-running queries

Specifies an upper limit on the estimated cost allowed for a given query to run. Query cost is an abstract figure based on estimated execution requirements (CPU time, memory, and disk I/O), not a measure of time. By default, this option allows all queries to run without any limitation. If you specify a nonzero positive integer, the query governor prevents any query with an estimated cost that exceeds that value from running. For more information, see [Server configuration: query governor cost limit](/sql/database-engine/configure-windows/configure-the-query-governor-cost-limit-server-configuration-option).

## Default connection options

| Setting | Description |
| --- | --- |
| `implicit transactions` | Controls whether a transaction starts implicitly when a statement runs. |
| `cursor close on commit` | Controls the behavior of cursors after a commit operation. |
| `ansi warnings` | Controls truncation and `NULL` in aggregate warnings. |
| `ansi padding` | Controls padding of fixed-length variables. |
| `ansi nulls` | Controls `NULL` handling when using equality operators. |
| `arithmetic abort` | Terminates a query when an overflow or divide-by-zero error occurs during query execution. |
| `arithmetic ignore` | Returns `NULL` when an overflow or divide-by-zero error occurs during a query. |
| `quoted identifier` | Differentiates between single and double quotation marks when evaluating an expression. |
| `no count` | Turns off the message returned at the end of each statement that states how many rows were affected. |
| `ansi null default on` | Alters the session's behavior to use ANSI compatibility for nullability. New columns defined without explicit nullability allow nulls. |
| `ansi null default off` | Alters the session's behavior not to use ANSI compatibility for nullability. New columns defined without explicit nullability don't allow nulls. |
| `concat null yields null` | Returns `NULL` when concatenating a `NULL` value with a string. |
| `numeric round abort` | Generates an error when a loss of precision occurs in an expression. |
| `xact abort` | Rolls back a transaction if a Transact-SQL (T-SQL) statement raises a run-time error. |

## Remote server connections

### Allow remote connections to this server

Controls whether remote instances of the [!INCLUDE [ssde-md](../includes/ssde-md.md)] can run stored procedures on this server. Selecting this checkbox has the same effect as setting the [remote access](/sql/database-engine/configure-windows/configure-the-remote-access-server-configuration-option) server configuration option to `1`. Clearing it prevents remote instances from running stored procedures on this server.

### Remote query timeout (in seconds, 0 = no timeout)

Specifies how long (in seconds) a remote operation can take before the [!INCLUDE [ssde-md](../includes/ssde-md.md)] times out. The default is `600` (600 seconds, or 10 minutes).

### Require distributed transactions for server-to-server communication

This setting protects the actions of a server-to-server procedure through a Microsoft Distributed Transaction Coordinator (MS DTC) transaction. For more information, see [Server configuration: remote proc trans](/sql/database-engine/configure-windows/configure-the-remote-proc-trans-server-configuration-option).

## Related content

- [Server Properties window in SQL Server Management Studio](server-properties-window.md)
- [Server configuration options](/sql/database-engine/configure-windows/server-configuration-options-sql-server)
