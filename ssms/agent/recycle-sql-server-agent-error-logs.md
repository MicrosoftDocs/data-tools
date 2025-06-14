---
title: "Recycle SQL Server Agent Error Logs"
description: "Recycle SQL Server Agent Error Logs"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.ag.errorlog.recyclesqlagenterrorlogs.f1"
---
# Recycle SQL Server Agent Error Logs
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

Use this page to recycle the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent Error Logs. Recycling the log closes the current [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent error log and starts a new error log without restarting the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service. Notice that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent maintains the nine most recent error logs. If there are already nine error logs present, recycling the error log causes [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to remove the oldest error log.  
  
## See Also  
[SQL Server Agent Error Log](sql-server-agent-error-log.md)  
