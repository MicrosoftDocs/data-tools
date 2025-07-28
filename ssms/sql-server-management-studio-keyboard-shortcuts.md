---
title: SQL Server Management Studio Keyboard Shortcuts
description: SQL Server Management Studio keyboard shortcuts
author: rwestMSFT
ms.author: randolphwest
ms.date: 07/28/2025
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
f1_keywords:
  - "VS.ToolsOptionsPages.Environment.Keyboard"
  - "VS.ToolsOptionsPages.Environment.Keyboard.Query_Shortcuts"
helpviewer_keywords:
  - "SQL Server Management Studio [SQL Server], shortcuts"
  - "keyboard shortcuts [SQL Server Management Studio]"
  - "menu shortcuts [SQL Server Management Studio]"
  - "Query Editor [SQL Server Management Studio], keyboard shortcuts"
  - "hot keys [SQL Server Management Studio]"
  - "shortcuts [SQL Server Management Studio], keyboard shortcuts"
  - "keyboard shortcuts [SQL Server Management Studio], list of shortcuts"
  - "shortcuts [SQL Server Management Studio]"
  - "accelerator keys"
---

# SQL Server Management Studio keyboard shortcuts

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

SQL Server Management Studio (SSMS) offers keyboard shortcuts. By default, it uses the SQL Server scheme, with keyboard shortcuts based on Visual Studio. To change the keyboard scheme or add more keyboard shortcuts, from the **Tools** menu, select **Options**. Select the desired keyboard scheme on the **Environment**, **Keyboard** page.

> [!NOTE]  
> To show only the headings, select **Collapse All** at the top of this page.

## Menu Activation keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Move to the SQL Server Management Studio menu bar | ALT |
| Activate the menu for a tool component | ALT+HYPHEN |
| Display the context menu | SHIFT+F10 |
| Display the **New File** dialog box to create a file | CTRL+ALT+N |
| Display the **New Project** dialog box to create a new project | CTRL+SHIFT+N |
| Display the **Open File** dialog box to open an existing file | CTRL+O |
| Display the **Open Project** dialog box to open an existing project | CTRL+SHIFT+O |
| Display the **Add New Item** dialog box to add a new file to the current project | CTRL+SHIFT+A |
| Display the **Add Existing Item** dialog box to add an existing file to the current project | SHIFT+ALT+A |
| Close a menu or dialog box, canceling the action | ESC |

## Windows Management and Toolbar keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Open a new query editor window | CTRL+N |
| Cycle through the MDI child windows | CTRL+F6<br />or<br />CTRL+SHIFT+F6 |
| Cycle through the MDI child windows using the IDE navigator | CTRL+TAB<br />or<br />CTRL+SHIFT+TAB |
| Display a popup listing all open MDI child windows | CTRL+ALT+DOWN ARROW |
| Display the IDE navigator with the first tool window selected | ALT+F7 |
| Display the IDE navigator with the first MDI child window selected | CTRL+TAB |
| Display the dock menu | ALT+MINUS SIGN (-) |
| Display Query Designer (avilble for the query editor) | CTRL+SHIFT+Q |
| Display Object Explorer | F8 |
| Display Object Explorer Details | F7 |
| Display Registered Servers | CTRL+ALT+G |
| Display Template Explorer | CTRL+ALT+T |
| Display Solution Explorer | CTRL+ALT+L |
| Display Copilot in SSMS | CTRL+ALT+C |
| Display the Properties Window | F4 |
| Display the **Output** window | CTRL+ALT+O |
| Display the **Task List** window | CTRL+\\, T<br />or<br />CTRL+\\, CTRL+T |
| Display the Toolbox | CTRL+ALT+X |
| Display the Bookmarks Window | CTRL+K, CTRL+W |
| Display the Browser Window | CTRL+ALT+R |
| Display the previous page in the viewing history. Available only in the Web browser window | ALT+LEFT ARROW |
| Display the next page in the viewing history. Available only in the Web browser window | ALT+RIGHT ARROW |
| Display the Error List Window ([!INCLUDE [tsql](includes/tsql-md.md)] Editor only) | CTRL+\\, CTRL+E |
| Move to the next entry in the Error List window ([!INCLUDE [tsql](includes/tsql-md.md)] Editor only) | CTRL+SHIFT+F12 |
| Moves the insertion point to the dropdown bar located at the top of the code editor when the editor is in Code view or Server Code view | CTRL+F2 |
| Move to the current tool window toolbar | SHIFT+ALT |
| Move to the next tool window | ALT+F6 |
| Move to the previous tool window | SHIFT+ALT+F6 |
| Move to the next pane of a split pane view of a single document | F6 |
| Move to the previous pane of a split pane view of a single document | SHIFT+F6 |
| Toggle between the **Query Editor** and the **Results Pane** | F6 |
| Toggle between **Object Explorer Details** list view and **Object Explorer Details** property pane. | F6 |
| Toggle full screen mode | SHIFT+ALT+ENTER |
| Control the splitter bar that separates the **Object Explorer Details** list view and **Object Explorer Details** property pane to adjust the size of the display pane. | TAB, then hold the UP arrow or DOWN arrow |
| Close a menu or dialog box, cancel an operation in progress, or focus on the current document window | ESC |
| Close the current MDI child window | CTRL+F4 |
| Close the current tool window | SHIFT+ESC |
| Exit | ALT+F4 |
| Print | CTRL+P |

## Cursor Movement keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Move the cursor left | LEFT ARROW |
| Move the cursor right | RIGHT ARROW |
| Move up the cursor | UP ARROW |
| Move the cursor down | DOWN ARROW |
| Move the cursor to the beginning of the line | HOME |
| Move the cursor to the end of the line | END |
| Move the cursor to the beginning of the document | CTRL+HOME |
| Move the cursor to the end of the document | CTRL+END |
| Move up the cursor one screen | PAGE UP |
| Move the cursor down one screen | PAGE DOWN |
| Moves the cursor one word to the right | CTRL+ RIGHT ARROW |
| Moves the cursor one word to the left | CTRL+ LEFT ARROW |
| Moves the cursor to the top of the document | CTRL+PAGE UP |
| Moves the cursor to the bottom of the document | CTRL+PAGE DOWN |

## Text Selection keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Select text from the cursor to the start of the current line | SHIFT+HOME |
| Select text from the cursor to the end of the current line | SHIFT+END |
| Select text from the cursor to the beginning of the document | CTRL+SHIFT+ HOME |
| Select text from the cursor to the end of the document | CTRL+SHIFT+END |
| Select text up line by line starting from the cursor | SHIFT+UP ARROW |
| Select text down line by line starting from the cursor | SHIFT+DOWN ARROW |
| Select the word containing the cursor, or the closest word | CTRL+W |
| Select the current location in the editor, back to the previous location in the editor | CTRL+= |
| Select the entire current document | CTRL+A |
| Move the cursor one character to the left and extend the selection | SHIFT+LEFT ARROW |
| Move the cursor one character to the left and extend the column selection | SHIFT+ALT+LEFT ARROW |
| Move the cursor one character to the right and extend the selection | SHIFT+RIGHT ARROW |
| Move the cursor one character to the right and extend the column selection | SHIFT+ALT+RIGHT ARROW |
| Move the cursor to the start of the current line and extend the column selection | SHIFT+ALT+HOME |
| Move the cursor to the end of the line and extend the column selection | SHIFT+ALT+END |
| Move the cursor to the right one word and extend the selection | CTRL+SHIFT+ALT+RIGHT ARROW |
| Move the cursor to the left one word and extend the selection | CTRL+SHIFT+ALT+LEFT ARROW |
| Move the cursor up one line and extend the selection | SHIFT+ALT+UP ARROW |
| Move the cursor down one line and extend the selection | SHIFT+ALT+DOWN ARROW |
| Move the cursor up one page and extend the selection | SHIFT+PAGE UP |
| Move the cursor down one page and extend the selection | SHIFT+PAGE DOWN |
| Extend the selection to the top of the current window | CTRL+SHIFT+PAGE UP |
| Extend the selection to the bottom of the current window | CTRL+SHIFT+PAGE DOWN |
| Select the text from the current location of the cursor to the Navigate Backward (CTRL+MINUS SIGN (-)) location | CTRL+EQUAL SIGN (=) |
| Go back to the previous document or window in the navigation history | CTRL+MINUS SIGN (-) |
| Go forward to the next document or window in the navigation history | CTRL+SHIFT+MINUS SIGN (-) |
| Swaps the anchor and end points of the current selection | CTRL+K, CTRL+A |

## Code Editor keyboard shortcuts

All shortcuts aren't implemented in all types of code editors.

| Action | Shortcut |
| --- | --- |
| Toggle the full-screen display | SHIFT+ALT+ENTER |
| Scroll text up one line | CTRL+UP ARROW |
| Scroll text down one line | CTRL+DOWN ARROW |
| Reverse the last editing action | CTRL+Z<br />or<br />ALT+BACKSPACE |
| Restore the previously undone edit | CTRL+SHIFT+Z<br />or<br />CTRL+Y<br />or<br />ALT+SHIFT+BACKSPACE |
| Save the selected item | CTRL+S |
| Save all | CTRL+SHIFT+S |
| Close | CTRL+F4 |
| Exit | ALT+F4 |
| Delete all text in the current file | CTRL+SHIFT+DEL |
| Display the **Go To Line** dialog box | CTRL+G |
| Increase line indent | TAB |
| Decrease line indent | SHIFT+TAB |
| Make the selected text uppercase | CTRL+SHIFT+U |
| Make the selected text lowercase | CTRL+SHIFT+L |
| Comment the selected text | CTRL+K, CTRL+C |
| Uncomment the selected text | CTRL+K, CTRL + U |
| Open a new query with current connection | CTRL+N |
| Specify values for template parameters | CTRL+SHIFT+M |
| Run the selected portion of the query editor or the entire query editor if nothing is selected | F5 |
| Parse the selected portion of the query editor or the entire query editor if nothing is selected | CTRL+F5 |
| Display the estimated execution plan | CTRL+L |
| Cancel the executing query | ALT+BREAK |
| Include actual execution plan in the query output | CTRL+M |
| Output results in a grid | CTRL+D |
| Output results in text format | CTRL+T |
| Output results to a file | CTRL+SHIFT+F |
| Show or hide the query results pane | CTRL+R |
| Toggle between query and results pane | F6 |
| Copy the result grid and headers to the clipboard | CTRL+SHIFT+C |
| Open [!INCLUDE [ssSqlProfiler](includes/sssqlprofiler-md.md)] | CTRL+ALT+P |
| Display the Query Designer dialog from the query editor window | CTRL+SHIFT+Q |
| Run the **sp_help** system stored procedure | ALT+F1 |
| Run the **sp_who** system stored procedure | CTRL+1 |
| Run the **sp_lock** system stored procedure | CTRL+2 |
| Print | CTRL+P |

   > [!NOTE]  
   > Additional keyboard shortcuts can be configured to execute stored procedures in **Tools** > **Options** > **Keyboard** > **Query Shortcuts**.

## Text Manipulation in Code Editor keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Insert a new line | ENTER or SHIFT+ENTER |
| Delete one character to the right of the cursor | DELETE |
| Delete one character to the left of the cursor | BACKSPACE<br />or<br />SHIFT+BACKSPACE |
| Delete whitespace in the selection, or deletes whitespace next to the cursor if there's no selection | CTRL+K, CTRL+\\ |
| Insert the number of spaces configured for the editor (configured in **Tools** > **Options** > **Text Editor** > **All Languages** > **Tabs**) | TAB |
| Insert a blank line above the cursor | CTRL+ENTER |
| Insert a blank line below the cursor | CTRL+SHIFT+ ENTER |
| Change the selected text to lowercase | CTRL+SHIFT+L |
| Change the selected text to uppercase | CTRL+SHIFT+U |
| Toggle between insert mode and overtype mode | INSERT |
| Move selected lines to the left on tab stop | SHIFT+TAB |
| Delete the word to the right of the cursor | CTRL+DELETE |
| Delete the word to the left of the cursor | CTRL+BACKSPACE |
| Move the line containing the cursor below the next line | SHIFT+ALT+T |
| Toggle outlining expansion for the selected outline | CTRL+M, CTRL+M |
| Toggle all outlining for the active query editor | CTRL+M, CTRL+L |
| Remove all outlining information active query editor | CTRL+M, CTRL+P |

## Microsoft IntelliSense keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Enable or disable IntelliSense | CTRL+B, CTRL+I |
| List members | CTRL+J |
| Complete word | ENTER<br />or<br />TAB |
| Launch code snippet picker | CTRL+K, CTRL+X |
| Refresh local cache | CTRL+SHIFT+R |
| Launch Surround With snippet picker | CTRL+K, CTRL+S |
| Display the Code Snippet Manager | CTRL+K, CTRL+B |

## Solution Explorer keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Display Solution Explorer | CTRL+ALT+L |
| Display the **New File** dialog box to create a new file | CTRL+SHIFT+A |
| Display the **New Project** dialog box to create a new project | CTRL+SHIFT+N |
| Display the **Open File** dialog box to open an existing file | CTRL+O |
| Change the name of the selected object | F2 |

## Bookmark keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Set or remove a bookmark at the current line | CTRL+K, CTRL+K |
| Next bookmark | CTRL+K, CTRL+N |
| If the current bookmark is in a folder, moves to the next bookmark in the folder. Bookmarks outside the folder are skipped.<br /><br />If the bookmark isn't in a folder, moves to the next bookmark at the same level.<br />If the Bookmarks window contains folder, bookmarks in folders are skipped. | CTRL+SHIFT+K, CTRL+SHIFT+N |
| Previous bookmark | CTRL+K, CTRL+P |
| If the current bookmark is in a folder, moves to the next bookmark in the folder. Bookmarks outside the folder are skipped.<br /><br />If the bookmark isn't in a folder, moves to the next bookmark at the same level.<br />If the Bookmarks window contains folder, bookmarks in folders are skipped. | CTRL+SHIFT+K, CTRL+SHIFT+P |
| Clear bookmarks | CTRL+K, CTRL+L |

## Tree Control keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Collapse tree nodes | - (on the numeric keypad) |
| Expand all tree nodes | * (on the numeric keypad) |
| Move up the tree control in the window | UP ARROW |
| Move the tree control down in the window | DOWN ARROW |

## Help and Books Online keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Help | F1<br />or<br />SHIFT+F1 |
| Display SQL Server Books Online | CTRL+F1 |
| Open the Help Library Manager | CTRL+ALT+F1 |
| Display the SQL Server Resource Center Web page | CTRL+ALT+F2 |
| Display help for the current editor window | SHIFT+F1 |

## Search keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Display the **Find** dialog box | CTRL+F |
| Display the **Replace** dialog box | CTRL+H |
| Display the **Replace in Files** dialog box | CTRL+SHIFT+H |
| Find the next occurrence of the search text | F3 |
| Find the previous occurrence of the search text | SHIFT+F3 |

## Cut and Paste keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Copy to the Clipboard | CTRL+C<br />or<br />CTRL+INSERT |
| Paste from the Clipboard at the insertion point | CTRL+V<br />or<br />SHIFT+INSERT |
| Pastes an item from the Clipboard Ring at the insertion point and automatically selects the pasted item | CTRL+SHIFT+V |
| Cut (delete the currently selected item and place it to the Clipboard) | CTRL+X |

## Activity Monitor keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Launches Activity Monitor | CTRL+ALT+A |
| Closes Activity Monitor | SHIFT+Esc |
| Refresh | F5 |
| Cycle through panels | F6 |
| Copies entire selected row in grid | CTRL+C |
| Copy cell | CTRL+SHIFT+C |
| Dropdown for filtering in grid | ALT+DOWN |
| Scroll up or down Activity Monitor | CTRL+ALT+UP/DOWN |

## Replication Monitor keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Refresh | F5 |
| Open a detail window from a grid | ENTER |

## Replication Conflict Viewer keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Define filter | F6 |
| Apply filter | F7 |
| Show all columns | F8 |

## Query Designer keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Displays or hides the diagram pane of the **Query Designer** | CTRL+1 |
| Displays or hides the criteria pane of the **Query Designer** | CTRL+2 |
| Displays or hides the SQL pane of the **Query Designer** | CTRL+3 |

## View Query Designer keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Displays or hides the diagram pane of the **Query Designer** | CTRL+1 |
| Displays or hides the criteria pane of the **Query Designer** | CTRL+2 |
| Displays or hides the SQL pane of the **Query Designer** | CTRL+3 |

## Table Designer keyboard shortcuts

| Action | Shortcut |
| --- | --- |
| Move up the list of controls on the design surface | UP ARROW |
| Move down the list of controls on the design surface | DOWN ARROW |
| Move right in the list of selected controls on the design surface | RIGHT ARROW |
| Move left in the list of selected controls on the design surface | LEFT ARROW |
| Move forward through the options of the selected control | SHIFT+DOWN ARROW |
| Move backward through the options of the selected control| SHIFT+UP ARROW |
| Moves to the next control on the page | TAB |
| Moves to the previous control on the page | SHIFT+TAB |
| Display the grid on the design surface | ENTER |

## Related content

- [Customize Menus and Shortcut Keys](customize-menus-and-shortcut-keys.md)
