---
title: Configure SQL Server Agent
description: Learn how to configure SQL Server Agent using SQL Server Management Studio, Transact-SQL, or SQL Server Management Objects.
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/01/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Agent, configuring"
  - "accounts [SQL Server], SQL Server Agent"
  - "SQL Server Agent, permissions"
  - "security [SQL Server], SQL Server Agent"
---

# Configure SQL Server Agent

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)] Enabling and disabling SQL Server Agent is currently not supported in SQL Managed Instance. SQL Agent is always running.

This article describes how to specify some configuration options for [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent during installation of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)]. The full set of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent configuration options is only available within SQL Server Management Studio (SSMS), [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Management Objects (SMO), or the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent stored procedures.

## Limitations

To administer jobs, operators, alerts, and the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent service, select **SQL Server Agent** in the Object Explorer of SSMS. Object Explorer only displays the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent node if you have permission to use it.

Auto-restart shouldn't be enabled for the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] service, or the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent service, on failover cluster instances.

## Permissions

To perform its functions, [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)]. The account must have the following Windows permissions:

- Log on as a service (`SeServiceLogonRight`)
- Replace a process-level token (`SeAssignPrimaryTokenPrivilege`)
- Bypass traverse checking (`SeChangeNotifyPrivilege`)
- Adjust memory quotas for a process (`SeIncreaseQuotaPrivilege`)

For more information about the Windows permissions required for the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent service account, see:

- [Select an account for the SQL Server Agent service](select-an-account-for-the-sql-server-agent-service.md)
- [Configure Windows service accounts and permissions](/sql/database-engine/configure-windows/configure-windows-service-accounts-and-permissions)

## How to configure SQL Server Agent

1. From the **Start** menu, navigate to **Control Panel**.

1. In Control Panel, select **System and Security**, select **Administrative Tools**, and then select **Local Security Policy**.

1. In Local Security Policy, select the chevron to expand the **Local Policies** folder, and then Select the **User Rights Assignment** folder.

1. Right-click a permission that you want to configure for use with [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] and select **Properties**.

1. In the permission's properties dialog box, verify that the account under which [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent runs is listed. If not, select **Add User or Group**, enter the account under which [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent runs in the **Select Users, Computers, Service Accounts, or Groups** dialog box, and then Select **OK**.

1. Repeat for each permission that you want to add to run with [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent. When finished, select **OK**.
