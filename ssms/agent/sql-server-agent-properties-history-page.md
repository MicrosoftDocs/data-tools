---
title: "SQL Server Agent Properties (History Page)"
description: "SQL Server Agent Properties (History Page)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.ag.agent.history.f1"
---
# SQL Server Agent Properties (History Page)
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

Use this page to view and modify settings for managing the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service history log.  
  
## Options  
**Limit size of job history log**  
Sets limits for the amount of job history information that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent retains in the log.  
  
**Maximum job history log size (in rows)**  
Sets the maximum number of rows that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent retains. When the log grows to contain this number of rows, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent removes the oldest rows in the log as new rows are entered.  
  
**Maximum job history rows per job**  
Sets the maximum number of rows that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent retains per job. When the history for a particular job grows to contain this number of rows, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent removes the oldest rows in the log as new rows are entered.  
  
**Remove agent history**  
Specifies that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent will remove entries that have been in the log longer than a specified length of time. This is a one-time execution to remove the history. If a reoccurring job is needed, create and schedule a maintenance plan with a cleanup job.  
  
**Older than**  
Sets the amount of time that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent will retain entries.  
  
## See Also  
[SQL Server Agent Error Log](sql-server-agent-error-log.md)  
