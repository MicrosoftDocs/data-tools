---
title: "Create a SQL Server Agent Proxy"
description: Create a SQL Server Agent Proxy using SQL Server Management Studio, or in Transact-SQL.
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/07/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "proxies [SQL Server Agent], creating"
---
# Create a SQL Server Agent proxy

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

This article describes how to create a SQL Server Agent proxy in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio or [!INCLUDE [tsql](../includes/tsql-md.md)].

A [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent proxy account defines a security context in which a job step can run. Each proxy corresponds to a security credential. To set permissions for a particular job step, create a proxy that has the required permissions for a [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent subsystem, and then assign that proxy to the job step.

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

## Limitations

You must create a credential before you create a proxy if one isn't already available.

[!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts. The user specified in the credential must have **Access this computer from the network** permission (`SeNetworkLogonRight`) on the computer on which [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] is running.

[!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs. If the proxy no longer has access to the subsystem, the job step fails. Otherwise, [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step. For a list of proxy subsystems, see [sp_grant_proxy_to_subsystem](/sql/relational-databases/system-stored-procedures/sp-grant-proxy-to-subsystem-transact-sql).

Creation of a proxy doesn't change the permissions for the user that is specified in the credential for the proxy. For example, you can create a proxy for a user that doesn't have permission to connect to an instance of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)]. In this case, job steps that use that proxy are unable to connect to [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)].

If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.

## Permissions

Only members of the **sysadmin** fixed server role have permission to create, modify, or delete proxy accounts. Users who aren't members of the **sysadmin** fixed server role must be added to one of the following [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles in the `msdb` database to use proxies:

**SQLAgentUserRole**
**SQLAgentReaderRole**
**SQLAgentOperatorRole**

Requires `ALTER ANY CREDENTIAL` permission if creating a credential in addition to the proxy.

<a id="SSMSProcedure"></a>

## Use SQL Server Management Studio (SSMS)

1. In **Object Explorer**, select the plus sign to expand the server where you want to create a proxy on SQL Server Agent.

1. Select the plus sign to expand **SQL Server Agent**.

1. Right-click the **Proxies** folder and select **New Proxy**.

1. On the **New Proxy Account** dialog box, on the **General** page, enter the name of the proxy account in the **Proxy name** box.

1. In the **Credential name** box, enter the name of the security credential that the proxy account will use.

1. In the **Description** box, enter a description for the proxy account

1. Under **Active to the following subsystems**, select the appropriate subsystem or subsystems for this proxy.

1. On the **Principals** page, add or remove logins or roles to grant or remove access to the proxy account.

1. When finished, select **OK**.

<a id="TsqlProcedure"></a>

## Use Transact-SQL

The following script creates a credential called `CatalogApplicationCredential`, creates proxy `Catalog application proxy` and assigns the credential `CatalogApplicationCredential` to it, and grants the proxy access to the ActiveX Scripting subsystem.

1. Create credential `CatalogApplicationCredential`.

   ```sql
   USE msdb;
   GO

   CREATE CREDENTIAL CatalogApplicationCredential
       WITH IDENTITY = 'REDMOND/TestUser', SECRET = 'G3$1o)lkJ8HNd!';
   GO
   ```

1. Create proxy `Catalog application proxy` and assign the credential `CatalogApplicationCredential` to it.

   ```sql
   EXECUTE dbo.sp_add_proxy
       @proxy_name = 'Catalog application proxy',
       @enabled = 1,
       @description = 'Maintenance tasks on catalog application.',
       @credential_name = 'CatalogApplicationCredential';
   GO
   ```

1. Grant the proxy `Catalog application proxy` access to the ActiveX Scripting subsystem.

   ```sql
   EXECUTE dbo.sp_grant_proxy_to_subsystem
       @proxy_name = N'Catalog application proxy',
       @subsystem_id = 2;
   GO
   ```

## Related content

- [CREATE CREDENTIAL (Transact-SQL)](/sql/t-sql/statements/create-credential-transact-sql)
- [sp_add_proxy (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-add-proxy-transact-sql)
- [sp_grant_proxy_to_subsystem (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-grant-proxy-to-subsystem-transact-sql)
