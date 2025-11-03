---
title: Register a Connected Server
description: Register a connected server in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.registerserver.f1"
helpviewer_keywords:
  - "Registered Servers [SQL Server], register connected servers"
  - "connected server registrations [SQL Server]"
---

# Register a connected server in SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This article describes how to register a connected server in SQL Server Management Studio (SSMS). By registering the server, you can save the connection information for servers that you access frequently. A server can be registered before connecting, or at the time of connection from Object Explorer. To view your registered servers in SSMS, select **View** > **Registered Servers**, or type **Ctrl**+**Alt**+**G**.

## Register a connected server

1. In Object Explorer, right-click a server to which you already are connected, and then select **Register**.

1. The **New Server Registration** dialog box appears. Enter the information for the server on the **General** page.

   | Setting | Description |
   | --- | --- |
   | **Server type** | When a connected server is registered, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers pane. |
   | **Server name** | For **Server name**, enter the fully qualified name of your SQL Server (you can also use *localhost* as the server name if you're connecting locally). If you *aren't* using the default instance (`MSSQLSERVER`), you must enter in the server name and the instance name.<br /><br />If you're unsure how to determine your SQL Server instance name, see [Find SQL Server instance name](../tutorials/ssms-tricks.md#find-sql-server-instance-name). |
   | **Authentication** | Windows Authentication is set as default.<br /><br />You can also use **SQL Server Authentication** to connect. However, if you select **SQL Server Authentication**, a username and password are required.<br /><br />**Microsoft Entra authentication** is available for [!INCLUDE [sssql22-md](../includes/sssql22-md.md)] and later versions. For step-by-step configuration instructions, see [Tutorial: Set up Microsoft Entra authentication for SQL Server with app registration](/sql/relational-databases/security/authentication-access/azure-ad-authentication-sql-server-setup-tutorial)<br /><br />For more information about authentication types, see [Connect to Server (Login page) - Database Engine](../f1-help/connect-to-server-login-page-database-engine.md). |
   | **Login** | The user ID from the server account used to sign in to the server. A login is required when using **SQL Server Authentication**. |
   | **Password** | The password from the server account used to sign in to the server. A password is required when using **SQL Server Authentication**. |
   | **Remember password** | Select to have [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] encrypt and store the password you entered. This option is displayed only if you have selected to connect using [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Authentication. |
   | **Encryption** <sup>1</sup> | Select the encryption level for the connection. The default value is *Mandatory*. |
   | **Trust server certificate** | Check this option to bypass server certificate validation. The default value is *False* (unchecked), which promotes better security using trusted certificates. |
   | **Host Name in Certificate** | The value provided in this option is used to specify a different, but expected, CN or SAN in the server certificate. |
   | **Registered server name** | The name you want to appear in Registered Servers. This name doesn't have to match the **Server name** box. |
   | **Registered server description** | Enter an optional description of the server. |

   <sup>1</sup> [!INCLUDE [ssms-encryption](../includes/ssms-encryption.md)]

   You can modify extra connection options by selecting **Options**. Examples of connection options include the connection timeout value, [application intent](/sql/database-engine/availability-groups/windows/listeners-client-connectivity-application-failover#ConnectToSecondary), and the [network protocol](/sql/sql-server/connect-to-database-engine#network-protocol-considerations). This article uses default values for these fields.

   > [!NOTE]  
   > If you stored the password and want to stop storing it, clear this check box, and then select **Save**.

1. After you complete all the fields, select **Test** to test the connection to the server.

1. Select **Save** to save the registered server settings.

By default, the connected server is added to the Local Server Groups folder. To move the registered server to another server group, see [Move a registered server or registered server group in SQL Server Management Studio](move-a-registered-server-or-registered-server-group.md).

## Related content

- [Create a new registered server in SQL Server Management Studio](create-a-new-registered-server-sql-server-management-studio.md)
