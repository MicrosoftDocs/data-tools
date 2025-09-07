---
title: "Manage Objects Using Object Explorer"
description: "This article is an overview of managing objects using Object Explorer in SQL Server Management Studio."
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mikeray
ms.date: 09/07/2025
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.SWB.SQLSERVEROBJECTEXPLORER.DHELP"
helpviewer_keywords:
  - "Object Explorer F1 Help"
  - "OE F1 Help"
  - "OE Help"
---

# Manage objects using Object Explorer

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

You can use Object Explorer in SQL Server Management Studio (SSMS) to manage objects such as databases, tables, views, stored procedures, functions, and more.

## View objects in Object Explorer

Object Explorer uses a tree structure to group information into folders. To expand a folder, select the plus sign (`+`) or double-click the folder. Expand a folder to show more detailed information, right-click a folder or object to perform a task, and double-click an object to perform the most common task.

The first time you expand a folder, Object Explorer queries the server for information to populate the tree. You can perform other functions while the tree populates. Further actions, such as filtering the list, act only upon the portion of the folder that was populated, unless you refresh the folder to start population again.

To conserve resources when there are many objects, the folders in the Object Explorer tree don't automatically refresh their list of contents. To refresh the list of objects within a folder, right-click the folder, and then select **Refresh**.

Object Explorer can only display up to 65,536 objects. After you exceed 65,536 visible objects, you can't scroll through additional objects in the Object Explorer tree view. To view more objects in Object Explorer, close nodes that you aren't using or apply filtering to reduce the number of objects.

## Filter the list of objects in Object Explorer

When a folder contains a large number of objects, it might be difficult to find the object you're looking for. In such cases, use the filter feature of Object Explorer to reduce the list to a smaller size. For example, you might want to find a specific database user or the most recently created table in lists that contain hundreds of objects. Select the folder that you want to filter, and then select the filter button to open the **Filter Settings** dialog box. You can filter the list by name, create date, or schema (where appropriate), and provide extra filtering operators like **Starts with**, **Contains**, and **Between**.

## Multi-select

Only one object can be selected at a time in Object Explorer. To select multiple items, select **F7** or **View > Object Explorer Details** to open the **Object Explorer Details Page**. The **Object Explorer Details Page** supports multi-select.

## Register a server from Object Explorer

When connected to a server, you can easily register the server for future use. In Object Explorer, right-click the server name, and then select **Register**. In the **Register Server** dialog box, specify where in the server group tree you want to place the server. In the **Server name** box, you can replace the server name with a more meaningful server name. For example, you could register server **APSQL02** with a more meaningful name such as "**Accounts Payable**".

## Perform actions on Object Explorer folders

Perform actions on folders by right-clicking the Object Explorer folder representing the object. Each type of folder supports a set of right-click actions, for example creating a new object.

## Perform actions on objects

Perform actions on objects by right-clicking object in Object Explorer. Each type of object supports a unique set of right-click actions. Some of the types of actions you can perform by using the right-click menus include:

- Using the designer to modify the object
- Viewing the properties of the object
- Scripting the object

### Open a connected Query Editor

When Object Explorer is connected to a server, you can open a new Query Editor window using the connection settings of Object Explorer. To open a new Query Editor window, right-click the server name in Object Explorer, and then select **New Query**. To open a Query Editor window for a specific database, right-click the database name, and then select **New Query**. When opening a new query for an Analysis Services server, you can select DMX, MDX, or XMLA queries.

### Start PowerShell

You can start a PowerShell session by right-clicking most folders and objects in the Object Explorer tree and selecting **Start PowerShell**. This step starts a PowerShell session that has the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] PowerShell support enabled, and the path set to the object you right-clicked in Object Explorer. You can then enter PowerShell commands in an interactive PowerShell environment. For more information, see [SQL Server PowerShell](/powershell/sql-server/sql-server-powershell).

## Related content

- [Object Explorer](object-explorer.md)
- [Open and configure Object Explorer](open-and-configure-object-explorer.md)
- [Connect to a SQL Server or Azure SQL Database](connect-to-an-instance-from-object-explorer.md)
- [Object Explorer Details pane](object-explorer-details-pane.md)
- [Custom reports in SQL Server Management Studio](custom-reports-in-management-studio.md)
