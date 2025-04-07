---
title: SQL Server Agent Error Log
description: "SQL Server Agent Error Log"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: conceptual
ms.collection:
  - data-tools
helpviewer_keywords:
  - "logs [SQL Server], SQL Server Agent"
  - "messages [SQL Server], SQL Server Agent"
  - "errors [SQL Server], logs"
  - "SQL Server Agent, errors"
---

# SQL Server Agent Error Log

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> On [Azure SQL Managed Instance](/azure/sql-database/sql-database-managed-instance), most, but not all SQL Server Agent features are currently supported. See [Azure SQL Managed Instance T-SQL differences from SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) for details.

[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent creates an error log that records warnings and errors by default. The following warnings and errors are displayed in the log:  
  
-   Warning messages that provide information about potential problems, such as "Job \<*job_name*> was deleted while it was running."  
  
-   Error messages that usually require intervention by a system administrator, such as "Unable to start mail session." Error messages can be sent to a specific user or computer by **net send**.  
  
[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] maintains up to nine [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent error logs. Each archived log has an extension that indicates the relative age of the log. For example, an extension of .1 indicates the newest archived error log and an extension of .9 indicates the oldest archived error log.  
  
By default, execution trace messages are not written to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent error log, because they can fill it. When the error log is full, your ability to select and analyze more difficult errors is reduced. Because the log adds to the server's processing load, it is important to consider carefully what value you obtain by capturing execution trace messages to the error log. Generally, it is best to capture all messages only when you are debugging a specific problem.  
  
When [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent is stopped, you can modify the location of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent error log. When the error log is empty, the log cannot be opened. You can cycle the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent log at any time without stopping [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent using [dbo.sp_cycle_agent_errorlog](/sql/relational-databases/system-stored-procedures/sp-cycle-agent-errorlog-transact-sql).  
  
**To view the SQL Server Agent error log**  
  
-   [View SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;](view-sql-server-agent-error-log-sql-server-management-studio.md)  
  
**To rename a SQL Server Agent error log**  
  
-   [Rename a SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;](rename-a-sql-server-agent-error-log-sql-server-management-studio.md)  
  
**To send SQL Server Agent error messages**  
  
-   [Send SQL Server Agent Error Messages](send-sql-server-agent-error-messages.md)  
  
**To write execution trace messages to the SQL Server Agent error log**  
  
-   [Write Execution Trace Messages to the SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;](write-execution-trace-messages-to-sql-server-agent-log-ssms.md)  
