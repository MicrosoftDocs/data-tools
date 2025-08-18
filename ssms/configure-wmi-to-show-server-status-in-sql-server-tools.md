---
title: "Configure WMI to Show Server Status in SQL Server Tools"
description: "Configure WMI to Show Server Status in SQL Server Tools"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/15/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "WMI Provider for Server Events, setting permissions"
  - "WMI permissions [SQL Server]"
---
# Configure WMI to show server status in SQL Server tools

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This article describes how to configure WMI to show the server status in SQL Server tools in [!INCLUDE [ssnoversion](includes/ssnoversion-md.md)]. When connecting to servers, both the Registered Servers and Object Explorer components of [!INCLUDE [ssManStudioFull](includes/ssmanstudiofull-md.md)], as well as [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] Configuration Manager, use Windows Management Instrumentation (WMI) to obtain the status of the [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] (MSSQLSERVER) and [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] Agent (MSSQLSERVER) services.

To display the status of the service, the user must have rights to remotely access the WMI object. The server must have WMI installed to configure this permission.

## Configure WMI permission

1. On the **Start** menu on the remote server, select **Run**.

1. In the **Open** box, type `wmimgmt.msc`, and then select **OK**.

1. In the **Windows Management Infrastructure** program, right-click **WMI Control (Local)**, and then select **Properties**.

1. In the **WMI Control (Local) Properties** dialog box, on the **Security** tab, expand **Root**, and then select **CIMV2**.

1. Select **Security** to open the **Security for ROOT\CIMV2** dialog box.

1. Add a group or user to the **Group or user names** box and select it.

1. In the **Permissions for***\<group or user\>* box, select the **Allow** column, for the **Remote Enable** permission, for users whom you wish to remotely detect the service status.

## Related content

- [Start, stop, or pause the SQL Server Agent service](agent/start-stop-or-pause-the-sql-server-agent-service.md)
