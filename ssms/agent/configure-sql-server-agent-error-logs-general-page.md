---
title: "Configure Error Logs (General Page)"
description: "Configure SQL Server Agent Error Logs (General Page)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.ag.errorlog.configure.f1"
---

# Configure SQL Server Agent Error Logs (General Page)

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

Use this screen to view and update settings for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent error logging.  
  
## Options  
**Error log file**  
Specifies the file to which [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent writes error logs.  
  
**...**  
Browse to the error log file.  
  
**Write OEM error log**  
Writes the error log file as a non-Unicode file. This reduces the amount of disk space consumed by the log file. However, messages that include Unicode data may be more difficult to read when this option is enabled.  
  
**Errors**  
Writes only errors and informational messages to the log file.  
  
**Warnings**  
Writes only warnings and informational messages to the log file.  
  
**Information**  
Writes only informational messages to the log file.  
  
## See Also  
[SQL Server Agent Error Log](sql-server-agent-error-log.md)  
