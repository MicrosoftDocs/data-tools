---
title: Build Database Projects
description: Build database projects with SQL Server Management Studio
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/07/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "scripts [SQL Server], database projects"
  - "database projects [SQL Server]"
  - "projects [SQL Server Management Studio], about projects"
  - "projects [SQL Server Management Studio]"
---

# Build database projects with SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Azure SQL Managed Instance Synapse Analytics PDW Fabric SE Fabric DW Fabric SQL DB](includes/applies-to-version/sql-asdb-asdbmi-asa-pdw-fabricse-fabricdw-fabricsqldb.md)]

A database script project is an organized set of scripts, connection information, and templates that are all associated with a database or one part of a database. Microsoft SQL Server provides the SQL Server Management Studio for administering and designing SQL Server databases within the context of a script project. SQL Server Management Studio includes designers, editors, guides, and wizards to assist users in developing, deploying, and maintaining databases.

## SQL Server Management Studio

SQL Server Management Studio is a suite of administrative tools for managing the components belonging to SQL Server. This integrated environment allows users to perform various tasks, such as backing up data, editing queries, and automating common functions within a single interface.

SQL Server Management Studio includes the following tools:

- Code Editor is a rich script editor for writing and editing scripts. SQL Server Management Studio provides four versions of the Code Editor; the Database Engine Query Editor for [!INCLUDE [tsql](includes/tsql-md.md)] scripts, the DMX Query Editor, the MDX Query Editor, and the XML/A Query Editor.

- Object Explorer for locating, modifying, scripting, or running objects belonging to instances of SQL Server.
- Template Explorer for locating and scripting templates.
- Solution Explorer for organizing and storing related scripts as parts of a project.
- Properties Window for displaying the current properties of selected objects.

SQL Server Management Studio supports efficient work processes by providing:

- Disconnected access. You can write and edit scripts without connecting to an instance of SQL Server.

- Scripting from any dialog box. You can create a script from any dialog box so that you can read, modify, store, and reuse the scripts after you create them.

- Nonmodal dialog boxes. When you access a UI dialog box, you can browse other resources in SQL Server Management Studio without closing the dialog box.

## Solutions and script projects

Solution Explorer is a utility to store and reopen database solutions. Solutions organize related script projects and files. Script projects store SQL Server script files, SQL templates, connection information, and other miscellaneous files. When a script is saved in a script project, users are able to:

- Maintain version control on scripts.
- Store results options with a script.
- Organize related scripts in a single script project.
- Save connection information with scripts.

Solution Explorer is a tool for developers who are creating and reusing scripts that are related to the same project. If a similar task is required later, you can use group of scripts that were stored in a project. If you created applications with Microsoft [!INCLUDE [vsprvs](includes/vsprvs-md.md)], Solution Explorer is familiar.

A solution consists of one or more script projects. A project consists of one or more scripts or connections. A project might also include nonscript files.

## Related content

- [What is SQL Server Management Studio (SSMS)?](sql-server-management-studio-ssms.md)
- [Solutions (SQL Server Management Studio)](solution/solutions-sql-server-management-studio.md)
