---
title: Set CPU Idle Time and Duration
description: Set CPU idle time and duration in SQL Server Management Studio to define when SQL Server Agent responds to idle events. Follow this step-by-step guide.
author: rwestMSFT
ms.author: randolphwest
ms.date: 07/08/2026
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
# customer intent: As a database administrator, I want to define the CPU idle condition for my server, so that SQL Server Agent runs jobs at the right time.
---

# Set CPU idle time and duration

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This article explains how to define the CPU idle condition for your server in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio. The CPU idle definition influences how [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent responds to events.

For example, suppose that you define the CPU idle condition as when the average CPU usage falls below 10 percent and remains at this level for 10 minutes. Then, if you define jobs to execute whenever the server CPU reaches an idle condition, the job starts when the CPU usage falls below 10 percent and remains at that level for 10 minutes. If this job significantly impacts the performance of your server, how you define the CPU idle condition is important.

<a id="SSMSProcedure"></a>

## Use SQL Server Management Studio

1. In **Object Explorer**, connect to an instance of the [!INCLUDE [ssDEnoversion](../includes/ssdenoversion-md.md)], and then expand that instance.

1. Right-click **SQL Server Agent**, select **Properties**, and select the **Advanced** page.

1. Under **Idle CPU condition**, complete the following steps:

   - Select **Define idle CPU condition**.

   - Enter a percentage for the **Average CPU usage falls below** (across all CPUs) box. This value sets the usage level that the CPU must fall below before it's considered idle.

   - Enter a number of seconds for the **And remains below this level for** box. This value sets the duration that the minimum CPU usage must remain at before it's considered idle.

## Related content

- [SQL Server Agent Properties (Advanced Page)](sql-server-agent-properties-advanced-page.md)
