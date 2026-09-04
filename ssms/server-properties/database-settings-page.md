---
title: Server Properties (Database Settings Page)
titleSuffix: SQL Server Management Studio
description: View and modify database settings including index fill factor, backup options, recovery interval, and default file locations by using the Database Settings page of the Server Properties window.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mbarickman
ms.date: 09/03/2026
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.serverproperties.databasesettings.f1"
ai-usage: ai-assisted
---
# Server Properties (Database Settings page)

[!INCLUDE [sql-asdbmi](../includes/applies-to-version/sql-asdbmi.md)]

Use this page to view or modify database settings.

## Default index fill factor

Specifies how full the [!INCLUDE [ssdenoversion-md](../includes/ssdenoversion-md.md)] should make each page when it creates a new index using existing data. The fill factor affects performance because the [!INCLUDE [ssde-md](../includes/ssde-md.md)] must take time to split pages when they fill up.

The default value is `0`. Valid values range from `0` through `100`. A fill factor of `0` or `100` creates clustered indexes with full data pages and nonclustered indexes with full leaf pages, but it leaves some space within the upper level of the index tree. Fill factor values `0` and `100` are identical in all respects.

Small fill factor values cause the [!INCLUDE [ssde-md](../includes/ssde-md.md)] to create indexes with pages that aren't full. Each index takes more storage space, but there's more room for subsequent insertions without requiring page splits.

## Backup and restore

The following options set how long the [!INCLUDE [ssde-md](../includes/ssde-md.md)] waits for a new backup tape. They're unavailable when the server has no tape device.

| Option | Description |
| --- | --- |
| **Wait indefinitely** | Specifies that the [!INCLUDE [ssde-md](../includes/ssde-md.md)] never times out while waiting for a new backup tape. |
| **Try once** | Specifies that the [!INCLUDE [ssde-md](../includes/ssde-md.md)] times out if a backup tape isn't available when needed. |
| **Try for minute(s)** | Specifies that the [!INCLUDE [ssde-md](../includes/ssde-md.md)] times out if a backup tape isn't available within the period specified. |

### Default backup media retention (in days)

Specifies the system-wide default for how long to keep each backup medium after it's been used for a database or transaction log backup. This option helps protect backups from being overwritten until the specified number of days passes.

### Compress backup

Specifies the server-level default for compressing backups:

- If the **Compress backup** box is empty, new backups are uncompressed by default.
- If the **Compress backup** box is checked, new backups are compressed by default.

> [!IMPORTANT]  
> Compression increases CPU usage, which might affect concurrent operations. You can create low-priority compressed backups in a session whose CPU usage is limited by [Resource governor](/sql/relational-databases/resource-governor/resource-governor). For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression](/sql/relational-databases/backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql).

For more information, see [Server configuration: backup compression default](/sql/database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option) and [Backup compression (SQL Server)](/sql/relational-databases/backup-restore/backup-compression-sql-server).

### Backup checksum

Toggles the [backup checksum default](/sql/database-engine/configure-windows/backup-checksum-default) server configuration option.

## Recovery

### Recovery interval (minutes)

Sets the maximum number of minutes per database to recover databases. The default is `0`, which means the [!INCLUDE [ssde-md](../includes/ssde-md.md)] automatically configures it. In practice, this option means a recovery time of less than one minute and a checkpoint occurs approximately every one minute for active databases. For more information, see [Server configuration: recovery interval (min)](/sql/database-engine/configure-windows/configure-the-recovery-interval-server-configuration-option).

## Database default locations

To change a default location, select the browse button for that option. A new location takes effect when the [!INCLUDE [ssde-md](../includes/ssde-md.md)] restarts.

| Option | Description |
| --- | --- |
| **Data** | Specifies the default location for data files. |
| **Log** | Specifies the default location for log files. |
| **Backup** | Specifies the default location for backup files. |

## Related content

- [Server Properties window in SQL Server Management Studio](server-properties-window.md)
- [Server configuration options](/sql/database-engine/configure-windows/server-configuration-options-sql-server)
- [Specify fill factor for an index](/sql/relational-databases/indexes/specify-fill-factor-for-an-index)
