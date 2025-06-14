---
title: "Set up the Job History Log"
description: "Set Up the Job History Log"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "jobs [SQL Server Agent], history"
  - "logs [SQL Server], jobs"
  - "SQL Server Agent jobs, history"
  - "historical information [SQL Server], jobs"
---
# Set Up the Job History Log
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic describes how to set up the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job history log.  
  
-   **Before you begin:**  [Security](#Security)  
  
-   **To setup the job history log, using:** [SQL Server Management Studio](#SSMS)  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Security"></a>Security  
For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).  
  
## <a name="SSMS"></a>Using SQL Server Management Studio  
**To set up the job history log**  
  
1.  In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.  
  
2.  Right-click **SQL Server Agent**, and then click **Properties**.  
  
3.  In the **SQL Server Agent Properties** dialog box, select the **History** page.  
  
4.  Choose from the following options:  
  
    1.  Check **Limit size of job history log**, and then type the maximum number of rows for the job history log, and the maximum number of rows per job.  
  
    2.  Check **Automatically remove agent history**, and specify a time period, such that history older than this period will be purged from the log.  
  
## See Also  
[Implement Jobs](implement-jobs.md)  
[Monitor Job Activity](monitor-job-activity.md)  
[Create Jobs](create-jobs.md)  
