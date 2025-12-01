---
title: "Files That Manage Solutions and Projects"
titleSuffix: SQL Server Management Studio
description: Learn about the file types that are specific to SQL Server Management Studio (SSMS) for managing solutions and projects.
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/01/2025
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "projects [SQL Server Management Studio], files"
  - ".ssmssln files"
  - ".ssmsmobileproj files"
  - ".ssmsasproj files"
  - ".ssmssqlproj files"
  - ".sqlsuo files"
  - "files [SQL Server Management Studio], projects"
---
# Files that manage solutions and projects

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This article describes the file types that are specific to [!INCLUDE [ssManStudioFull](../includes/ssmanstudiofull-md.md)] (SSMS). By default, all solutions and their projects are created in `SQL Server Management Studio Projects` under your local user folder.

## Management Studio solution files

SSMS uses different file types than [!INCLUDE [ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] or Visual Studio. This means you can't open an SSMS solution in [!INCLUDE [ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] or in Visual Studio. SSMS solution files allow Solution Explorer to display a graphical interface for managing your files.

| Extension | File type | Description | Created by |
| --- | --- | --- | --- |
| `.ssmssln` | SSMS solution object | Provides the environment with references to the location on disk of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] projects, project items, and solution | SQL Server Management Studio |

## Management Studio project files

In the same way that solutions contain solution files that manage objects in a solution, projects contain project files. The type of project file that SSMS creates for a project depends on the template used to create the project. The following table describes the type of file created for each project.

| Extension | Project template |
| --- | --- |
| .ssmssqlproj | [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Scripts Project |
| .ssmsasproj | [!INCLUDE [ssASnoversion](../includes/ssasnoversion-md.md)] Scripts Project |

## Location of solution-Level files

By default, solution-level files are created in the physical directory of the first project that is created with the solution. You can specify a directory for the solution by creating a solution, or you can specify the directory when you create a new project.

If you have a directory structure similar to the logical structure shown in Solution Explorer, project and solution files are easier to locate and share with other developers on a team.

## Related content

- [Manage Files with Encoding](manage-files-with-encoding.md)
- [Miscellaneous project files (SQL Server Management Studio)](miscellaneous-files.md)
- [Solution Explorer (SQL Server Management Studio)](solution-explorer.md)
- [Solutions (SQL Server Management Studio)](solutions-sql-server-management-studio.md)
- [Projects (SQL Server Management Studio)](projects-sql-server-management-studio.md)
