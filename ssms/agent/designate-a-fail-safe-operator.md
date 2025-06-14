---
title: "Designate a Fail-Safe Operator"
description: "Designate a Fail-Safe Operator"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Agent jobs, operators"
  - "fail-safe operator [SQL Server]"
  - "jobs [SQL Server Agent], operators"
  - "notifications [SQL Server], job status"
---
# Designate a Fail-Safe Operator
[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

A fail-safe operator is a user who receives the alert if the designated operator cannot be reached. This topic describes how to set a fail-safe operator to receive [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent alert notifications in [!INCLUDE[ssnoversion](../includes/ssnoversion-md.md)] by using SQL Server Management Studio.  
  
## <a name="BeforeYouBegin"></a>Before You Begin  
  
### <a name="Restrictions"></a>Limitations and Restrictions  
  
-   The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. Avoid using these features in new development work, and plan to modify applications that currently use these features.  
  
-   Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators. For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).  
  
-   SQL Server Management Studio provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.  
  
### <a name="Security"></a>Security  
  
#### <a name="Permissions"></a>Permissions  
Only members of the **sysadmin** fixed server role can designate fail-safe operators.  
  
## <a name="SSMSProcedure"></a>Using SQL Server Management Studio  
  
#### To designate a fail-safe operator  
  
1.  In **Object Explorer,** click the plus sign to expand the server that contains the SQL Server Agent operator that you want to designate as a fail-safe.  
  
2.  Right-click **SQL Server Agent** and select **Properties**.  
  
3.  In the **SQL Server Agent Properties -**_server\_name_ dialog box, under **Select a page**, select **Alert System**.  
  
4.  Under **Fail-safe operator**, select **Enable fail-safe operator**.  
  
5.  In the **Operator** list, select the operator that you want to make a fail-safe.  
  
6.  Select either any or all of the following check boxes to specify how the operator will be notified: **E-mail**, **Pager**, or **Net send**.  
  
7.  When finished, click **OK**.  
