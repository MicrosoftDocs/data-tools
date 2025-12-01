---
title: View SQL Server Agent Error Log
description: View the SQL Server Agent error log using SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/01/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "logs [SQL Server], SQL Server Agent"
  - "viewing SQL Server Agent error logs"
  - "displaying SQL Server Agent error logs"
  - "SQL Server Agent, errors"
  - "errors [SQL Server Agent]"
---

# View the SQL Server Agent error log

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This article describes how to view the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent error log in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio.

Log File Viewer displays log information from many different components. When Log File Viewer is open, use the **Select logs** pane to select the logs you want to display. Each log displays columns appropriate to that kind of log. The logs that are available depend on how Log File Viewer is opened.

## Limitations

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

1. In **Object Explorer**, select the plus sign to expand the server that contains the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent error log that you want to view.

1. Select the plus sign to expand **SQL Server Agent**.

1. Select the plus sign to expand the **Error Logs** folder.

1. Right-click the error log you want to view and select **View Agent Log**.

   The following options are available in the **Log File Viewer -***server_name* dialog box:

   | Option | Description |
   | --- | --- |
   | **Load Log** | Open a dialog box where you can specify a log file to load. |
   | **Export** | Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file. |
   | **Refresh** | Refresh the view of the selected logs. The **Refresh** button rereads the selected logs from the target server while applying any filter settings. |
   | **Filter** | Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria. |
   | **Search** | Search the log file for specific text. Searching with wildcard characters isn't supported. |
   | **Stop** | Stops loading the log file entries. For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries. |
   | **Log file summary** | This information panel displays a summary of the log file filtering.<br /><br />If the file isn't filtered, you see the following text: **No filter applied**<br /><br />If a filter is applied to the log, you see the following text: **Filter log entries where:** \<filter criteria\> |
   | **Selected row details** | Select a row to display more details about the selected event row at the bottom of the page. The columns can be reordered by dragging them to new locations in the grid. The columns can be resized by dragging the column separator bars in the grid header to the left or right. Double-click the column separator bars in the grid header to automatically size the column to the content width. |
   | **Instance** | The name of the instance on which the event occurred. This name is displayed as `<computer name>\<instance name>`. |
   | **Date** | Displays the date of the event. |
   | **Source** | Displays the source feature from which the event is created, such as the name of the service (`MSSQLSERVER`, for example). This value doesn't appear for all log types. |
   | **Message** | Displays any messages associated with the event. |
   | **Log Type** | Displays the type of log to which the event belongs. All selected logs appear in the log file summary window. |
   | **Log Source** | Displays a description of the source log in which the event is captured. |

1. When finished, select **Close**.
