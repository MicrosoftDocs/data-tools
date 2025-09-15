---
title: "External Tools"
description: "External Tools"
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/15/2025
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
helpviewer_keywords:
  - "External Tools dialog box"
---

# External tools

[!INCLUDE [SQL Server Azure SQL Database Azure SQL Managed Instance Synapse Analytics PDW Fabric SE Fabric DW Fabric SQL DB](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw-fabricse-fabricdw-fabricsqldb.md)]

Use this dialog box to add external tools, such as SQL Server Configuration Manager or Notepad, to the **Tools** menu. Adding external tools allows you to easily launch other applications while working in [!INCLUDE [ssManStudioFull](../includes/ssmanstudiofull-md.md)]. You can specify arguments and a working directory when launching the tool. In addition, the outputs from some tools can be displayed in the Output window. The **External Tools** dialog box is available on the **Tools** menu.

## Options

#### Menu Contents

Lists the titles of the items currently added to the **Tools** menu. Use the **Move Up** and **Move Down** arrows to change the order the items that appear on the menu. Use the **Delete** button to remove an item from the menu.

#### Move Up

Move the selected tool higher in the list of tools that appear on the **Tools** menu.

#### Move Down

Move the selected tool lower in the list of tools that appear on the **Tools** menu.

#### Add

Clear the text boxes so you can specify a new tool.

#### Delete

Remove the tool or command from the **Menu Contents** list as well as from the **Tools** menu.

#### Title

The name of the tool or command that appears on the **External Tools** submenu of the **Tools** menu. Place an ampersand before a letter in the name of the tool to use that letter as an accelerator key for the tool. For example, `&Spy++` would display **Spy++** on the **Tools** menu.

#### Command

Specify the path to the .exe, .com, .pif, .bat, .cmd, or other file that you intend to launch. The output from `.bat`, `.com`, and other files can be viewed in the Output window if you select the **Use output window** check box.

#### Arguments

Specify the variables that are passed to the tool when the tool is selected on the menu. Arguments can specify values that are passed to the tool or command when it launches. For example, a value can specify a file name or directory. Use the **Arrow** button to select from a list of predefined arguments. You can add more than one. For a complete list of predefined arguments and their definitions, see [Arguments for External Tools](../use-of-sql-server-features-and-capabilities-wwi-oltp.md). You can also enter custom arguments (command-prompt switches, for example), depending on the command or tool you use.

#### Initial directory

Specify the working directory of the tool. Use the **Arrow** button to select directories. You can select more than one.

#### Use output Window

Specify whether or not results from the tool are displayed in the Output window. This option is only available for files, such as .bat and .com files, that normally display output in the command prompt window. When enabled, this option eases window management when you're following the progress of a tool.

#### Prompt for arguments

Display the **Arguments** dialog box to enable you to enter or edit values for the arguments each time you launch the external tool.

#### Treat output as Unicode

Allow the Output window to accept Unicode.

#### Close On Exit

Close the window opened by the tool when the tool is closed.

## Examples

### Add SQL Server Configuration Manager to the Tools menu

1. On the **Tools** menu, select **External Tools**.

1. In the **Title** box, type **SQL Server Configuration Manager**.

1. In the **Command** box, type the path to the [!INCLUDE [msCoName](../includes/msconame-md.md)] Management Console executable, such as `C:\WINNT\system32\mmc.exe`

1. In the **Arguments** box, type the path to the .msc file, such as `"C:\WINNT\system32\SQLServerManager.msc"`

> [!NOTE]  
> View the properties of the SQL Server Management Studio shortcut on the **Start** menu to confirm the location of the files on your computer.
