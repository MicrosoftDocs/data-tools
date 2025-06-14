---
title: "Format Pager Addresses for Alerts"
description: "Format Pager Addresses for Alerts"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "pager addresses [SQL Server]"
  - "SQL Server Agent, alerts"
  - "formats [SQL Server], pager addresses"
  - "pager notifications [SQL Server]"
  - "addresses [SQL Server]"
  - "alerts [SQL Server], pager addresses"
---
# Format Pager Addresses for Alerts
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic describes how to format pager addresses for [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio or [!INCLUDE[tsql](../includes/tsql-md.md)].  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Security"></a>Security  
  
#### <a name="Permissions"></a>Permissions  
By default, members of the **sysadmin** fixed server role can view information about an alert. Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To format pager addresses  
  
1.  In **Object Explorer**, click the plus sign to expand the server that contains the alert that you want to send to a pager.  
  
2.  Right-click **SQL Server Agent** and select **Properties**  
  
3.  Under **Select a page**, select **Alert System**.  
  
4.  In the **To line** and **CC line** boxes of the **Address formatting for pager e-mails** field, enter the pager address prefix or suffix. The operator's actual pager address is inserted when a notification is sent.  
  
5.  In the **Subject** box, enter the subject line prefix or suffix.  
  
6.  Select the **Include body of e-mail in notification page** check box to include the full e-mail message with the pager message (as opposed to the subject line only).  
  
7.  When finished, click **OK**.  
