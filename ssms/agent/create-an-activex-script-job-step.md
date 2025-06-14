---
title: "Create an ActiveX Script Job Step"
description: "Create an ActiveX Script Job Step"
author: rwestMSFT
ms.author: randolphwest
ms.date: 10/06/2020
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "ActiveX scripting jobs [SQL Server]"
  - "job steps [Analysis Services]"
---
# Create an ActiveX script job step

[!INCLUDE [sqlserver](../includes/applies-to-version/sqlserver.md)]

ActiveX subsystem is discontinued beginning with SQL Server 2016. Convert any existing job steps that use ActiveX Script to a [PowerShell script job step](create-a-powershell-script-job-step.md). Use PowerShell for any future development.

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic describes how to create and define a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job step in SQL Server 2014 and prior that executes an ActiveX script by using SQL Server Management Studio, [!INCLUDE[tsql](../includes/tsql-md.md)], or SQL Server Management Objects.  

## Before you begin  
  
### <a name="Restrictions"></a>Limitations and Restrictions  

[!INCLUDE[ssNoteDepFutureAvoid](../includes/ssnotedepfutureavoid-md.md)]  

  
### <a name="Security"></a>Security  

For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).  
  
## <a name="SSMS"></a>Use SQL Server Management Studio  
  
#### To create an ActiveX Script job step  
  
1.  In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.  
  
2.  Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**. For more information on creating a job, see [Creating Jobs](create-jobs.md).  
  
3.  In the **Job Properties** dialog, click the **Steps** page, and then click **New**.  
  
4.  In the **New Job Step** dialog, type a job **Step name**.  
  
5.  In the **Type** list, click **ActiveX Script**.  
  
6.  In the **Run as** list, select the proxy account with the credentials that the job will use.  
  
7.  Select the **Language** in which the script was written. Alternatively, click **Other** and then enter the name of the [!INCLUDE[msCoName](../includes/msconame-md.md)] ActiveX scripting language in which the script will be written.  
  
8.  In the **Command** box, enter the script syntax that will be executed for the job step. Alternately, click **Open** and select a file containing the script syntax.  
  
9. Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.  
  
## <a name="TSQL"></a>Using Transact-SQL  
  
#### To create an ActiveX script job step  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    -- create an ActiveX Script job step written in VBScript that creates a restore point  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Create a restore point',  
        @subsystem = N'ACTIVESCRIPTING',  
        @command = N'Const RESTORE_POINT = 20  
  
    strComputer = "."  
    Set objWMIService = GetObject("winmgmts:" _  
        & "{impersonationLevel=impersonate}!\\" & strComputer & "\root\default")  
  
    Set objItem = objWMIService.Get("SystemRestore")  
    errResults = objItem.Restore(RESTORE_POINT)',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
For more information, see [sp_add_jobstep (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).  
  
## <a name="SMO"></a>Using SQL Server Management Objects  
**To create an ActiveX Script job step**  
  
Use the **JobStep** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.  
