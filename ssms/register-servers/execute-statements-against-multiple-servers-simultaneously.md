---
title: Execute Statements Against Multiple Servers Simultaneously
description: Overview of how to execute statements against multiple servers at the same time in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.date: 07/08/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "multiserver queries"
  - "executing queries against multiple servers"
  - "queries [SQL Server], multiserver"
---
# Execute statements against multiple servers simultaneously in SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This article describes how to query multiple servers at the same time in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)], by creating a local server group, or a Central Management Server (CMS) and one or more server groups. There must be one or more registered servers within the groups, and queries can be executed against a single group, or multiple groups.

The results returned by the query can be combined into a single results pane, or they can be returned in separate results panes. The result set can include extra columns that provide the name of the server that produced each row, and the login that was used to connect to the server that provided each row.

## Permissions

Because the connections to the servers maintained by a CMS are made in the context of the user, the effective permissions on the registered servers might vary. For example, the user might be a member of the **sysadmin** fixed server role on the instance of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] A, but have limited permissions on the instance of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] B.

When queries are executed in a Query Editor, they execute against all servers in the group, using the connection information provided by the user. Servers registered with [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Authentication that don't have a saved password fail to connect.

## Execute statements against multiple configuration targets simultaneously

If the Registered Servers tool window isn't visible in SQL Server Management Studio, select **View** > **Registered Servers**, or type **Ctrl** + **Alt** + **G**.

1. Expand **Database Engine**, then **Central Management Servers** and find the server group that contains the servers you want to query.

1. Right-click on the server group and select **New Query**.

1. In the Query Editor, the number of connected servers displays in the bottom left of the status bar as `Connected. (4/4)`.

   - The first number is the active connections. The second number is the number of registered servers in the group.
   - If the connection to a server fails, no error message is displayed.

1. In the Query Editor, enter and then execute a [!INCLUDE [tsql](../includes/tsql-md.md)] statement, such as the following example:

   ```sql
   SELECT
       @@VERSION AS [ProductVersion],
       SERVERPROPERTY('Edition') AS [Edition];
   GO
   ```

1. By default, the results pane combines the query results from all the servers in the server group into a single results grid.

### Change the multiserver results options

1. Within SQL Server Management Studio, select **Tools** > **Options** > **Query Results** > **SQL Server** > **Multiserver Results**.

1. Edit the option based on your preferences.

   | Option | Default value | Definition |
   | --- | --- |
   | **Add login name to the results** | False | Adds a column in the query results that displays the name of the login connected to the server. |
   | **Add server name to the results** | True | Adds a column in the query results that displays the name of the server that produces the row. |
   | **Merge results** | True | Displays the results from all servers in the same results grid. |

1. Select **OK** to save your changes.

## Related content

- [Administer multiple servers using Central Management Servers](/sql/relational-databases/administer-multiple-servers-using-central-management-servers)
