---
title: Server Properties (Processors Page)
titleSuffix: SQL Server Management Studio
description: View and modify processor and I/O affinity settings and maximum worker threads by using the Processors page of the Server Properties window.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mbarickman
ms.date: 09/03/2026
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.serverproperties.processor.f1"
ai-usage: ai-assisted
---
# Server Properties (Processors page)

[!INCLUDE [sql-asdbmi](../includes/applies-to-version/sql-asdbmi.md)]

Use this page to view or modify processor options. Processor affinity settings are only enabled when more than one processor is installed.

## Enable processors

The grid has the following columns:

| Column | Description |
| --- | --- |
| **Processor** | Lists the processors on the server. |
| **Processor Affinity** | Assigns processors to specific threads to eliminate processor reloads and reduce thread migration across processors. For more information, see [Server configuration: affinity mask](/sql/database-engine/configure-windows/affinity-mask-server-configuration-option). |
| **I/O Affinity** | Binds the [!INCLUDE [ssdenoversion-md](../includes/ssdenoversion-md.md)] disk I/O to a specified subset of CPUs. For more information, see [Server configuration: affinity I/O mask](/sql/database-engine/configure-windows/affinity-input-output-mask-server-configuration-option). |

### Automatically set processor affinity mask for all processors

Allows the [!INCLUDE [ssde-md](../includes/ssde-md.md)] to set the processor affinity.

### Automatically set I/O affinity mask for all processors

Allows the [!INCLUDE [ssde-md](../includes/ssde-md.md)] to set the I/O affinity.

## Threads

### Maximum worker threads

A value of `0` allows the [!INCLUDE [ssde-md](../includes/ssde-md.md)] to dynamically set the number of worker threads. This setting is best for most systems. However, depending on your system configuration, setting this option to a specific value sometimes improves performance. For more information, see [Server configuration: max worker threads](/sql/database-engine/configure-windows/configure-the-max-worker-threads-server-configuration-option).

## Related content

- [Server Properties window in SQL Server Management Studio](server-properties-window.md)
- [Server configuration options](/sql/database-engine/configure-windows/server-configuration-options-sql-server)
