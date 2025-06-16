---
title: "SQL Server Agent Properties (Job System Page)"
description: "SQL Server Agent Properties (Job System Page)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.ag.agent.job.f1"
---
# SQL Server Agent Properties (Job System Page)
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

Use this page to view and modify how the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent Service manages jobs.  
  
## Options  
**Shutdown time-out interval (in seconds)**  
Specifies the number of seconds that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent waits for jobs to complete before shutting down. If the job is still running after the interval specified, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent forcefully stops the job.  
  
**Use a non-administrator proxy account**  
Sets a non-administrator proxy account for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent. [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[sql2008-md](../includes/sql2008-md.md)] and later versions support multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[sql2008-md](../includes/sql2008-md.md)].  
  
**User name**  
Type the name of the user for the non-administrator proxy account. [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] supports multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[sql2008-md](../includes/sql2008-md.md)].  
  
**Password**  
Type the password of the user for the non-administrator proxy account. [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] and later versions support multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)].  
  
**Domain**  
Type the domain of the user for the non-administrative proxy account. [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] supports multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[sql2008-md](../includes/sql2008-md.md)].  
  
## See Also  
[Implement Jobs](implement-jobs.md)  
