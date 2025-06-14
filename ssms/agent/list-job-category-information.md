---
title: "List Job Category Information"
description: "List Job Category Information"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---
# List Job Category Information
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This topic describes how to list job category information in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using [!INCLUDE[tsql](../includes/tsql-md.md)] or SQL Server Management Objects.  
  
-   **Before you begin:**  
  
    [Security](#Security)  
  
-   **To list job category information, using:**  
  
    [Transact-SQL](#TSQL)  
  
    [SQL Server Management Objects](#SMO)  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Security"></a>Security  
For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).  
  
## <a name="TSQL"></a>Using Transact-SQL  
  
#### To list job category information  
  
1.  In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].  
  
2.  On the Standard bar, click **New Query**.  
  
3.  Copy and paste the following example into the query window and click **Execute**.  
  
    ```  
    -- returns information about jobs that are administered locally  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_category  
        @type = N'LOCAL' ;  
    GO  
    ```  
  
For more information, see [sp_help_category (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-help-category-transact-sql).  
  
## <a name="SMO"></a>Using SQL Server Management Objects  
**To list job category information**  
  
Use the **JobCategory** class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.  
