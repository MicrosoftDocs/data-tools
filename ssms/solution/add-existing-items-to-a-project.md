---
title: Add Existing Items to a Project
description: Learn how to add new items to a project to extend application functionality.
author: rwestMSFT
ms.author: randolphwest
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "projects [SQL Server Management Studio], item additions"
  - "adding project items"
---
# Add existing items to a project

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

Add new items to a project to extend application functionality. An existing item can be a query or a miscellaneous file. [!INCLUDE [ssManStudioFull](../includes/ssmanstudiofull-md.md)] has two project types: [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Script Project, and Analysis Services Script Project. The project type determines the query files that you can add to the project. For example, you can add a [!INCLUDE [tsql](../includes/tsql-md.md)] query (a file with a .sql extension) to a [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Script project, but you can't add it to an Analysis Services Script Project. To associate other file extensions to a project type, see [Associate file extensions to a code editor](../scripting/associate-file-extensions-to-a-code-editor.md).

## Add an existing query or a miscellaneous file to a project

1. In Solution Explorer, select a target project.

1. On the **Project** menu, select **Add Existing Item**.

   - **Look in**

     Locate the files or folders to add to your project from this list. For XML Web services and ASP.NET Web applications, the files are located on the Web server.

   - **Desktop**

     Displays the files and folders located on the desktop.

   - **My Projects**

     Displays the files and folders at the default **My Projects** location.

   - **My Computer**

     Displays the contents of your **My Computer** folder.

   - **File name**

     Use this option to filter the files and folders that are displayed. Enter the full or partial file name on which to filter; use an asterisk (`*`) as a wildcard.

     > [!NOTE]  
     > Navigate to Web and network locations by entering the URL or network path in the **File name** box. For example, `https://mywebsite` displays the files available at the `mywebsite` Web location, and `\\myserver\myshare` displays the files available at the myshare location on `myserver`.

   - **Files of type**

     Use this option to filter files based on file extension. Each product lists default filters of the most common file types.

   - **Add**
  
     Use this dropdown list button to add the item to the project and open the item in its default editor.

     - **Add**

       Copies the existing item to your project folder on disk and adds the item under the selected project in Solution Explorer. Any changes made to the item aren't reflected in the item at the original location. This is the default editor for the file type.

     - **Add As Link**

       Adds the selected file to the project and opens it with the default editor for the file type. This option opens the originally selected file and doesn't copy the file to the project folder.

1. If you're adding query files, the connection dialog prompts you to specify a connection for the query. You can select **Cancel** on the connection dialog if you don't want to associate a connection to the query.

1. The file is added to the **Queries** or **Miscellaneous Files** folder of the project.

## Related content

- [Solution Explorer](solution-explorer.md)
- [Add New Items to a Project](add-new-items-to-a-project.md)
- [Remove or Delete an Item or Project](remove-or-delete-an-item-or-project.md)
