---
title: Rename a SQL Server Agent Error Log
description: "Rename a SQL Server Agent Error Log"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "logs [SQL Server], SQL Server Agent"
  - "renaming SQL Server Agent error log"
  - "SQL Server Agent, errors"
  - "errors [SQL Server Agent]"
---
# Rename a SQL Server Agent Error Log
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic describes how to rename the file where [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent errors are written in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio.  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Restrictions"></a>Limitations and Restrictions  
  
-   Object Explorer only displays the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent node if you have permission to use it.  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent will not write to the new log file until the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service is restarted.  
  
### <a name="Security"></a>Security  
  
#### <a name="Permissions"></a>Permissions  
To perform its functions, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. The account must have the following Windows permissions:  
  
-   Log on as a service (SeServiceLogonRight)  
  
-   Replace a process-level token (SeAssignPrimaryTokenPrivilege)  
  
-   Bypass traverse checking (SeChangeNotifyPrivilege)  
  
-   Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)  
  
For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Setting Up Windows Service Accounts](/sql/database-engine/configure-windows/configure-windows-service-accounts-and-permissions).  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To rename a SQL Server Agent error log  
  
1.  In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent error log that you want to rename.  
  
2.  Click the plus sign to expand **SQL Server Agent**.  
  
3.  Right-click the **Error Logs** folder and select **Configure**.  
  
4.  In the **Configure SQL Server Agent Error Logs** dialog box, in the **Error log file** box, enter the new file path and file name for the error log. Alternately, click the ellipsis **(...)** to open the **Specify agent error log location** dialog box.  
  
5.  When finished, click **OK**.  
