---
title: Create a New Registered Server
description: An overview of how to create a new registered server in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.registerserver.general.sqlce.f1"
  - "sql13.swb.registerserver.general.sqlserver.f1"
helpviewer_keywords:
  - "Registered Servers [SQL Server], creating new registered servers"
---

# Create a new registered server in SQL Server Management Studio

[!INCLUDE [sqlserver](../includes/applies-to-version/sqlserver.md)]

This article describes how to save information for servers that you access frequently, by registering the server in the Registered Servers component of SQL Server Management Studio (SSMS). A server can be registered before connecting, or once connected from Object Explorer.

There are two kinds of registered servers:

- **Local server groups**

  Use local server groups to easily connect to servers that you frequently manage. Local server groups are unique to each user.

  For information about how to share registered server information, see:

  - [Export registered server information in SQL Server Management Studio](export-registered-server-information-sql-server-management-studio.md)
  - [Import registered server information in SQL Server Management Studio](import-registered-server-information-sql-server-management-studio.md)

  > [!NOTE]  
  > Use Windows Authentication whenever possible.

- **Central Management Servers**

  Central Management Servers store server registrations in the Central Management Server (CMS) instead of on the file system. After a Central Management Server has been registered, its existing registered servers will be automatically displayed. For more information about Central Management Servers, see [Administer multiple servers using Central Management Servers](/sql/relational-databases/administer-multiple-servers-using-central-management-servers).

  [!INCLUDE [sql2008-md](../includes/sql2008-md.md)] and earlier versions can't be designated as a CMS.

## Create a new registered server (local server groups)

If the Registered Servers tool window isn't visible in SQL Server Management Studio, select **View** > **Registered Servers**, or type **Ctrl**+**Alt**+**G**.

1. In **Local Server Groups**, right-click on a server group select **New Server Registration...**.

1. The **New Server Registration** dialog box appears. Enter the information for the server on the **General** page.

   | Setting | Description |
   | --- | --- |
   | **Server type** | When a server is registered from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers pane. To register a different type of server, select **Database Engine**, **Analysis Server**, **Reporting Services**, or **Integration Services** on the **Registered Servers** toolbar before starting to register a new server. |
   | **Server name** | For **Server name**, enter the fully qualified name of your SQL Server (you can also use *localhost* as the server name if you're connecting locally). If you *aren't* using the default instance (`MSSQLSERVER`), you must enter in the server name and the instance name.<br /><br />If you're unsure how to determine your SQL Server instance name, see [Find SQL Server instance name](../tutorials/ssms-tricks.md#find-sql-server-instance-name). |
   | **Authentication** | Windows Authentication is set as default.<br /><br />You can also use **SQL Server Authentication** to connect. However, if you select **SQL Server Authentication**, a username and password are required.<br /><br />**Microsoft Entra authentication** is available for [!INCLUDE [sssql22-md](../includes/sssql22-md.md)] and later versions. For step-by-step configuration instructions, see [Tutorial: Set up Microsoft Entra authentication for SQL Server with app registration](/sql/relational-databases/security/authentication-access/azure-ad-authentication-sql-server-setup-tutorial)<br /><br />For more information about authentication types, see [Connect to Server (Login page) - Database Engine](../f1-help/connect-to-server-login-page-database-engine.md). |
   | **Login** | The user ID from the server account used to sign in to the server. A login is required when using **SQL Server Authentication**. |
   | **Password** | The password from the server account used to sign in to the server. A password is required when using **SQL Server Authentication**. |
   | **Remember password** | Select to have [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] encrypt and store the password you entered. This option is displayed only if you have selected to connect using [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Authentication. |
   | **Encryption** <sup>1</sup> | Select the encryption level for the connection. The default value is *Mandatory*. |
   | **Trust server certificate** | Check this option to bypass server certificate validation. The default value is *False* (unchecked), which promotes better security using trusted certificates. |
   | **Host Name in Certificate** | The value provided in this option is used to specify a different, but expected, CN or SAN in the server certificate. |

   <sup>1</sup> [!INCLUDE [ssms-encryption](../includes/ssms-encryption.md)]

   You can modify extra connection options by selecting **Options**. Examples of connection options include the connection timeout value, [application intent](/sql/database-engine/availability-groups/windows/listeners-client-connectivity-application-failover#ConnectToSecondary), and the [network protocol](/sql/sql-server/connect-to-database-engine#network-protocol-considerations). This article uses default values for these fields.

   > [!NOTE]  
   > If you have stored the password and want to stop storing it, clear this check box, and then select **Save**.

1. After you complete all the fields, select **Test** to test the connection to the server.

1. Select **Save** to save the registered server settings.

## Create a new registered server (Central Management Servers)

If the Registered Servers pane isn't visible in SQL Server Management Studio, select **View** > **Registered Servers**, or type **Ctrl**+**Alt**+**G**.

1. Within **Central Management Servers**, right-click on a CMS, or a server group, and select **New Server Registration...**.

1. The **New Server Registration** dialog box appears. Enter the information for the server; this is the only information that is stored for a registered server in a CMS.

   | Setting | Description |
   | --- | --- |
   | **Server name** | Enter the name of your SQL Server (you can also use *localhost* as the server name if you're connecting locally). If you *aren't* using the default instance (`MSSQLSERVER`), you must enter in the server name and the instance name.<br /><br />If you're unsure how to determine your SQL Server instance name, see [Find SQL Server instance name](../tutorials/ssms-tricks.md#find-sql-server-instance-name). |
   | **Registered server name** | The default value is the same as the **Server name**. Change this to a more friendly or readable name if appropriate. |
   | **Registered server description** | Description of the registered server. |

1. Select **Save** to save the registered server settings.

## Related content

- [Export registered server information in SQL Server Management Studio](export-registered-server-information-sql-server-management-studio.md)
- [Import registered server information in SQL Server Management Studio](import-registered-server-information-sql-server-management-studio.md)
- [Administer multiple servers using Central Management Servers](/sql/relational-databases/administer-multiple-servers-using-central-management-servers)
