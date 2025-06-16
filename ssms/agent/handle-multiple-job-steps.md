---
title: "Handle Multiple Job Steps"
description: "Handle Multiple Job Steps"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "job steps [SQL Server Agent]"
  - "ordering job steps [SQL Server]"
  - "multiple job steps"
  - "SQL Server Agent jobs, job steps"
  - "control of flow for jobs [SQL Server]"
---
# Handle Multiple Job Steps
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

If your job has more than one job step, you must specify the order in which the job steps run. This is called *control of flow.* You can add new job steps and rearrange the flow of job steps at any time; the changes take effect the next time the job is run. This illustration shows the control of flow for a database backup job.  
  
![SQL Server Agent job steps control of flow](media/dbflow01.gif "SQL Server Agent job steps control of flow")  
  
The first step is Backup Database. If this step fails, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent reports failure to the operator who is defined to receive notification. If the Backup Database step succeeds, the job proceeds to the next step, "Scrub" Customer Data. If this step fails, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent skips forward to Restore Database. If "Scrub" Customer Data succeeds, the job proceeds to the next step, Update Statistics, and so on, until the final step either results in Report Success or Report Failure.  
  
You define a control-of-flow action for the success and failure of each job step. You must specify an action to be taken when a job step succeeds and an action to be taken when a job step fails. You can also define the number of retry attempts for failed job steps and the interval between the retry attempts.  
  
> [!NOTE]  
> When you use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent graphical user interface (GUI) and delete one or more steps from a multistep job, the GUI removes all job steps and then adds the remaining steps back with the correct on-success or on-failure references. For example, suppose you have a job with five steps, and the first step is configured to jump to step 4 if it completes successfully. If you delete step 3, the GUI removes all steps for this job and adds the remaining four steps (1, 2, 4, and 5) with corrected references. In this case, the reference in step 1 would be reconfigured to jump to step 3 if step 1 completes successfully.  
  
Job steps must be self-contained. That is, a job cannot pass Boolean values, data, or numeric values between job steps. You can, however, pass values from one [!INCLUDE[tsql](../includes/tsql-md.md)] job step to another by using permanent tables or global temporary tables. You can pass values from job steps that run executable programs from one job step to another job step by using files. For example, the executable run by one job step writes a file, and the executable run by a subsequent job step reads the file.  
  
> [!NOTE]  
> If you create looping job steps (job step 1 is followed by job step 2, then job step 2 returns to job step 1), a warning message appears when the job is created using SQL Server Management Studio.  
  
[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent records job and job step information in the job history.  
  
## See Also  
[sp_add_job](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)  
[sysjobhistory](/sql/relational-databases/system-tables/dbo-sysjobhistory-transact-sql)  
[sysjobs (Transact-SQL)](/sql/relational-databases/system-tables/dbo-sysjobs-transact-sql)  
[sysjobsteps](/sql/relational-databases/system-tables/dbo-sysjobsteps-transact-sql)  
[Implement Jobs](implement-jobs.md)  
[Manage Job Steps](manage-job-steps.md)  
