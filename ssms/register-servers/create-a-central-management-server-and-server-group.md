---
title: Create a Central Management Server
description: Overview of creating a Central Management Server and Server Group in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "configuration server"
---

# Create a Central Management Server and server group in SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This article describes how to designate an instance of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] as a Central Management Server (CMS) in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] using SQL Server Management Studio (SSMS). A CMS stores a list of instances of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] that is organized into one or more groups. Actions that are taken by using a CMS server group act on all servers in the group. This includes connecting to servers by using Object Explorer and executing [!INCLUDE [tsql](../includes/tsql-md.md)] statements and Policy-Based Management policies on multiple servers at the same time.

> [!NOTE]  
> [!INCLUDE [sql2008-md](../includes/sql2008-md.md)] and earlier versions can't be designated as a CMS.

## Permissions

Two database roles in the `msdb` database grant access to Central Management Servers. Only members of the **ServerGroupAdministratorRole** role can manage the CMS. Membership in the **ServerGroupReaderRole** role is required to connect to a CMS.

Because the connections that are maintained by a CMS execute in the context of the user, the effective permissions on the registered servers can vary. For example, the user might be a member of the **sysadmin** fixed server role on the instance of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] A, but have limited permissions on the instance of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] B.

## Create a central management server

If the Registered Servers tool window isn't visible in SSMS, select **View** > **Registered Servers**, or type **Ctrl**+**Alt**+**G**.

1. In the Registered Servers pane, expand **Database Engine**, right-click **Central Management Servers**, and then select **Register Central Management Server...**.

1. In the **New Server Registration** dialog, enter the information for the instance of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] that you want to be the CMS.

| Setting | Description |
| --- | --- |
| **Server type** | The **Server type** box is read-only. Only a **Database Engine** can be a CMS. |
| **Server name** | For **Server name**, enter the fully qualified name of your SQL Server (you can also use *localhost* as the server name if you're connecting locally). If you *aren't* using the default instance (`MSSQLSERVER`), you must enter in the server name and the instance name.<br /><br />If you're unsure how to determine your SQL Server instance name, see [Find SQL Server instance name](../tutorials/ssms-tricks.md#find-sql-server-instance-name). |
| **Authentication** | Windows Authentication is set as default.<br /><br />You can also use **SQL Server Authentication** to connect. However, if you select **SQL Server Authentication**, a username and password are required.<br /><br />**Microsoft Entra authentication** is available for [!INCLUDE [sssql22-md](../includes/sssql22-md.md)] and later versions. For step-by-step configuration instructions, see [Tutorial: Set up Microsoft Entra authentication for SQL Server with app registration](/sql/relational-databases/security/authentication-access/azure-ad-authentication-sql-server-setup-tutorial)<br /><br />For more information about authentication types, see [Connect to Server (Login page) - Database Engine](../f1-help/connect-to-server-login-page-database-engine.md). |
| **Login** | The user ID from the server account used to sign in to the server. A login is required when using **SQL Server Authentication**. |
| **Password** | The password from the server account used to sign in to the server. A password is required when using **SQL Server Authentication**. |
| **Remember password** | Select to have [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] encrypt and store the password you have entered. This option is displayed only if you have selected to connect using [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Authentication. |
| **Encryption** <sup>1</sup> | Select the encryption level for the connection. The default value is *Mandatory*. |
| **Trust server certificate** | Check this option to bypass server certificate validation. The default value is *False* (unchecked), which promotes better security using trusted certificates. |
| **Host Name in Certificate** | The value provided in this option is used to specify a different, but expected, CN or SAN in the server certificate. |

<sup>1</sup> [!INCLUDE [ssms-encryption](../includes/ssms-encryption.md)]

You can modify more connection options by selecting **Options**. Examples of connection options include the connection timeout value, [application intent](/sql/database-engine/availability-groups/windows/listeners-client-connectivity-application-failover#ConnectToSecondary), and the [network protocol](/sql/sql-server/connect-to-database-engine#network-protocol-considerations). This article uses default values for these fields.

### Create a new server group and add servers to the group

1. From **Registered Servers**, expand **Central Management Servers**. Right-click the instance of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] added in the previous steps and select **New Server Group**.

1. In **New Server Group Properties**, enter a group name and optional description.

1. From **Registered Servers**, right-click the server group and select **New Server Registration**.

1. From New Server Registration, select an instance of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)]. For more information, see [Create a new registered server in SQL Server Management Studio](create-a-new-registered-server-sql-server-management-studio.md).

1. Repeat these steps to add more servers to the server group.

### Execute multi-server queries

After you create a CMS, one or more server groups, and one or more registered servers, you can execute queries against a group of servers at the same time. For more information about how to execute [!INCLUDE [tsql](../includes/tsql-md.md)] statements on the servers in a server group at the same time, see [Execute statements against multiple servers simultaneously in SQL Server Management Studio](execute-statements-against-multiple-servers-simultaneously.md).

## Related content

- [Administer multiple servers using Central Management Servers](/sql/relational-databases/administer-multiple-servers-using-central-management-servers)
