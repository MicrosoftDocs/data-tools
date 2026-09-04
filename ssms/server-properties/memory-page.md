---
title: Server Properties (Memory Page)
titleSuffix: SQL Server Management Studio
description: View and modify server memory options, including minimum and maximum server memory, index creation memory, and minimum memory per query.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mbarickman
ms.date: 09/03/2026
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.serverproperties.memory.f1"
ai-usage: ai-assisted
---
# Server Properties (Memory page)

[!INCLUDE [sql-asdbmi](../includes/applies-to-version/sql-asdbmi.md)]

Use this page to view or modify server memory options. When you set **Minimum server memory (in MB)** to `0` and **Maximum server memory (in MB)** to `2147483647` (2,147,483,647 MB), the [!INCLUDE [ssdenoversion-md](../includes/ssdenoversion-md.md)] takes advantage of the optimum amount of memory at any given time, depending on how much memory the operating system and other applications currently use.

> [!NOTE]  
> You should set an upper limit for [!INCLUDE [ssde-md](../includes/ssde-md.md)] memory use. For more information, see [Server memory configuration options](/sql/database-engine/configure-windows/server-memory-server-configuration-options).

Use the following options to set the minimum and maximum memory that the [!INCLUDE [ssde-md](../includes/ssde-md.md)] allocates to the buffer pool.

## Server memory options

### Minimum server memory (in MB)

Specifies that the [!INCLUDE [ssde-md](../includes/ssde-md.md)] starts with at least the minimum amount of allocated memory and doesn't release memory below this value. Set this value based on the size and activity of your instance of the [!INCLUDE [ssde-md](../includes/ssde-md.md)].

Always set the option to a reasonable value to ensure that the operating system doesn't request too much memory from the [!INCLUDE [ssde-md](../includes/ssde-md.md)] and inhibit operating system performance.

### Maximum server memory (in MB)

Specifies the upper limit of memory the [!INCLUDE [ssde-md](../includes/ssde-md.md)] can allocate during its operation. Always set this configuration option to a specific value to ensure that the operating system and other applications have enough memory to run.

If these other applications, such as web or email servers, request memory only as needed, don't set the option. The [!INCLUDE [ssde-md](../includes/ssde-md.md)] releases memory to them as needed. However, applications often use whatever memory is available when they start and don't request more if needed.

If an application that behaves in this manner runs on the same computer at the same time as the [!INCLUDE [ssde-md](../includes/ssde-md.md)], set the option to a value that guarantees that the memory required by the application isn't allocated by the [!INCLUDE [ssde-md](../includes/ssde-md.md)].

The minimum amount of memory you can specify for `max server memory (MB)` is 128 MB.

## Other memory options

### Index creation memory (in KB, 0 = dynamic memory)

Specifies the amount of memory in kilobytes to use during index creation sorts. The default value of zero enables dynamic allocation and should work in most cases without extra adjustment. However, you can enter a different value from `704` to `2147483647` (2,147,483,647).

> [!NOTE]  
> Values from `1` to `703` aren't allowed. If you enter a value in this range, the field overrides the entered value with `704`.

### Minimum memory per query (in KB)

Specifies the amount of memory in kilobytes to allocate to run a query. Valid values range from `512` through `2147483647` (2,147,483,647 KB). The default value is `1024` (1,024 KB).

## Related content

- [Server Properties window in SQL Server Management Studio](server-properties-window.md)
- [Server memory configuration options](/sql/database-engine/configure-windows/server-memory-server-configuration-options)
