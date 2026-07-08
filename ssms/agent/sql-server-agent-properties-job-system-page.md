---
title: SQL Server Agent Properties (Job System Page)
description: SQL Server Agent job system properties let you configure shutdown timeouts and proxy accounts. Learn how to view and modify job management settings in SSMS.
author: rwestMSFT
ms.author: randolphwest
ms.date: 07/08/2026
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.ag.agent.job.f1"
# customer intent: As a database administrator, I want to view and modify the SQL Server Agent job system settings, so that I can manage how jobs run in my environment.
---

# SQL Server Agent Properties (Job System page)

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

Use this page to view and change how the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent service manages jobs.

## Options

#### Shutdown timeout interval (in seconds)

Specifies the number of seconds that [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent waits for jobs to complete before shutting down. If the job is still running after the interval you specify, [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent forcefully stops the job.

#### Use a non-administrator proxy account

**Applies to**: [!INCLUDE [ssversion2005-md](../includes/ssversion2005-md.md)] and earlier versions only.

Sets a non-administrator proxy account for [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent.

No longer supported.

#### User name

**Applies to**: [!INCLUDE [ssversion2005-md](../includes/ssversion2005-md.md)] and earlier versions only.

Type the name of the user for the non-administrator proxy account.

No longer supported.

#### Password

**Applies to**: [!INCLUDE [ssversion2005-md](../includes/ssversion2005-md.md)] and earlier versions only.

Type the password of the user for the non-administrator proxy account.

No longer supported.

#### Domain

**Applies to**: [!INCLUDE [ssversion2005-md](../includes/ssversion2005-md.md)] and earlier versions only.

Type the domain of the user for the non-administrator proxy account.

No longer supported.

## Related content

- [SQL Server Agent Properties (General Page)](sql-server-agent-properties-general-page.md)
- [Implement Jobs](implement-jobs.md)
