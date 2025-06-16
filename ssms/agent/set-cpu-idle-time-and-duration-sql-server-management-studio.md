---
title: Set CPU Idle Time and Duration
description: "Set CPU Idle Time and Duration"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "CPU [SQL Server], idle conditions"
  - "time [SQL Server], CPU idle and duration"
  - "duration of CPU idle [SQL Server]"
  - "SQL Server Agent, CPU idle conditions"
  - "idle time [SQL Server]"
---

# Set CPU Idle Time and Duration

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic explains how to define the CPU idle condition for your server in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio. The CPU idle definition influences how [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent responds to events. For example, suppose that you define the CPU idle condition as when the average CPU usage falls below 10 percent and remains at this level for 10 minutes. Then if you have defined jobs to execute whenever the server CPU reaches an idle condition, the job will start when the CPU usage falls below 10 percent and remains at that level for 10 minutes. If this is a job that significantly impacts the performance of your server, how you define the CPU idle condition is important.  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To set CPU idle time and duration  
  
1.  In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.  
  
2.  Right-click **SQL Server Agent**, click **Properties**, and select the **Advanced** page.  
  
3.  Under **Idle CPU condition**, do the following:  
  
    -   Check **Define idle CPU condition.**  
  
    -   Specify a percentage for the **Average CPU usage falls below** (across all CPUs) box. This sets the usage level that the CPU must fall below before it is considered idle.  
  
    -   Specify a number of seconds for the **And remains below this level for** box. This sets the duration that the minimum CPU usage must remain at before it is considered idle.  
