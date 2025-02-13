---
title: Edit a Breakpoint Location
titleSuffix: T-SQL debugger
description: Learn how to move a breakpoint in a Transact-SQL script file to another location in the script, or to a different script.
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/04/2019
ms.service: sql-server-management-studio
ms.topic: conceptual
helpviewer_keywords:
  - "Transact-SQL debugger, breakpoint location"
---

# Edit a Breakpoint Location

 [!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

The breakpoint location specifies the line and character where the breakpoint resides in a [!INCLUDE[tsql](../includes/tsql-md.md)] script file. You can edit the breakpoint location to move the breakpoint to another location in the script, or to a different script.

## Editing a Location

When you edit a breakpoint location, the breakpoint moves to the new location, carrying with it all of the existing properties, such as a hit count or condition.  

#### To Edit a Breakpoint Location

1. In the editor window, right-click the breakpoint glyph, and then click **Location** on the shortcut menu.  
  
     -or-  
  
     In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Location** on the shortcut menu.  
  
2. In the **File Breakpoint** dialog box, edit **File** to specify a new file, **Line** to specify a new line, or **Character** to specify a new location within the line. If the new file you specify is already open in a query editor window, the breakpoint is moved to that editor window. If the file is not opened, a new editor window is opened, the file is loaded in, and the breakpoint moved to the new location.  
  
     The **Allow the source code to be different from the original version** option has no effect when debugging [!INCLUDE[tsql](../includes/tsql-md.md)].  
  
## See Also

- [Specify a Hit Count](/sql/ssdt/debugger/specify-hit-count)
- [Specify a Breakpoint Action](/sql/ssdt/debugger/specify-breakpoint-action)
- [Specify a Breakpoint Condition](/sql/ssdt/debugger/specify-breakpoint-condition)
- [Specify a Breakpoint Filter](/sql/ssdt/debugger/specify-breakpoint-filter)
