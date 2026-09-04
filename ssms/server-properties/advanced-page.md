---
title: Server Properties (Advanced Page)
titleSuffix: SQL Server Management Studio
description: View and modify advanced server settings including FILESTREAM, containment, network, and parallelism options by using the Advanced page of the Server Properties window.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mbarickman
ms.date: 09/03/2026
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.serverproperties.advanced.f1"
  - "sql13.swb.serverproperties.filestream.f1"
  - "sql13.swb.serverproperties.miscserversettings.f1"
ai-usage: ai-assisted
---
# Server Properties (Advanced page)

[!INCLUDE [sql-asdbmi](../includes/applies-to-version/sql-asdbmi.md)]

Use this page to view or modify advanced server settings.

## Containment

### Enable Contained Databases

Indicates if this instance of the [!INCLUDE [ssdenoversion-md](../includes/ssdenoversion-md.md)] permits contained databases. When **True**, you can create, restore, or attach a contained database. When **False**, you can't create, restore, or attach a contained database to this instance. Changing the containment property can affect the security of the database. Enabling contained databases lets database owners grant access to this [!INCLUDE [ssde-md](../includes/ssde-md.md)] instance. Disabling contained databases can prevent users from connecting.

For more information, see [Contained Databases](/sql/relational-databases/databases/contained-databases) and [Security Best Practices with Contained Databases](/sql/relational-databases/databases/security-best-practices-with-contained-databases).

## FILESTREAM

### FILESTREAM Access Level

Shows the current level of FILESTREAM support on the [!INCLUDE [ssde-md](../includes/ssde-md.md)] instance. To change the access level, select one of the following values:

| Value | Description |
| --- | --- |
| **Disabled** (default) | Binary large object (BLOB) data can't be stored on the file system. |
| **Transact-SQL access enabled** | FILESTREAM data is accessible by using T-SQL, but not through the file system. |
| **Full access enabled** | FILESTREAM data is accessible by using T-SQL and through the file system. |

When you enable FILESTREAM for the first time, you might have to restart the computer to configure drivers.

### FILESTREAM Share Name

Displays the read-only name of the FILESTREAM share that you selected during setup.

For more information, see [FILESTREAM (SQL Server)](/sql/relational-databases/blob/filestream-sql-server).

## Miscellaneous

### Allow Triggers to Fire Others

When you enable this option, triggers can fire other triggers. You can nest triggers up to 32 levels.

For more information, see the "Nested Triggers" section in [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql).

### Blocked Process Threshold

Specifies the threshold, in seconds, at which the system generates blocked process reports. You can set the threshold from `0` to `86400` (86,400 seconds, or 24 hours). By default, the system doesn't produce any blocked process reports.

For more information, see [Server configuration: blocked process threshold](/sql/database-engine/configure-windows/blocked-process-threshold-server-configuration-option).

### Boost SQL Server Priority

Specifies whether the [!INCLUDE [ssde-md](../includes/ssde-md.md)] runs at a higher Windows scheduling priority than other processes on the same computer. For more information, see [Server configuration: priority boost](/sql/database-engine/configure-windows/configure-the-priority-boost-server-configuration-option).

### Cursor Threshold

Specifies the number of rows in the cursor set at which cursor keysets are generated asynchronously. When cursors generate a keyset for a result set, the query optimizer estimates the number of rows that are returned for that result set. If the query optimizer estimates that the number of returned rows is greater than this threshold, the cursor is generated asynchronously, which means you can fetch rows from the cursor while the cursor continues to be populated. Otherwise, the cursor is generated synchronously, and the query waits until all rows are returned.

If you set this value to `-1`, all keysets are generated synchronously, which benefits small cursor sets. If you set it to `0`, all cursor keysets are generated asynchronously. For other values, the query optimizer compares the number of expected rows in the cursor set and builds the keyset asynchronously if it exceeds the number set.

For more information, see [Server configuration: cursor threshold](/sql/database-engine/configure-windows/configure-the-cursor-threshold-server-configuration-option).

### Default Full-Text Language

Specifies a default language for full-text indexed columns. Linguistic analysis of full-text indexed data depends on the language of the data. The default value of this option is the language of the server.

For the language that corresponds to the displayed setting, see [sys.fulltext_languages](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql).

### Default Language

The default language for all new logins, unless you specify otherwise.

### Full-Text Upgrade Option

Controls how the [!INCLUDE [ssde-md](../includes/ssde-md.md)] handles full-text indexes when you attach a database, restore a database backup, restore a file backup, or copy a database by using the Copy Database Wizard.

| Property | Description |
| --- | --- |
| **Import** | Full-text catalogs are imported. This operation is significantly faster than **Rebuild**. However, an imported full-text catalog doesn't use the enhanced word breakers introduced in later versions. Therefore, you might want to rebuild your full-text catalogs eventually. If a full-text catalog isn't available, the associated full-text indexes are rebuilt. |
| **Rebuild** | Full-text catalogs are rebuilt using the enhanced word breakers. Rebuilding indexes can take some time, and a significant amount of CPU and memory might be required after the upgrade. Rebuilding can take up to 10 times longer than importing. |
| **Reset** | Full-text catalogs are reset. Full-text catalog files are removed, but the metadata for full-text catalogs and full-text indexes is retained. After being upgraded, all full-text indexes are disabled for change tracking and crawls aren't started automatically. The catalog remains empty until you manually issue a full population, after the upgrade completes. |

> [!NOTE]  
> You can set the full-text upgrade option using the [sys.sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql) `upgrade_option` action.

For more information, see [Upgrade Full-Text Search (SQL Server Search)](/sql/relational-databases/search/upgrade-full-text-search).

### Max Text Replication Size

Specifies the maximum size (in bytes) of **text**, **ntext**, **varchar(max)**, **nvarchar(max)**, **xml**, and **image** data that you can add to a replicated column or captured column in a single `INSERT`, `UPDATE`, `WRITETEXT`, or `UPDATETEXT` statement. Changing the setting takes effect immediately.

For more information, see [Server configuration: max text repl size](/sql/database-engine/configure-windows/configure-the-max-text-repl-size-server-configuration-option).

### Optimize for Ad hoc Workloads

Specifies whether the [!INCLUDE [ssde-md](../includes/ssde-md.md)] stores a small compiled plan stub in the plan cache the first time a batch is compiled, instead of the full compiled plan. This setting reduces the memory that single-use plans consume. For more information, see [Server configuration: optimize for ad hoc workloads](/sql/database-engine/configure-windows/optimize-for-ad-hoc-workloads-server-configuration-option).

### Scan for Startup Procs

Specifies that the [!INCLUDE [ssde-md](../includes/ssde-md.md)] scans for stored procedures to run automatically at startup. If set to **True**, the [!INCLUDE [ssde-md](../includes/ssde-md.md)] scans for and runs all automatically run stored procedures defined on the server. If set to **False** (the default), no scan is performed.

For more information, see [Server configuration: scan for startup procs](/sql/database-engine/configure-windows/configure-the-scan-for-startup-procs-server-configuration-option).

### Two Digit Year Cutoff

Indicates the highest year number that you can enter as a two-digit year. The year listed and the previous 99 years can be entered as a two-digit year. All other years must be entered as a four-digit year.

For example, the default setting of `2049` indicates that a date entered as `3/14/49` is interpreted as March 14, 2049, and a date entered as `3/14/50` is interpreted as March 14, 1950.

For more information, see [Server configuration: two digit year cutoff](/sql/database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option).

### Use Windows fibers (lightweight pooling)

Specifies whether the [!INCLUDE [ssde-md](../includes/ssde-md.md)] service uses Windows fibers instead of threads. For more information, see [Server configuration: lightweight pooling](/sql/database-engine/configure-windows/lightweight-pooling-server-configuration-option).

## Network

### Network Packet Size

Sets the packet size in bytes for the whole network. The default packet size is `4096` (4,096 bytes). If an application performs bulk copy operations or sends or receives large amounts of **text** or **image** data, a packet size larger than the default might improve efficiency because it results in fewer network reads and writes. If an application sends and receives small amounts of information, set the packet size to 512 bytes, which is sufficient for most data transfers.

For more information, see [Server configuration: network packet size](/sql/database-engine/configure-windows/configure-the-network-packet-size-server-configuration-option).

> [!NOTE]  
> Don't change the packet size unless you're certain that it improves performance. For most applications, the default packet size is best.

### Remote Login Timeout

Specifies the number of seconds that the [!INCLUDE [ssde-md](../includes/ssde-md.md)] waits before returning from a failed remote login attempt. This setting affects connections to OLE DB providers made for heterogeneous queries. The default value is 20 seconds. A value of `0` allows for an infinite wait.

For more information, see [Server configuration: remote login timeout](/sql/database-engine/configure-windows/configure-the-remote-login-timeout-server-configuration-option).

Changing the setting takes effect immediately.

## Parallelism

### Cost Threshold for Parallelism

Specifies the threshold above which the [!INCLUDE [ssde-md](../includes/ssde-md.md)] creates and runs parallel plans for queries. The cost refers to an estimated elapsed time in seconds required to run the serial plan on a specific hardware configuration. Set this option only on computers with more than one [logical processor](/sql/sql-server/compute-capacity-limits-by-edition-of-sql-server#remarks).

For more information, see [Server configuration: cost threshold for parallelism](/sql/database-engine/configure-windows/configure-the-cost-threshold-for-parallelism-server-configuration-option).

### Locks

Sets the maximum number of available locks, which limits the amount of memory that the [!INCLUDE [ssde-md](../includes/ssde-md.md)] uses for them. The default setting is `0`, which allows the [!INCLUDE [ssde-md](../includes/ssde-md.md)] to allocate and deallocate locks dynamically based on changing system requirements.

Allowing the [!INCLUDE [ssde-md](../includes/ssde-md.md)] to use locks dynamically is the recommended configuration.

For more information, see [Server configuration: locks](/sql/database-engine/configure-windows/configure-the-locks-server-configuration-option).

### Max Degree of Parallelism

Limits the number of processors (up to a maximum of `64`) to use in parallel plan execution. The default value of `0` uses all available processors. A value of `1` suppresses parallel plan generation. A number greater than `1` restricts the maximum number of processors used by a single query execution. If a value greater than the number of available processors is specified, the actual number of available processors is used.

For more information, see [Server configuration: max degree of parallelism](/sql/database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option).

### Query Wait

Specifies the time in seconds, from `0` through `2147483647` (2,147,483,647) that a query waits for resources before timing out. If you use the default value of `-1`, the timeout is calculated as 25 times the estimated query cost.

For more information, see [Server configuration: query wait](/sql/database-engine/configure-windows/configure-the-query-wait-server-configuration-option).

## Related content

- [Server Properties window in SQL Server Management Studio](server-properties-window.md)
- [Server configuration options](/sql/database-engine/configure-windows/server-configuration-options-sql-server)
