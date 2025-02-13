---
title: "Manage Jobs Across an Enterprise"
description: "Manage Jobs Across an Enterprise"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
helpviewer_keywords:
  - "multiserver job management [SQL Server]"
  - "jobs [SQL Server Agent], modifying"
  - "modifying jobs"
  - "SQL Server Agent jobs, modifying"
  - "target servers [SQL Server], job changes"
---
# Manage Jobs Across an Enterprise
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> On [Azure SQL Managed Instance](/azure/sql-database/sql-database-managed-instance), most, but not all SQL Server Agent features are currently supported. See [Azure SQL Managed Instance T-SQL differences from SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) for details.

If you make changes to multiserver job definitions outside [!INCLUDE[msCoName](../includes/msconame-md.md)] SQL Server Management Studio, you must post the changes to the download list so that target servers can download the updated job again. To ensure that target servers have current job definitions, post an INSERT instruction after you update the multiserver job, as follows:  
  
```  
EXECUTE sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
To notify target servers that a multiserver job has been modified, you must invoke the preceding command after using any of the following procedures:  
  
-   [sp_add_jobstep (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [sp_update_jobstep (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql)  
  
-   [sp_delete_jobstep (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql)  
  
-   [Managing Events](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [sp_detach_schedule (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-detach-schedule-transact-sql)  
  
    > [!NOTE]  
    > It is not necessary to call **sp_post_msx_operation** after you call **sp_update_job** or **sp_delete_job**, because these stored procedures post the required changes to the download list automatically.  
  
The following are common tasks for managing jobs across an enterprise:  
  
**To check the status of a target server**  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-help-targetserver-transact-sql)  
  
-   [SQL Server Management Objects (SMO)](/sql/relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide)  
  
**To change the target servers for a job**  
  
-   [SQL Server Management Studio](modify-the-target-servers-for-a-job.md)  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  
-   [SQL Server Management Objects (SMO)](/sql/relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide)  
  
**To change the location of a target server**  
  
-   [SQL Server Management Studio](specify-a-target-server-s-location-sql-server-management-studio.md)  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)  
  
-   [SQL Server Management Objects (SMO)](/sql/relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide)  
  
**To synchronize target server clocks**  
  
-   [SQL Server Management Studio](synchronize-target-server-clocks-sql-server-management-studio.md)  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql)  
  
**To force a target server to poll the master server**  
  
-   [SQL Server Management Studio](force-a-target-server-to-poll-the-master-server.md)  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql)  
  
## See Also  
[Manage Events](manage-events.md)  
