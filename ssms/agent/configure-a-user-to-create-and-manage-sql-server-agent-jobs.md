---
title: Configure a User to Create and Manage SQL Server Agent Jobs
description: Learn how to configure a user to create and manage SQL Server Agent Jobs.
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/07/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Agent jobs, user configuration"
  - "jobs [SQL Server Agent], user configuration"
  - "SQLAgentUserRole database role"
  - "proxy accounts [SQL Server Agent]"
---

# Configure a user to create and manage SQL Server Agent jobs

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This article describes how to configure a user to create or execute [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs.

## Security

To configure a user to create or execute [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs, you must first add an existing SQL Server login or `msdb` role to one of the following [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles in the `msdb` database:

- **SQLAgentUserRole**
- **SQLAgentReaderRole**
- **SQLAgentOperatorRole**

By default, members of these database roles can create their own job steps that run as themselves. If these non-administrative users want to run jobs that execute other job step types (for example, [!INCLUDE [ssIS](../includes/ssis-md.md)] packages), they must have access to a proxy account. All members of the **sysadmin** fixed server role have permission to create, modify, and delete proxy accounts. For more information about the permissions that are associated with these [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent fixed database roles](sql-server-agent-fixed-database-roles.md).

### Permissions

For detailed information, see [Implement SQL Server Agent security](implement-sql-server-agent-security.md).

<a id="SSMS"></a>

## Use SQL Server Management Studio

### Add a SQL login or msdb role to a SQL Server Agent fixed database role

1. In **Object Explorer**, expand a server.

1. Expand **Security**, and then expand **Logins**.

1. Right-click the login you wish to add to a [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database role, and select **Properties**.

1. On the **User Mapping** page of the **Login Properties** dialog box, select the row containing `msdb`.

1. Under **Database role membership for: msdb**, check the appropriate [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database role.

### Configure a proxy account to create and manage SQL Server Agent job steps

1. In **Object Explorer**, expand a server.

1. Expand **SQL Server Agent**.

1. Right-click **Proxies** and select **New Proxy**.

1. On the **General** page of the **New Proxy Account** dialog, specify the proxy name, credential name, and description for the new proxy. You must create a credential first before creating a SQL Server Agent proxy. For more information about creating a credential, see [Create a Credential](/sql/relational-databases/security/authentication-access/create-a-credential) and [CREATE CREDENTIAL](/sql/t-sql/statements/create-credential-transact-sql).

1. Check the appropriate subsystems for this proxy.

   1. [Create a CmdExec Job Step](create-a-cmdexec-job-step.md)
   1. [SQL Server Analysis Services Query](create-an-analysis-services-job-step.md#to-create-an-analysis-services-query-job-step)
   1. [SQL Server Analysis Services Command](create-an-analysis-services-job-step.md#to-create-an-analysis-services-command-job-step-1)
   1. [Run Integration Services (SSIS) Packages](/sql/integration-services/packages/run-integration-services-ssis-packages)
   1. [PowerShell](/powershell/sql-server/run-windows-powershell-steps-in-sql-server-agent)

1. On the **Principals** page, add or remove logins or roles to grant or remove access to the proxy account.

## Related content

- [Implement SQL Server Agent security](implement-sql-server-agent-security.md)
