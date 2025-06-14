---
title: "Force a Target Server to Poll the Master Server"
description: "Force a Target Server to Poll the Master Server"
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/05/2023
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "forcing master server polling"
  - "polling master servers [SQL Server]"
  - "master servers [SQL Server], polling"
  - "target servers [SQL Server], polling the master server"
---

# Force a Target Server to Poll the Master Server

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This article describes how to force a target server to poll the master server. The target server must be a registered server on the master server.

A job is a specified series of actions that [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent performs. A multiserver job is a job that a master server runs on one or more target servers. Each target server can run one instance of the same job at the same time. Each target server periodically polls the master server, downloads a copy of any new jobs assigned to the target server, and then disconnects. The target server runs the job locally and then reconnects to the master server to upload the job outcome status.

> [!NOTE]  
> If the master server is inaccessible when the target server tries to upload job status, the job status is spooled until the master server can be accessed.

- **Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)

- **To force a target server to poll the master server, using:** [SQL Server Management Studio](#SSMS)

## <a id="BeforeYouBegin"></a> Before You Begin

### <a id="Restrictions"></a> Limitations and Restrictions

The target server must be a registered server on the master server. You must run the instructions given in this topic from the master server.

### <a id="Security"></a> Security

For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) and [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).

## <a id="SSMS"></a> Use SQL Server Management Studio

**To force a target server to poll the master server**

1. In **Object Explorer**, expand the master server.

1. Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then select **Manage Target Servers**.

1. Select a target server, and then select **Force Poll**.
