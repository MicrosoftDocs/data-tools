---
title: "SQL Server Agent"
description: "SQL Server Agent"
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mathoma
ms.date: 09/02/2025
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Agent, about SQL Server Agent"
  - "automatic administration steps"
---

# SQL Server Agent

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

This article provides an overview of the SQL Server Agent, which is a Microsoft Windows service that executes scheduled administrative tasks (called *jobs*) in SQL Server and Azure SQL Managed Instance.

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

## <a name="Benefits"></a>Benefits of SQL Server Agent

SQL Server Agent uses SQL Server to store job information. Jobs contain one or more job steps. Each step contains its own task, for example, backing up a database.

SQL Server Agent can run a job on a schedule, in response to a specific event, or on demand. For example, if you want to back up all the company servers every weekday after hours, you can automate this task. Schedule the backup to run after 22:00 Monday through Friday. If the backup encounters a problem, SQL Server Agent can record the event and notify you.

> [!NOTE]  
> By default, the SQL Server Agent service is disabled when SQL Server is installed unless the user explicitly chooses to autostart the service.

## <a name="Components"></a>SQL Server Agent Components

SQL Server Agent uses the following components to define the tasks to be performed, when to perform the tasks, and how to report the success or failure of the tasks.

Use the [SQL Server Configuration Manager](/sql/relational-databases/sql-server-configuration-manager) to manage the SQL Server Agent service, and use [SQL Server Management Studio (SSMS)](../sql-server-management-studio-ssms.md) to easily manage SQL Server Agent properties, jobs, alerts, operators, and proxies in a graphical user interface.

### Jobs

A *job* is a specified series of actions that SQL Server Agent performs. Use jobs to define an administrative task that can be run one or more times and monitored for success or failure. A job can run on one local server or on multiple remote servers.

> [!IMPORTANT]  
> SQL Server Agent jobs that are running at the time of a failover event on a SQL Server failover cluster instance do not resume after failover to another failover cluster node. SQL Server Agent jobs that are running at the time a Hyper-V node is paused do not resume if the pause causes a failover to another node. Jobs that begin but fail to complete because of a failover event are logged as started, but do not show additional log entries for completion or failure. SQL Server Agent jobs in these scenarios appear to have never ended.

You can run jobs in several ways:

- According to one or more schedules.

- In response to one or more alerts.

- By executing the `sp_start_job` stored procedure.

Each action in a job is a *job step*. For example, a job step might consist of running a Transact-SQL statement, executing an SSIS package, or issuing a command to an Analysis Services server. Job steps are managed as part of a job.

Each job step runs in a specific security context. For job steps that use Transact-SQL, use the EXECUTE AS statement to set the security context for the job step. For other types of job steps, use a proxy account to set the security context for the job step.

Use the [sp_help_job](/sql/relational-databases/system-stored-procedures/sp-help-job-transact-sql) system stored procedure to find out information about a specific job. Use the [dbo.sysjobs](/sql/relational-databases/system-tables/dbo-sysjobs-transact-sql) system table to view information about jobs. For example, use the following Transact-SQL (T-SQL) statement to view information about all jobs on a server:

```sql
USE MSDB
GO
SELECT job_id, [name] FROM dbo.sysjobs;
```

### Schedules

A *schedule* specifies when a job runs. More than one job can run on the same schedule, and more than one schedule can apply to the same job. A schedule can define the following conditions for the time when a job runs:

- Whenever SQL Server Agent starts.

- Whenever CPU utilization of the computer is at a level you've defined as idle.

- One time, at a specific date and time.

- On a recurring schedule.

For more information, see [Create and attach schedules to jobs](create-and-attach-schedules-to-jobs.md).

### Alerts

An *alert* is an automatic response to a specific event. For example, an event can be a job that starts or system resources that reach a specific threshold. You define the conditions under which an alert occurs.

An alert can respond to one of the following conditions:

- SQL Server events

- SQL Server performance conditions

- Microsoft Windows Management Instrumentation (WMI) events on the computer where SQL Server Agent is running

An alert can perform the following actions:

- Notify one or more operators

- Run a job

For more information, see [Alerts](alerts.md).

### Operators

An *operator* defines contact information for an individual responsible for the maintenance of one or more instances of SQL Server. In some enterprises, operator responsibilities are assigned to one individual. In enterprises with multiple servers, many individuals can share operator responsibilities. An operator doesn't contain security information, and doesn't define a security principal.

SQL Server can notify operators of alerts through...

- E-mail

- Pager (through e-mail)

- **net send**

> [!NOTE]  
> To send notifications by using **net send**, the Windows Messenger service must be started on the computer where SQL Server Agent resides.

> [!IMPORTANT]  
> The Pager and **net send** options is removed from SQL Server Agent in a future version of SQL Server. Avoid using these features in new development work, and plan to modify applications that currently use these features.

To send notifications to operators by using e-mail or pagers, you must configure SQL Server Agent to use Database Mail. For more information, see [Database Mail](/sql/relational-databases/database-mail/database-mail).

You can define an operator as the alias for a group of individuals. In this way, all members of that alias aren't verified at the same time. For more information, see [Operators](operators.md).

## <a name="Security"></a>Security for SQL Server Agent administration

SQL Server Agent uses the **SQLAgentUserRole**, **SQLAgentReaderRole**, and **SQLAgentOperatorRole** fixed database roles in the `msdb` database to control access to SQL Server Agent for users who aren't members of the **sysadmin** fixed server role. In addition to these fixed database roles, subsystems and proxies help database administrators ensure that each job step runs with the minimum permissions required to perform its task.

### Roles

Members of the **SQLAgentUserRole**, **SQLAgentReaderRole**, and **SQLAgentOperatorRole** fixed database roles in `msdb`, and members of the **sysadmin** fixed server role have access to SQL Server Agent. A user that doesn't belong to any of these roles can't use SQL Server Agent. For more information on the roles used by SQL Server Agent, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).

### Subsystems

A subsystem is a predefined object that represents functionality that is available to a job step. Each proxy has access to one or more subsystems. Subsystems provide security because they delimit access to the functionality that is available to a proxy. Each job step runs in the context of a proxy, except for Transact-SQL job steps. Transact-SQL job steps use the EXECUTE AS command to set the security context to the owner of the Job.

SQL Server defines the subsystems listed in the following table:

| Subsystem name | Description |
| --- | --- |
| Microsoft ActiveX Script | Run an ActiveX scripting job step.<br /><br />**Warning** The ActiveX Scripting subsystem is removed from SQL Server Agent in a future version of Microsoft SQL Server. Avoid using this feature in new development work, and plan to modify applications that currently use this feature. |
| Operating System (**CmdExec**) | Run an executable program. |
| PowerShell | Run a PowerShell scripting job step. |
| Replication Distributor | Run a job step that activates the replication Distribution Agent. |
| Replication Merge | Run a job step that activates the replication Merge Agent. |
| Replication Queue Reader | Run a job step that activates the replication Queue Reader Agent. |
| Replication Snapshot | Run a job step that activates the replication Snapshot Agent. |
| Replication Transaction Log Reader | Run a job step that activates the replication Log Reader Agent. |
| Analysis Services Command | Run an Analysis Services command. |
| Analysis Services Query | Run an Analysis Services query. |
| SSIS package execution | Run an SSIS package. |

> [!NOTE]  
> Because Transact-SQL job steps do not use proxies, there is no SQL Server Agent subsystem for Transact-SQL job steps.

SQL Server Agent enforces subsystem restrictions even when the security principal for the proxy would normally have permission to run the task in the job step. For example, a proxy for a user that is a member of the sysadmin fixed server role can't run an SSIS job step unless the proxy has access to the SSIS subsystem, even though the user can run SSIS packages.

### Proxies

SQL Server Agent uses proxies to manage security contexts. A proxy can be used in more than one job step. Members of the **sysadmin** fixed server role can create proxies.

Each proxy corresponds to a security credential. Each proxy can be associated with a set of subsystems and a set of logins. The proxy can be used only for job steps that use a subsystem associated with the proxy. To create a job step that uses a specific proxy, the job owner must either use a login associated with that proxy or a member of a role with unrestricted access to proxies. Members of the **sysadmin** fixed server role have unrestricted access to proxies. Members of **SQLAgentUserRole**, **SQLAgentReaderRole**, or **SQLAgentOperatorRole** can only use proxies to which they have been granted specific access. Each user that is a member of any of these SQL Server Agent fixed database roles must be granted access to specific proxies so that the user can create job steps that use those proxies.

## Automate administration

Use the following steps to configure SQL Server Agent to automate SQL Server administration:

1. Establish which administrative tasks or server events occur regularly and whether these tasks or events can be administered programmatically. A task is a good candidate for automation if it involves a predictable sequence of steps and occurs at a specific time or in response to a specific event.

1. Define a set of jobs, schedules, alerts, and operators by using SQL Server Management Studio, Transact-SQL scripts, or SQL Server Management Objects (SMO). For more information, see [Create Jobs](create-jobs.md).

1. Run the SQL Server Agent jobs you've defined.

> [!NOTE]  
> For the default instance of SQL Server, the SQL Server service is named SQLSERVERAGENT. For named instances, the SQL Server Agent service is named SQLAgent$*instancename*.

If you're running multiple instances of SQL Server, you can use multiserver administration to automate tasks common across all instances. For more information, see [Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md).

Use the following tasks to get started with SQL Server Agent:

| Description | Article |
| --- | --- |
| Describes how to configure SQL Server Agent. | [Configure SQL Server Agent](configure-sql-server-agent.md) |
| Describes how to start, stop, and pause the SQL Server Agent service. | [Start, Stop, or Pause the SQL Server Agent Service](start-stop-or-pause-the-sql-server-agent-service.md) |
| Describes considerations for specifying an account for the SQL Server Agent service. | [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) |
| Describes how to use the SQL Server Agent error log. | [SQL Server Agent Error Log](sql-server-agent-error-log.md) |
| Describes how to use performance objects. | [Use Performance Objects](use-performance-objects.md) |
| Describes the Maintenance Plan Wizard, which is a utility that you use create jobs, alerts, and operators to automate administration of an instance of SQL Server. | [Use the Maintenance Plan Wizard](/sql/relational-databases/maintenance-plans/use-the-maintenance-plan-wizard) |
| Describes how to automate administrative tasks using SQL Server Agent. | [Automated Administration Tasks (SQL Server Agent)](automated-administration-tasks-sql-server-agent.md) |

## NOSQLPS

[!INCLUDE [sql-server-powershell-no-sqlps](../includes/sql-server-powershell-no-sqlps.md)]

## TDS 8.0 and strict encryption support

[!INCLUDE [sssql25-md](../includes/sssql25-md.md)] introduces TDS 8.0 and TLS 1.3 support for the SQL Server Agent, which can use strict encryption. SQL Server Agent discovers the level of encryption configured in the **SQL Server Configuration Manager** (`Force Strict Encryption`, `Force Encryption` or none) and uses the corresponding option to connect to SQL Server (`strict`, `mandatory`, or `optional`). SQL Agent T-SQL jobs connecting to the local instance use the SQL Server Agent encryption settings. This means that if SQL Server Agent connects with `strict` encryption, then a local T-SQL job also connects with the same level of encryption.

## Related content

- [Surface area configuration](/sql/relational-databases/security/surface-area-configuration)
- [SQL Server Agent with PowerShell](/powershell/sql-server/sql-server-powershell#sql-server-agent)
