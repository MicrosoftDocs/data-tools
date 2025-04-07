---
title: "Modify a SQL Server Agent Proxy"
description: "Modify a SQL Server Agent Proxy"
author: rwestMSFT
ms.author: randolphwest
ms.date: 06/03/2020
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "proxies [SQL Server Agent], modifying"
  - "modifying SQL Server Agent proxy"
---

# Modify a SQL Server Agent Proxy

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> On [Azure SQL Managed Instance](/azure/sql-database/sql-database-managed-instance), most, but not all SQL Server Agent features are currently supported. See [Azure SQL Managed Instance T-SQL differences from SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) for details.

This topic describes how to modify a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent proxy in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio or [!INCLUDE[tsql](../includes/tsql-md.md)].  

## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Restrictions"></a>Limitations and Restrictions  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts. The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is running.  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs. If the proxy no longer has access to the subsystem, the job step fails. Otherwise, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.  
  
-   If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.  
  
### <a name="Security"></a>Security  
  
#### <a name="Permissions"></a>Permissions  
Only members of the **sysadmin** fixed server role can create, modify, or delete proxy accounts.  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To modify a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent proxy  
  
1.  In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent proxy account that you want to modify.  
  
2.  Click the plus sign to expand **SQL Server Agent**.  
  
3.  Click the plus sign to expand the **Proxies** folder.  
  
4.  Click the plus sign to expand the subsystem node for the proxy (for example, **ActiveX Script**).  
  
5.  Right-click the proxy account you want to modify and select **Properties**.  
  
6.  In the _proxy\_name_**Proxy Account Properties** dialog box, make changes to the proxy account as necessary. For more information on the options in this dialog box, see [Create a SQL Server Agent Proxy](create-a-sql-server-agent-proxy.md).  
  
7.  When finished, click **OK**.  
  
## <a name="TsqlProcedure"></a>Using Transact-SQL  
  
#### To modify a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent proxy  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```sql
    -- Disables the proxy named 'Catalog application proxy'.  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_proxy  
        @proxy_name = 'Catalog application proxy',  
        @enabled = 0;  
    GO  
    ```  
  
For more information, see [sp_update_proxy (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-update-proxy-transact-sql).  
