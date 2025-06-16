---
title: Choose the Agent Service Account for Multiserver Environments
description: "Choose the Right SQL Server Agent Service Account for Multiserver Environments"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Agent, service accounts"
  - "multiserver environments [SQL Server], SQL Server Agent service account behavior"
---

# Choose the Right SQL Server Agent Service Account for Multiserver Environments

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

The Windows account you choose for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service can affect the behavior of a multiserver environment, as follows:  
  
-   If you run the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service under an account that is not a member of the local Windows Administrators group, enlisting target servers to master servers may fail. If it does, the following error message is returned:  
  
    "The enlistment operation failed."  
  
    Restart the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent services to resolve this issue.  
  
-   When the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service is run under the Local System account, master server-target server operations are supported only if both the master server and the target server reside on the same computer. If you use this configuration, the following message is returned when you enlist target servers to a master server:  
  
    "Ensure the agent start-up account for *<target_server_computer_name>* has rights to log on as targetServer."  
  
    You can ignore this informational message. The enlistment operation should complete successfully.  
  
For more information about choosing an account for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md).  
