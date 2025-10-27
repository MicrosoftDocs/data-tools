---
title: "Save As"
description: "Save As"
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/15/2025
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "vs.saveas"
helpviewer_keywords:
  - "Save As dialog box"
---
# Save As

[!INCLUDE [SQL Server Azure SQL Database Azure SQL Managed Instance Synapse Analytics PDW Fabric SE Fabric DW Fabric SQL DB](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw-fabricse-fabricdw-fabricsqldb.md)]

Used to save an instance of the current item at a specified location in a specified file format. Select **Save** *\<file\>* **As** on the **File** menu (where *\<file\>* is the name of the current item), or press ALT+F, A in the Code Editor.

## Central panel

#### Save in

Locate the existing project folder from this dropdown menu. Selecting a folder from this list displays the contents of the folder in the primary pane below.

#### File name

Use this option to view the current file name, change the file name, or filter the files and folders that are displayed. To filter the files and folders that are displayed, enter a full or partial file name on which to filter. You can use the asterisk (`*`) as a wildcard.

> [!TIP]  
> To display files on Web and network locations, enter a URL or network path in the **File name** box. For example, `https://mywebsite` displays the files available at the "mywebsite" Web location and "\\\myserver\myshare" displays the files available at the "myshare" location on "myserver".

#### Save as type

Use this option to select a new file type for the selected item. The file types displayed include all available file types to which the selected item can be converted.

#### Advanced Save Options

To access the **Advanced Save Options Dialog Box**, select the small rectangle at the right of the **Save** button and then select **Save with Encoding**. Use this dialog box to specify an encoding for the file and the characters to use at Line endings.

## Left panel

#### Desktop

Displays any files and folders located on the desktop.

#### My Projects

Displays files and folders at the **My Projects** or the most recently visited location.

#### My Computer

Displays the **My Computer** location on your computer.

## Related content

- [Advanced Save Options](advanced-save-options.md)
- [Manage Files with Encoding](../solution/manage-files-with-encoding.md)
