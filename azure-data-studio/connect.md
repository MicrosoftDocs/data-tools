---
title: "Connect to a SQL Server Instance"
description: Explains the connection parameters to connect to an instance of SQL Server with Azure Data Studio. Includes details about how to secure and encrypt connections.
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest, maghan
ms.date: 02/06/2025
ms.service: azure-data-studio
ms.topic: "how-to"
ms.collection:
  - data-tools
---

# Connect with Azure Data Studio

[!INCLUDE [azure-data-studio-deprecation](includes/azure-data-studio-deprecation.md)]

This article describes how to connect to SQL Server with Azure Data Studio 1.40 and higher.

> [!NOTE]  
> [!INCLUDE [azure-active-directory-microsoft-entra-id](includes/azure-active-directory-microsoft-entra-id.md)]

## Sql Authentication Provider

Azure Data Studio 1.44 and later defaults to use the Sql Authentication Provider for Azure SQL connections and the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview). This provider is used with the **Microsoft Entra ID - Universal with MFA support** authentication mode and enables server-side resource endpoint integration when fetching access tokens. 

After a user upgrades to Azure Data Studio 1.44 and higher, the initial launch of the application will display the following message:

:::image type="content" source="connect/connect-update-after-upgrade-no-tenant.png" alt-text="Screenshot of message about tenant list box removal after upgrading Azure Data Studio.":::

With the Sql Authentication Provider, selection of a tenant is no longer required.  The Microsoft Entra tenant list box has been removed from the Connection dialog because it's now handled by the underlying driver.  This change also allows for improved token refresh for Azure SQL Database connections.

The **Mssql: Enable Sql Authentication Provider** option can be disabled within **File** > **Preferences** > **Settings**.

## Encrypt and Trust server certificate

Azure Data Studio 1.40 and later includes an important change to the **Encrypt** property, which is now enabled (set to **True**) by default for MSSQL provider connections, and SQL Server must be configured with TLS certificates signed by a trusted root certificate authority. In addition, the **Encrypt** and **Trust server certificate** properties have moved from the **Advanced** pane to the front of the **Connection Details** pane. Both properties have information icons to provide more detail on hover. The [best practice](/sql/relational-databases/security/securing-sql-server) is to support a trusted encrypted connection to the server.

For users connecting to Azure SQL Database, no changes to existing, saved connections in Azure Data Studio are needed; Azure SQL Database supports encrypted connections and is configured with trusted certificates.

For users connecting to on-premises SQL Server, or SQL Server in a Virtual Machine, if **Encrypt** is configured with a value of **True**, ensure that you have a certificate from a trusted certificate authority (e.g. not a self-signed certificate). Alternatively, you may choose to connect without encryption (**Encrypt** set to **False**), or to trust the server certificate (**Encrypt** set to **True** and **Trust server certificate** set to **True**).

## New installation of Azure Data Studio 1.40 and higher

For workstations with a new installation:

1. Select **New Connection** on the **Welcome** page to open the **Connection** pane.
2. From the **Connection** pane, select  **Servers** > **New Connection**.  Azure Data Studio shows **Connection Details**.

:::image type="content" source="connect/connect-connection-details.png" alt-text="Screenshot of Connection Details.":::

3. Set the connection details for your server.

## Connection detail description

- **Server Name:** Enter server name here. For example, localhost.
- **Authentication Type:** SQL Login
- **User name:** User name for the SQL Server
- **Password:** Password for the SQL Server
- **Encrypt:** Default value is True
- **Trust server certificate:** Default value is False
- **Database Name:** \<Default\>
- **Server Group:** \<Default\>

## Connections after upgrading to Azure Data Studio 1.40 and higher

After a user upgrades to Azure Data Studio 1.40 and higher, the initial launch of the application will display the following message:

:::image type="content" source="connect/connect-import-update-after-upgrade.png" alt-text="Screenshot of important update message after upgrading Azure Data Studio.":::

You should review the options selected for **Encrypt** and **Trust server certificate** for existing connections in Azure Data Studio before connecting. In some scenarios, it may be necessary to configure a signed certificate, or change the value for one or both properties.  

## More information

These changes are the result of updates at the driver level in Microsoft.Data.SqlClient. Recent releases of Microsoft.Data.SqlClient have offered increased security in the connection options. Read more in the [release notes](/sql/connect/ado-net/introduction-microsoft-data-sqlclient-namespace) for Microsoft.Data.SqlClient.

If you have previously been connecting to a SQL Server that doesn't have encrypted connections enable and would like to enable encryption, you'll be prompted to trust server certificate. You may choose to connect with the 'Trust Server Certificate' property enabled, or cancel and review client configuration to verify a valid server certificate is installed. For more information, please visit the [SQL Server documentation](/sql/database-engine/configure-windows/configure-sql-server-encryption).

## Next steps

- [Quickstart: Use Azure Data Studio to connect and query SQL Server](quickstart-sql-server.md)
