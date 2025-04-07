---
title: Tune Automated Administration Across an Enterprise
description: "Tune Automated Administration Across an Enterprise"
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/05/2023
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "performance [SQL Server], automated administration"
  - "tuning automated administration [SQL Server]"
  - "monitoring performance [SQL Server], automated administration"
---

# Tune Automated Administration Across an Enterprise

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> On [Azure SQL Managed Instance](/azure/sql-database/sql-database-managed-instance), most, but not all SQL Server Agent features are currently supported. See [Azure SQL Managed Instance T-SQL differences from SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) for details.

Multiserver administration with Microsoft [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent takes advantage of the self-tuning features of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)]. Therefore, under normal conditions, additional job tuning is not necessary. However, network loads increase when you run jobs, generate alerts, and notify operators. You can tune automated administration across an enterprise to minimize the network traffic these activities cause.

## Related content

- [Monitoring Performance of the Data Flow Engine](/sql/integration-services/performance/performance-counters)
