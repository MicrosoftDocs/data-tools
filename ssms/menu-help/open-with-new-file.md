---
title: "Open With (New File)"
description: "Open With (New File)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/15/2025
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
helpviewer_keywords:
  - "Open With dialog box"
---
# Open With (New File)

[!INCLUDE [SQL Server Azure SQL Database Azure SQL Managed Instance Synapse Analytics PDW Fabric SE Fabric DW Fabric SQL DB](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw-fabricse-fabricdw-fabricsqldb.md)]

You can open a document in one or more editors by selecting **Open** on the **File** menu and then selecting **File**. In the **Open File** dialog box, select the file, select the **Open** arrow, and then select **Open With**. In the **Open With** dialog box, in the **Select a program to open** list, select the preferred program, and then select **Open**.

## Options

#### Select a program to open

Lists the editors available in Visual Studio for the selected type of file. Choose the editor with which to open the document from the list displayed, or select **Add** to include a new editor in the list.

#### Open

Select **Open** to open the document in the selected editor.

#### Add

Select this button to add a program to the list under **Select a program to open**. You can either type the file path to the program in the **Program Name** field or browse to the program's location by selecting **Browse**. In **Friendly Name**, enter a program name to display in the list under **Select a program to open**.

#### Remove

To remove a program, select the program and then select **Remove**.

#### Set as Default

To specify a default editor (and language encoding options, if applicable) for the type of file selected, choose a program from the list under **Select a program to open** and then select **Set as Default**. The next time you open this type of file in SQL Server Management Studio, the document will open in the new default editor.

> [!NOTE]  
> In the list of programs under **Select a program to open**, the name of the default editor for the type of file selected is followed by **(Default)**.

## Related content

- [Associate file extensions to a code editor](../scripting/associate-file-extensions-to-a-code-editor.md)
