---
title: Start, Stop, or Pause the SQL Server Agent Service
description: Start, stop, or pause the SQL Server Agent service using SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/01/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Agent, starting"
  - "SQL Server Agent, pausing"
  - "SQL Server Agent, stopping"
---

# Start, stop, or pause the SQL Server Agent service

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This article describes how to start, stop, or restart the SQL Server Agent Service in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio.

You can configure the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent service to start automatically when the operating system starts, or you can start it manually when you need to complete jobs. You can stop or pause the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent service to suspend jobs, operator notifications, and alerts.

## Limitations

[!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent must be running as a service in order to automate administrative tasks. For more information, see [Configure SQL Server Agent](configure-sql-server-agent.md).

Object Explorer only displays the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent node if you have permission to use it.

## Permissions

To perform its functions, [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)]. The account must have the following Windows permissions:

- Log on as a service (`SeServiceLogonRight`)
- Replace a process-level token (`SeAssignPrimaryTokenPrivilege`)
- Bypass traverse checking (`SeChangeNotifyPrivilege`)
- Adjust memory quotas for a process (`SeIncreaseQuotaPrivilege`)

For more information about the Windows permissions required for the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent service account, see [Select an account for the SQL Server Agent service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows service accounts and permissions](/sql/database-engine/configure-windows/configure-windows-service-accounts-and-permissions).

<a id="SSMSProcedure"></a>

## Use SQL Server Management Studio

1. In **Object Explorer**, select the plus sign to expand the server where you want to manage SQL Server Agent Service.

1. Right-click **SQL Server Agent**, and then select either **Start**, **Stop**, or **Restart**.

1. In the **User Account Control** dialog box, select **Yes**.

1. When prompted if you want to perform the action, select **Yes**.

## Related content

- [Start, stop, pause, resume, and restart SQL Server services](/sql/database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services)
- [Auto Restart SQL Server Agent](autorestart-sql-server-agent-sql-server-management-studio.md)
