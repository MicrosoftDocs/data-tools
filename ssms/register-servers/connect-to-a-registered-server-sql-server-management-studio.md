---
title: Connect to a Registered Server
description: Overview of connecting to a registered server in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.date: 07/08/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "Registered Servers [SQL Server], connections"
  - "connections [SQL Server], registered servers"
---

# Connect to a registered server in SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This article describes how to connect to a registered server using SQL Server Management Studio (SSMS). If the server isn't running or can't be found on the network, the Registered Servers feature displays an error.

If the Registered Servers tool window isn't visible in SSMS, select **View** > **Registered Servers**, or type **Ctrl** + **Alt** + **G**.

## Open Object Explorer for a registered server

1. Within the Local Server Groups or Central Management Servers, find the registered server you want to view in Object Explorer.
1. Right-click on the registered server and select **Object Explorer**.
1. The tree structure for the server displays in the Object Explorer pane.

## Query a registered server

1. Within the Local Server Groups or Central Management Servers, find the registered server you want to query.
1. Right-click on the registered server and select **New Query**.
1. A new query editor window opens and is connected to the server.

## Connect to a registered server in a Central Management Server (CMS)

When a user connects to a registered server in a CMS, they must enter the appropriate authentication and login information in the connection dialog. Connection information for individual registered servers isn't persisted within the CMS.

The `Microsoft.Data.SqlClient` (MDS) driver was updated to version 5.x with SSMS 20, which defaults to use **Mandatory (True)** for encryption, instead of **Optional (False)**. For more information, see [Connect with SQL Server Management Studio](../quickstarts/ssms-connect.md).

If there's no trusted certificate installed for the registered server to which you're trying to connect, you see the error:

```output
Cannot connect to <server>

A connection was successfully established with the server, but then an error occurred during the login process.
(provider: SSL Provider, error: 0 - > The certificate chain was issued by an authority that is not trusted.)
(Microsoft SQL Server, Error: -2146893019)
For help, click: https://docs.microsoft.com/sql/relational-databases/errors-events/mssqlserver--2146893019-database-engine-error

The certificate chain was issued by an authority that is not trusted
```

> [!NOTE]  
> You should install trusted certificates for your server when using **Mandatory** encryption.

To bypass this message for future connections to a registered server in a CMS, you can either:

- Connect to the registered server with **Trust server certificate** enabled for the connection.
- Enable the **Trust server certificate** option for the CMS.

> [!NOTE]  
> Starting with SSMS 21.4.8, when you connect to a registered server the connection information for that server is added to the Most Recently Used (MRU) list of connections, if it doesn't already exist. You don't need to modify the connection, for example enable **Trust Server Certificate** for subsequent connections, even after you restart SSMS. The MRU is available in the connection dialog, whether you connect to Object Explorer or a query editor.

To enable the **Trust server certificate** option for the CMS:

1. Go to the top level CMS.

1. Right-click on the CMS and select **Central Management Server Actions** > **Properties**. Check the box for **Trust server certificate**.

1. Select **Save**.

1. Go to **Tools** > **Options** > **SQL Server Object Explorer** > **Commands**, and under **Connection security**, for **Trust server certificate for imported connections**, select **Always**, then **Ok**.

## Multiserver queries

The Query Editor window in SQL Server Management Studio can connect to and query multiple instances of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] at the same time. For more information about how to execute [!INCLUDE [tsql](../includes/tsql-md.md)] statements on the servers in a server group at the same time, see [Execute statements against multiple servers simultaneously in SQL Server Management Studio](execute-statements-against-multiple-servers-simultaneously.md).

## Related content

- [Disconnect from a registered server in SQL Server Management Studio](disconnect-from-a-registered-server-sql-server-management-studio.md)
