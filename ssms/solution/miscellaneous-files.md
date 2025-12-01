---
title: "Miscellaneous Files"
titleSuffix: SQL Server Management Studio
description: Work with miscellaneous files in SQL Server Management Studio (SSMS) projects and solutions.
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/01/2025
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "files [SQL Server Management Studio], miscellaneous"
  - "projects [SQL Server Management Studio], files"
  - "solutions [SQL Server Management Studio], files"
  - "miscellaneous files folder [SQL Server]"
---
# Miscellaneous project files (SQL Server Management Studio)

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

Files that are external to any SQL Server Management Studio (SSMS) project are called *miscellaneous files*. When you have a project or solution open, you can open and modify miscellaneous files related to the project. A file is classified as a miscellaneous file if the file extension isn't associated with the project code editor.

For example, in a [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Scripts project, files with the extension `.txt` or `.mdx` are treated as miscellaneous files. In an MDX project, files with the extension of `.txt` or `.sql` are treated as miscellaneous files. To associate a file extension with a code editor, see [Associate file extensions to a code editor](../scripting/associate-file-extensions-to-a-code-editor.md).

## Work with miscellaneous files

There are several reasons why it's useful to add miscellaneous files to your project. You might have a file that isn't necessarily a recognized script but is integral to the solution's development. Common examples include development notes or instructions, data files, and code clips.

Miscellaneous files provide flexibility. For example, suppose you have a [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Scripts project that has several scripts for creating tables and stored procedures in your database. You also have several data files for the tables with file extensions `.bcp`, and execution instructions in a `README` file. You can attach the data and the `README` files as miscellaneous files to the project, so you can take advantage of source control and other features of the project system.

SSMS menus and toolbars change according to the format of the file you open. When you open a text file, for example, the Text Editor toolbar appears. If you open an XML schema file, the XML Schema toolbar appears. When you edit your XML schema, the Text Editor toolbar is unavailable. When you switch between a project file and a miscellaneous file, all project-related commands and toolbars are replaced by the commands and toolbars relevant to the miscellaneous file.

## Related content

- [Files that manage solutions and projects](files-that-manage-solutions-and-projects.md)
- [Solutions (SQL Server Management Studio)](solutions-sql-server-management-studio.md)
- [Projects (SQL Server Management Studio)](projects-sql-server-management-studio.md)
