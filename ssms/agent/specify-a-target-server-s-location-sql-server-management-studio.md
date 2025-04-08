---
title: Specify a Target Server Location
description: "Specify a Target Server's Location"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Agent jobs, target servers"
  - "target servers [SQL Server], location"
---
# Specify a Target Server's Location
[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

> [!IMPORTANT]  
> On [Azure SQL Managed Instance](/azure/sql-database/sql-database-managed-instance), most, but not all SQL Server Agent features are currently supported. See [Azure SQL Managed Instance T-SQL differences from SQL Server](/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) for details.

This topic describes how to specify the location of a target server in a multiserver administration configuration in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio or [!INCLUDE[tsql](../includes/tsql-md.md)].  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Restrictions"></a>Limitations and Restrictions  
Performing this action edits the registry. Manual editing of the registry is not recommended because inappropriate or incorrect changes can cause serious configuration problems for your system. Therefore, only experienced users should use the Registry Editor program to edit the registry. For more information, see the Microsoft Windows documentation.  
  
### <a name="Security"></a>Security  
  
#### <a name="Permissions"></a>Permissions  
Requires membership in the **sysadmin** fixed server role.  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To specify a target server's location  
  
1.  In **Object Explorer**, click the plus sign to expand the master server on which you want to specify a target server's location.  
  
2.  Right-click **SQL Server Agent**, point to **Multi Server Administration**, and select **Manage Target Servers**.  
  
3.  Right-click a target server and select **Properties**.  
  
4.  In the **Location** box, enter a location for the server, and then click **OK**.  
  
## <a name="TsqlProcedure"></a>Using Transact-SQL  
  
#### To specify a target server's location  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    USE msdb ;  
    GO  
    -- enlists the current server into the AdventureWorks1 master server.   
    -- The location for the current server is Building 21, Room 309, Rack 5  
    EXEC dbo.sp_msx_enlist N'AdventureWorks2022',   
        N'Building 21, Room 309, Rack 5' ;  
    GO  
    ```  
  
For more information, see [sp_msx_enlist (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).  
