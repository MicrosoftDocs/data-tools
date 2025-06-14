---
title: "Defect a Target Server from a Master Server"
description: "Defect a Target Server from a Master Server"
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
---
# Defect a Target Server from a Master Server
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic describes how to defect a target server from a master server in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio, [!INCLUDE[tsql](../includes/tsql-md.md)], or SQL Server Management Objects (SMO). Run this procedure from the target server.  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Security"></a>Security  
  
#### <a name="Permissions"></a>Permissions  
To execute this stored procedure, a user must be a member of the **sysadmin** fixed server role.  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To defect a target server from a master server  
  
1.  In **Object Explorer**, expand a server that is configured as a target server.  
  
2.  Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Defect**.  
  
3.  Click **Yes** to confirm that you want to defect this target server from a master server.  
  
## <a name="TsqlProcedure"></a>Using Transact-SQL  
  
#### To defect a target server from a master server  
  
1.  Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].  
  
2.  From the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
```  
sp_msx_defect ;  
```  
  
For more information, see [sp_msx_defect (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-msx-defect-transact-sql).  
  
## <a name="PowerShellProcedure"></a>Using SQL Server Management Objects (SMO)  
Use the **MsxDefect Method**.  
  
## See Also  
[Create a Multiserver Environment](create-a-multiserver-environment.md)  
[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md)  
[Defect Multiple Target Servers from a Master Server](defect-multiple-target-servers-from-a-master-server.md)  
