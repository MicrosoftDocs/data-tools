---
title: Defect Multiple Target Servers from a Master Server
description: "Defect Multiple Target Servers from a Master Server"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Agent jobs, target servers"
  - "target servers [SQL Server], defecting"
  - "SQL Server Agent jobs, master servers"
  - "master servers [SQL Server], defecting target servers"
  - "defecting target servers"
  - "multiple target server defections"
---

# Defect Multiple Target Servers from a Master Server

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic describes how to defect multiple target servers from a multiserver administration configuration in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio. Run this procedure from the master server.  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To defect multiple target servers from a master server  
  
1.  In **Object Explorer**, expand a server that is configured as a master server.  
  
2.  Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.  
  
3.  Click **Post Instructions**, and then in the **Instruction type** list, select **Defect**.  
  
4.  Under **Recipients**, do one of the following:  
  
    -   Click **All target servers** to defect all target servers of this master server. Use this option if you want to completely uninstall the current multiserver administration configuration.  
  
    -   Click **These target servers**, and then click the corresponding **Select** box, to defect some, but not all, target servers of this master server.  
  
## See Also  
[Create a Multiserver Environment](create-a-multiserver-environment.md)  
[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md)  
[Defect a Target Server from a Master Server](defect-a-target-server-from-a-master-server.md)  
