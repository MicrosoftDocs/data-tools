---
title: Select an Account for the SQL Server Agent Service
description: The service startup account defines the Microsoft Windows account in which SQL Server Agent runs and its network permissions.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: randolphwest
ms.date: 07/26/2024
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---

# Select an account for the SQL Server Agent service

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> On [Azure SQL Managed Instance](/azure/sql-database/sql-database-managed-instance), most, but not all SQL Server Agent features are currently supported. See [Azure SQL Managed Instance T-SQL differences from SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) for details.

The service startup account defines the Microsoft Windows account in which SQL Server Agent runs and its network permissions. SQL Server Agent runs as a specified user account. You select an account for the SQL Server Agent service by using SQL Server Configuration Manager, where you can choose from the following options:

- **Built-in account**. You can choose from a list of the following built-in Windows service accounts:

  - **Local System** account. The name of this account is NT AUTHORITY\System. it's a powerful account that has unrestricted access to all local system resources. it's a member of the Windows **Administrators** group on the local computer.

  > [!IMPORTANT]  
  > The **Local System account** option is provided for backward compatibility only. The Local System account has permissions that SQL Server Agent doesn't require. Avoid running SQL Server Agent as the Local System account. For improved security, use a Windows domain account with the permissions listed in the following section, "Windows Domain Account Permissions."

- **This account**. Lets you specify the Windows domain account in which the SQL Server Agent service runs. We recommend choosing a Windows user account that isn't a member of the Windows **Administrators** group. However, there are limitations for using multiserver administration when the SQL Server Agent service account isn't a member of the local **Administrators** group. For more information, see 'Supported Service Account Types' that follows in this article.

## Windows domain account permissions

For improved security, select **This account**, which specifies a Windows domain account. The Windows domain account that you specify must have the following permissions:

- In all Windows versions, permission to log on as a service (`SeServiceLogonRight`)

  > [!NOTE]  
  > The SQL Server Agent service account must be part of the Pre-Windows 2000 Compatible Access group on the domain controller, or jobs that are owned by domain users who aren't members of the Windows Administrators group fails.

- In Windows servers, the account that the SQL Server Agent Service runs as requires the following permissions can support SQL Server Agent proxies.

  - Permission to bypass traverse checking (`SeChangeNotifyPrivilege`)
  - Permission to replace a process-level token (`SeAssignPrimaryTokenPrivilege`)
  - Permission to adjust memory quotas for a process (`SeIncreaseQuotaPrivilege`)
  - Permission to access this computer from the network (`SeNetworkLogonRight`)

If the account doesn't have the permissions required to support proxies, only members of the **sysadmin** fixed server role can create jobs.

To receive Windows Management Instrumentation (WMI) alert notification, the service account for SQL Server Agent must have been granted permission to the namespace that contains the WMI events, and `ALTER ANY EVENT NOTIFICATION`.

## SQL Server role membership

By default, the SQL Server Agent service account is mapped to the default SQL Server Agent service SID (`NT SERVICE\SQLSERVERAGENT`), which is a member of the **sysadmin** fixed server role. The account must also be a member of the `msdb` database role **TargetServersRole** on the master server if multiserver job processing is used. The Master Server Wizard automatically adds the service account to this role as part of the enlistment process.

## Supported service account types

The following table lists the Windows account types that can be used for the SQL Server Agent service.

| Service account type | Nonclustered Server | Clustered server | Domain controller (nonclustered) |
| --- | --- | --- | --- |
| Microsoft Windows domain account (member of Windows Administrators group) | Supported | Supported | Supported |
| Windows domain account (non-administrative) | Supported<br /><br />See Limitation 1 later in this section. | Supported<br /><br />See Limitation 1 later in this section. | Supported<br /><br />See Limitation 1 later in this section. |
| Network Service account (`NT AUTHORITY\NetworkService`) | Supported<br /><br />See Limitation 1, 3, and 4 later in this section. | Not supported | Not supported |
| Local user account (non-administrative) | Supported<br /><br />See Limitation 1 later in this section. | Not supported | Not applicable |
| Local System account (`NT AUTHORITY\System`) | Supported<br /><br />See Limitation 2 later in this section. | Not supported | Supported<br /><br />See Limitation 2 later in this section. |
| Local Service account (`NT AUTHORITY\LocalService`) | Not supported | Not supported | Not supported |

### Limitation 1: Using non-administrative accounts for multiserver administration

Enlisting target servers to a master server might fail with the following error message: `The enlist operation failed.`

To resolve this error, restart both the SQL Server and the SQL Server Agent services. For more information, see [Start, stop, pause, resume, and restart SQL Server services](/sql/database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services).

### Limitation 2: Using the Local System account for multiserver administration

Multiserver administration is supported when the SQL Server Agent service is run under the Local System account only when both the master server and the target server reside on the same computer. If you use this configuration, the following message is returned when you enlist target servers to the master server:

```output
Ensure the agent start-up account for <target_server_computer_name> has rights to log on as targetServer.
```

You can ignore this informational message. The enlistment operation should complete successfully. For more information, see [Create a multiserver environment](create-a-multiserver-environment.md).

### Limitation 3: Using the Network Service account when it's a SQL Server user

The SQL Server Agent might fail to start if you run the SQL Server Agent service under the Network Service account, and the Network Service account is explicitly granted access to log into a SQL Server instance as a SQL Server user.

To resolve this, restart the computer where SQL Server is running. This only needs to be done once.

### Limitation 4: Using the Network Service account when SQL Server Reporting Services is running on the same computer

The SQL Server Agent might fail to start if you run the SQL Server Agent service under the Network Service account and [!INCLUDE [ssRSnoversion](../includes/ssrsnoversion-md.md)] is also running on the same computer.

To resolve this, restart the computer where SQL Server is running, and then restart both the SQL Server and the SQL Server Agent services. This only needs to be done once.

## Common tasks

- [Set the Service Startup Account for SQL Server Agent (SQL Server Configuration Manager)](set-service-startup-account-sql-server-agent-sql-server-configuration-manager.md)

- [Configure SQL Server Agent mail to use Database Mail](/sql/relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail)

Use SQL Server Configuration Manager to specify that SQL Server Agent must start up when the operating system starts.

## Related content

- [Configure Windows service accounts and permissions](/sql/database-engine/configure-windows/configure-windows-service-accounts-and-permissions)
- [SQL Server Configuration Manager: Connect to another computer](/sql/database-engine/configure-windows/scm-services-connect-to-another-computer)
- [Implement SQL Server Agent Security](implement-sql-server-agent-security.md)
