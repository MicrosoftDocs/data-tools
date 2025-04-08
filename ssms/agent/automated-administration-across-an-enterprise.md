---
title: "Automated Administration Across an Enterprise"
description: "Automated Administration Across an Enterprise"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "enterprise automatic administration [SQL Server]"
  - "multiserver administration [SQL Server]"
  - "SQL Server Agent jobs, multiserver administration"
  - "jobs [SQL Server Agent], multiserver administration"
  - "master servers [SQL Server], about master servers"
  - "target servers [SQL Server], about target servers"
  - "master servers [SQL Server]"
  - "multiple instances of SQL Server"
  - "target servers [SQL Server]"
---
# Automated Administration Across an Enterprise
[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

> [!IMPORTANT]  
> On [Azure SQL Managed Instance](/azure/sql-database/sql-database-managed-instance), most, but not all SQL Server Agent features are currently supported. See [Azure SQL Managed Instance T-SQL differences from SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) for details.

Automating administration across multiple instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is called *multiserver administration*. Use multiserver administration to do the following:  
  
-   Manage two or more servers.  
  
-   Schedule information flows between enterprise servers for data warehousing.  
  
To take advantage of multiserver administration, you must have at least one master server and at least one target server. A master server distributes jobs to, and receives events from, target servers. A master server also stores the central copy of job definitions for jobs that are run on target servers. Target servers connect periodically to the master server to update their schedule of jobs. If a new job exists on the master server, the target server downloads the job. After the target server completes the job, it reconnects to the master server and reports the status of the job. Note that your job definition must be same when performing any database related activities.  
  
The following illustration shows the relationship between master and target servers:  
  
![Multiserver administration configuration](media/multisvr.gif "Multiserver administration configuration")  
  
If you administer departmental servers across a large corporation, you can define the following:  
  
-   One backup job with job steps.  
  
-   Operators to notify in case of backup failure.  
  
-   An execution schedule for the backup job.  
  
Write this backup job one time on the master server and then enlist each departmental server as a target server. From the time of their enlistment, all the departmental servers run the same backup job, yet you defined the job only once.  
  
> [!NOTE]  
> Multiserver administration features are intended for members of the sysadmin role. However, a member of the sysadmin role on the target server cannot edit the operations that are performed on the target server by the master server. This security measure prevents job steps from being accidentally deleted and operations on the target server from being interrupted.  
  
## In This Section  
[Create a Multiserver Environment](create-a-multiserver-environment.md)  
Contains information about how to create and manage master and target servers.  
  
[Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md)  
Contains information about how using nonadministrative Windows accounts or the Local System account for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service can affect multiserver environments.  
  
[Set Encryption Options on Target Servers](set-encryption-options-on-target-servers.md)  
Contains information about setting the MsxEncryptChannelOptions [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent registry subkey on target servers.  
  
[Manage Jobs Across an Enterprise](manage-jobs-across-an-enterprise.md)  
Contains information about checking job status, changing target servers for jobs, synchronizing target server clocks, and polling master servers for their current job status.  
  
[Troubleshoot Multiserver Jobs That Use Proxies](troubleshoot-multiserver-jobs-that-use-proxies.md)  
Contains information about troubleshooting multiserver jobs that use proxies which fail.  
  
[Poll Servers](poll-servers.md)  
Contains information about how to implicitly and explicitly make target servers poll master servers to synchronize jobs information.  
  
[Manage Events](manage-events.md)  
Contains information about event forwarding from target servers to master servers.  
  
[Tune Automated Administration Across an Enterprise](tune-automated-administration-across-an-enterprise.md)  
Contains information about how automated administration in a multiserver environment takes advantage of the self-tuning features of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].  
  
## See Also  
[Backward Compatibility Topics for Installing the SQL Server Database Engine](/sql/database-engine/discontinued-database-engine-functionality-in-sql-server)  
[Registering Servers](../register-servers/register-servers.md)  
[sp_add_targetservergroup](/sql/relational-databases/system-stored-procedures/sp-add-targetservergroup-transact-sql)  
[sp_delete_targetserver](/sql/relational-databases/system-stored-procedures/sp-delete-targetserver-transact-sql)  
[sp_delete_targetservergroup](/sql/relational-databases/system-stored-procedures/sp-delete-targetservergroup-transact-sql)  
[sp_help_downloadlist](/sql/relational-databases/system-stored-procedures/sp-help-downloadlist-transact-sql)  
[sp_help_jobserver](/sql/relational-databases/system-stored-procedures/sp-help-jobserver-transact-sql)  
[sp_help_targetservergroup](/sql/relational-databases/system-stored-procedures/sp-help-targetservergroup-transact-sql)  
[sp_resync_targetserver](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql)  
[sp_update_targetservergroup](/sql/relational-databases/system-stored-procedures/sp-update-targetservergroup-transact-sql)  
[sysjobservers](/sql/relational-databases/system-tables/dbo-sysjobservers-transact-sql)  
[syslogins](/sql/relational-databases/system-compatibility-views/sys-syslogins-transact-sql)  
[systargetservers](/sql/relational-databases/system-tables/dbo-systargetservers-transact-sql)  
