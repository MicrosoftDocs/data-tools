---
title: "Create a PowerShell Script Job Step"
description: "Create a PowerShell Script Job Step"
author: rwestMSFT
ms.author: randolphwest
ms.date: "01/20/2017"
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "PowerShell [SQL Server], job steps"
  - "jobs [SQL Server Agent], PowerShell"
  - "job steps [PowerShell]"
  - "SQL Server Agent jobs, PowerShell steps"
---
# Create a PowerShell Script Job Step
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic describes how to create and define a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job step that executes a PowerShell script in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio or [!INCLUDE[tsql](../includes/tsql-md.md)].  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Security"></a>Security  
For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).  

[!INCLUDE[Freshness](../includes/paragraph-content/fresh-note-steps-feedback.md)]

## <a name="SSMS"></a>Using SQL Server Management Studio  
  
#### To create a PowerShell Script job step  
  
1.  In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.  
  
2.  Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**. For more information on creating a job, see [Creating Jobs](create-jobs.md).  
  
3.  In the **Job Properties** dialog, click the **Steps** page, and then click **New**.  
  
4.  In the **New Job Step** dialog, type a job **Step name**.  
  
5.  In the **Type** list, click **PowerShell**.  
  
6.  In the **Run as** list, select the proxy account with the credentials that the job will use.  
  
7.  In the **Command** box, enter the PowerShell script syntax that will be executed for the job step. Alternately, click **Open** and select a file containing the script syntax. For an example of a PowerShell script, see **Using Transact-SQL** below.  
  
8.  Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.  
  
## <a name="TSQL"></a>Using Transact-SQL  
  
#### To create a PowerShell Script job step  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    -- creates a PowerShell job step that finds the processes
    -- that use more than 1000 MB of memory and kills them  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Kills all processes that use more than 1000 MB of memory',  
        @subsystem = N'PowerShell',  
        @command = N'Get-Process | Where-Object { $_.WS -gt 1000MB } | Stop-Process',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
For more information, see [sp_add_jobstep (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).  
  
## <a name="SMO"></a>Using SQL Server Management Objects  
**To create a PowerShell Script job step**  
  
Use the **JobStep** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.  
