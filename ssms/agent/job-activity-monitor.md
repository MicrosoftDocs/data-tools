---
title: Job Activity Monitor
description: View the current activity of SQL Server Agent jobs.
author: rwestMSFT
ms.author: randolphwest
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.ag.jobactivitymonitor.alljobs.f1"
  - "SQL13.SWB.ACTIVITYMON.F1"
---
# Job Activity Monitor

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

Use this page to view the current activity of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs. Select **Filter** to limit the jobs displayed. The **Agent Job Activity** grid is read-only.

Select the column headers to sort the grid. To modify a job, double-click the job to open the **Job Properties** dialog box.

Right-clicking a job in the grid can perform one of the following actions:

- Start running all job steps
- Start at a particular job step
- Disable or enable the job
- Refresh the job
- Delete the job
- View the history of the job
- View the properties of the job.

Select **Refresh** to update the grid with current information.

## Options

#### Name

Name of the job.

#### Enabled

Specifies whether the job is enabled (**Yes**) or not enabled (**No**).

#### Status*

Current status of the job.

#### Last Run Outcome

Job status when last run.

#### Last Run

Date and time job was last run using the local date and time of the server.

#### Next Run

Date and time the job is next scheduled to run using the local date and time of the server.

> [!NOTE]  
> Only members of the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] **sysadmin** fixed server role and the server administrators group can see values in this column. Members of the **SQLAgentOperatorRole** role can't see values in this column.

#### Category

The job category assigned to the job.

#### Runnable

**Yes** if the job can be run; **No** if the job can't be run. A job isn't runnable if it has no steps or if it has no target server.

#### Scheduled

**Yes** if the job is assigned to a job schedule; **No** if the job has no schedule.

## Open the job activity monitor

In **Object Explorer**, expand your server, expand **SQL Server Agent**, right-click **Job Activity Monitor**, and then select **View Job Activity**.

## Related content

- [Monitor Job Activity](monitor-job-activity.md)
