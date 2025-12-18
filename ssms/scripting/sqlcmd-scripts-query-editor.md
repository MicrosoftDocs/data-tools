---
title: Edit SQLCMD Scripts with Query Editor
titleSuffix: SQL Server Management Studio
description: Write and edit SQLCMD scripts using the query editor. Learn how SQLCMD scripts help you to process Windows System commands and Transact-SQL statements in the same script.
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/17/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "scripts [SQL Server], SQLCMD scripts"
  - "SQLCMD scripts"
  - "[SQL Server Management Studio], SQLCMD scripts"
  - "SSMS, SQLCMD scripts"
  - "modifying scripts"
  - "Query Editor [Database Engine], SQLCMD scripts"
  - "scripts [SQL Server], SQL Server Management Studio"
  - "scripts [SQL Server], SSMS"
---
# Edit SQLCMD scripts with Query Editor

Use the query editor in SQL Server Management Studio (SSMS) to write and edit queries as SQLCMD scripts. You can use SQLCMD scripts to process Windows system commands and Transact-SQL statements in the same script.

## Enable SQLCMD mode

To use the query editor to write or edit SQLCMD scripts, you must enable the SQLCMD scripting mode. SQLCMD mode isn't enabled by default. You can enable scripting mode by selecting the **SQLCMD Mode** icon in the toolbar, or by selecting **SQLCMD Mode** from the **Query** menu.

> [!NOTE]  
> When you enable SQLCMD mode, IntelliSense and the Transact-SQL debugger are turned off in the query editor.

SQLCMD scripts in the query editor can use the same features that all Transact-SQL scripts use. These features include:

- Color coding
- Executing scripts
- Source control
- Parsing scripts
- Showplan

## Enable SQLCMD scripting in Query Editor

To turn on SQLCMD scripting for an active Query Editor window, use the following procedure.

### Switch a query editor window to SQLCMD mode

1. In Object Explorer, right-click the server and then select **New Query** to open a new Query Editor window.

1. On the **Query** menu, select **SQLCMD Mode**.

   SQLCMD statements are executed in the context of the query editor.

1. On the **SQL Editor** toolbar, in the **Available Databases** list, select [!INCLUDE [sssampledbobject-md](../includes/sssampledbobject-md.md)].

1. In the query editor window, type the following Transact-SQL statements and the `!!DIR` SQLCMD statement:

   ```sql
   SELECT DISTINCT Type FROM Sales.SpecialOffer;
   GO
   !!DIR
   GO
   SELECT ProductCategoryID, Name FROM Production.ProductCategory;
   GO
   ```

1. Press F5 to execute the mixed Transact-SQL and MS-DOS statements section.

   Notice the two SQL result panes from the first and third statements.

1. In the **Results** pane, select the **Messages** tab to see the messages from all three statements:

   - `(6 row(s) affected)`
   - `<The directory information>`
   - `(4 row(s) affected)`

> [!IMPORTANT]  
> When you run **sqlcmd** from the command line, it permits full interaction with the operating system. When you use the query editor in **SQLCMD Mode**, be careful not to execute interactive statements. The query editor can't respond to operating system prompts. For more information about how to run SQLCMD from the command line, see [sqlcmd utility](/sql/tools/sqlcmd/sqlcmd-utility).

## Enable SQLCMD scripting by default

To turn on SQLCMD scripting by default, on the **Tools** menu, select **Options**, expand **Query Execution**, and **SQL Server**, select the **General** page and then check the **By default open new queries in SQLCMD Mode** box.

## Write and edit SQLCMD scripts

After you enable scripting mode, you can write both SQLCMD commands and Transact-SQL statements. The following rules apply:

- SQLCMD commands must be the first statement on a line.

- Only one SQLCMD command is permitted on each line.

- You can use comments and white space in front of SQLCMD commands.

- SQLCMD commands within comment characters aren't executed.

- Single-line comment characters are two hyphens (`--`) and must appear at the beginning of a line.

- Prefix operating system commands with two exclamation points (`!!`). The double-exclamation points command causes the statement that follows the exclamation points to be executed using the `cmd.exe` command processor. The text after `!!` is passed in as a parameter to `cmd.exe`, so the final command line executes as: `"%SystemRoot%\system32\cmd.exe /c <text after !!>"`.

- To make a clear distinction between SQLCMD commands and Transact-SQL, prefix all SQLCMD commands with a colon (`:`).

- The `GO` command can be used without preface or preceded by `!!:`.

- The query editor supports environment variables and variables that you define as part of a SQLCMD script, but it doesn't support built-in SQLCMD or **osql** variables. SSMS processes SQLCMD variables as case sensitive. For example, `PRINT '$(COMPUTERNAME)'` produces the correct result, but `PRINT '$(ComputerName)'` returns an error.

> [!CAUTION]  
> SSMS uses the `SqlClient` .NET library for execution in regular and SQLCMD mode. When you run the query from the [command line](/sql/tools/sqlcmd/sqlcmd-utility), **sqlcmd** uses the OLE DB provider. Because different default options could apply, you might see different behavior while executing the same query in SQLCMD mode inside SSMS, compared to SQLCMD mode in the **sqlcmd** utility.

## Supported SQLCMD syntax

The query editor supports the following SQLCMD script keywords:

- `[!!:]GO[count]`
- `!! <command>`
- `:exit(statement)`
- `:Quit`
- `:r <filename>`
- `:setvar <var> <value>`
- `:connect server[\instance] [-l login_timeout] [-U user [-P password]]` <sup>1</sup>
- `:on error [ignore|exit]`
- `:error <filename>|stderr|stdout` <sup>2</sup>
- `:out <filename>|stderr|stdout` <sup>2</sup>

<sup>1</sup> For more information about the `:connect` command, see [Commands in the sqlcmd utility](/sql/tools/sqlcmd/sqlcmd-commands).

<sup>2</sup> The query editor sends output to the **Messages** tab for `stderr` and `stdout`.

The query editor doesn't support SQLCMD commands that aren't included in the preceding list. When you execute a script that contains unsupported SQLCMD keywords, the query editor ignores the command. For each unsupported keyword, the query editor sends the following message to the destination:

```output
Ignoring command <ignored_command>
```

> [!CAUTION]  
> Because you don't start SQLCMD from the command line, there are some limitations when running Query Editor in SQLCMD mode. You can't pass in command-line parameters such as variables. Also, because the query editor can't respond to operating system prompts, you must be careful not to execute interactive statements.

## Color coding in SQLCMD scripts

When you enable SQLCMD scripting, scripts are color coded. The color coding for Transact-SQL keywords stays the same. SQLCMD commands appear with a shaded background.

## Examples

The following example uses a SQLCMD statement to create an output file named `testoutput.txt`. It runs two Transact-SQL `SELECT` statements and one operating system command that prints the current directory. The resulting file contains the message output from the `DIR` statement and the results output from the Transact-SQL statements.

```sql
:out C:\testoutput.txt
SELECT @@VERSION As 'Server Version';
!!DIR
!!:GO
SELECT @@SERVERNAME AS 'Server Name';
GO
```

## Related content

- [sqlcmd utility](/sql/tools/sqlcmd/sqlcmd-utility)
