---
title: Server Properties (General Page)
titleSuffix: SQL Server Management Studio
description: View read-only properties for a SQL Server instance, including server name, operating system, collation, and version.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mbarickman
ms.date: 09/03/2026
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.serverproperties.setsapassword.f1"
  - "sql13.swb.serverproperties.activedirectory.f1"
  - "sql13.swb.serverproperties.prodinfo.f1"
ai-usage: ai-assisted
---
# Server Properties (General page)

[!INCLUDE [sql-asdbmi](../includes/applies-to-version/sql-asdbmi.md)]

Use this page to view read-only information about the [!INCLUDE [ssdenoversion-md](../includes/ssdenoversion-md.md)] instance in [SQL Server Management Studio](../sql-server-management-studio-ssms.md). Depending on the environment, platform, or host, some properties might not be available.

## Property grid

| Property | Description | More information |
| --- | --- | --- |
| **Name** | The name of the [!INCLUDE [ssde-md](../includes/ssde-md.md)] server and instance. | [Database Engine instances (SQL Server)](/sql/database-engine/configure-windows/database-engine-instances-sql-server) |
| **Product** | The edition of the [!INCLUDE [ssde-md](../includes/ssde-md.md)] currently running. | [Editions and supported features of SQL Server 2025](/sql/sql-server/editions-and-components-of-sql-server-2025) |
| **Operating System** <sup>1</sup> | The operating system of the host, virtual machine, or container where the [!INCLUDE [ssde-md](../includes/ssde-md.md)] is installed. | [Software requirements](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server-2025#software-requirements) |
| **Platform** <sup>1</sup> | The operating system and processor running the [!INCLUDE [ssde-md](../includes/ssde-md.md)]. | [Hardware requirements](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server-2025#hardware-requirements) |
| **Version** | The build number of the [!INCLUDE [ssde-md](../includes/ssde-md.md)] edition currently running. | [Latest updates and version history for SQL Server](/troubleshoot/sql/releases/download-and-install-latest-updates) |
| **Language** | The language supported by the running instance of the [!INCLUDE [ssde-md](../includes/ssde-md.md)]. | [Local language versions in SQL Server](/sql/sql-server/install/local-language-versions-in-sql-server) |
| **Memory** | The amount of RAM installed on the server. This memory might not all be available to the [!INCLUDE [ssde-md](../includes/ssde-md.md)]. | [Hardware requirements](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server-2025#hardware-requirements) |
| **Processors** | The number of logical CPU cores installed. These cores might not all be available to the [!INCLUDE [ssde-md](../includes/ssde-md.md)]. | [Compute capacity limits by edition of SQL Server](/sql/sql-server/compute-capacity-limits-by-edition-of-sql-server) |
| **Root Directory** | The path to the [!INCLUDE [ssde-md](../includes/ssde-md.md)] instance. On Windows, this path is typically `C:\Program Files\Microsoft SQL Server\`. | [File locations for default and named instances of SQL Server](/sql/sql-server/install/file-locations-for-default-and-named-instances-of-sql-server) |
| **Server Collation** | The collation supported by the server. A collation specifies the code page and sort order for Unicode and non-Unicode data. | [Set or change the server collation](/sql/relational-databases/collations/set-or-change-the-server-collation) |
| **Is HADR Enabled** | **True** if Always On availability groups is enabled, or **False** otherwise. | [Enable or disable the Always On availability group feature](/sql/database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server) |
| **Is XTP Supported** | **True** if this instance supports In-Memory OLTP (extreme transaction processing). **False** if In-Memory OLTP support is disabled. | [Requirements for using memory-optimized tables](/sql/relational-databases/in-memory-oltp/requirements-for-using-memory-optimized-tables) |
| **Is PolyBase Installed** | **True** if PolyBase is installed on this instance, or **False** otherwise. | [Install PolyBase on Windows](/sql/relational-databases/polybase/polybase-installation) |
| **Is Clustered** | **True** if the server instance is configured in a failover cluster, or **False** otherwise. | [Windows Server Failover Clustering with SQL Server](/sql/sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server) |

<sup>1</sup> For more information about the operating system version, see [@@VERSION](/sql/t-sql/functions/version-transact-sql-metadata-functions#general-remarks).

## Related content

- [Server Properties window in SQL Server Management Studio](server-properties-window.md)
- [Server configuration options](/sql/database-engine/configure-windows/server-configuration-options-sql-server)
