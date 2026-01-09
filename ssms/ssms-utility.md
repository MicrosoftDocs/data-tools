---
title: SSMS Utility
description: Learn about the SSMS utility.
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/15/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL Server Management Studio [SQL Server], opening"
  - "command prompt utilities [SQL Server], sqlwb"
  - "sqlwb utility"
  - "Management Studio command line"
  - "opening SQL Server Management Studio"
---

# SSMS utility

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

The **ssms** utility opens SQL Server Management Studio. If specified, **ssms** also establishes a connection to a server, and opens queries, scripts, files, projects, and solutions.

You can specify files that contain queries, projects, or solutions. Files that contain queries are automatically connected to a server if connection information is provided and the file type is associated with that type of server. For instance, `.sql` files open a SQL Query Editor window in SQL Server Management Studio, and `.mdx` files open an MDX Query Editor window in SQL Server Management Studio. **SQL Server Solutions and Projects** open in SQL Server Management Studio.

> [!NOTE]  
> The **ssms** utility doesn't run queries. To run queries from the command line, use the **sqlcmd** utility.

## Syntax

```syntax
ssms
[ scriptfile ] [ projectfile ] [ solutionfile ]
[ -S servername ] [ -d databasename ] [ -G ] [ -U username ] [ -E ] [ -nosplash ] [ -log [ filename ] ? ] [ -? ]
```

## Arguments

#### *scriptfile*

Specifies one or more script files to open. The parameter must contain the full path to the files.

#### *projectfile*

Specifies a script project to open. The parameter must contain the full path to the script project file.

#### *solutionfile*

Specifies a solution to open. The parameter must contain the full path to the solution file.

#### [ -S *servername* ]

Server name

#### [ -d *databasename* ]

Database name

#### [ -G ]

Connect using Active Directory authentication. The type of connection is determined whether `-U` is included.

> [!NOTE]  
> **Active Directory - Universal with MFA support** isn't currently supported.

#### [ -U *username* ]

User name when connecting with SQL Authentication.

> [!NOTE]  
> `-P` was removed in SSMS version 18.0. Try to connect to the server once using the UI and save your password.

#### [ -E ]

Connect using Windows Authentication.

#### [ -nosplash ]

Prevents SQL Server Management Studio from displaying the splash screen graphic while opening. Use this option when connecting to the computer running SQL Server Management Studio over Terminal Services, on a connection with a limited bandwidth. This argument isn't case-sensitive and might appear before or after other arguments

#### [ -log* [ filename ] ?* ]

Logs SQL Server Management Studio activity to the specified file for troubleshooting

#### [ -? ]

Displays command-line help

## Remarks

All of the switches are optional and separated by a space except files, which are separated by commas. If you don't specify any switches, **ssms** opens SQL Server Management Studio as specified in the **Options** settings on the **Tools** menu. For example, if the **Environment/General** page **At startup** option specifies **Open new query window**, **ssms** opens with a blank Query Editor.

The `-log` switch must appear at the end of the command line, after all, other switches. The filename argument is optional. If a filename is specified, and the file doesn't exist, the file is created. If the file can't be created - for example, due to insufficient write access, the log is written to the nonlocalized `APPDATA` location instead (See the following example). If the filename argument isn't specified, two files are written to the current user's nonlocalized application data folder.

The nonlocalized application data folder for SQL Server can be found from the `APPDATA` environment variable. For example, for SQL Server 2012, the folder is `<system drive>:\Users\<username\>\AppData\Roaming\Microsoft\AppEnv\10.0\`. The two files are, by default, named `ActivityLog.xml` and `ActivityLog.xsl`. The former contains the activity log data, and the latter is an XML style sheet, which provides a more convenient way to view the XML file.

Use the following steps to view the log file in your default XML viewer, like Internet Explorer: Select **Start**, then select **Run...**, type `<system drive>:\Users\<username\>\AppData\Roaming\Microsoft\AppEnv\10.0\ActivityLog.xml` into the field provided, and then press Enter.

Files that contain queries prompt to be connected to a server if connection information is provided and the file type is associated with that type of server. For instance, `.sql` files open a SQL Query Editor window in SQL Server Management Studio, and `.mdx` files open an MDX Query Editor window in SQL Server Management Studio. **SQL Server Solutions and Projects** open in SQL Server Management Studio.

The following table maps server types to file extensions.

| Server type | Extension |
| --- | --- |
| SQL Server | `.sql` |
| SQL Server Analysis Services | `.mdx`, `.xmla` |

## Examples

The following script opens SQL Server Management Studio from a command prompt with the default settings:

```console
ssms
```

The following script opens SQL Server Management Studio from a command prompt using *Active Directory - Integrated*:

```console
ssms.exe -S servername.database.windows.net -G
```

The following script opens SQL Server Management Studio from a command prompt, with Windows Authentication, with the Code Editor set to the server `ACCTG` and the database [!INCLUDE [sssampledbobject-md](includes/sssampledbobject-md.md)], without showing the splash screen:

```console
ssms -E -S ACCTG -d AdventureWorks2022 -nosplash
```

The following script opens SQL Server Management Studio from a command prompt, and opens the MonthEndQuery script.

```console
ssms "C:\Documents and Settings\username\My Documents\SQL Server Management Studio Projects\FinanceScripts\FinanceScripts\MonthEndQuery.sql"
```

The following script opens SQL Server Management Studio from a command prompt, and opens the NewReportsProject project on the computer named `developer`:

```console
ssms "\\developer\fin\ReportProj\ReportProj\NewReportProj.ssmssqlproj"
```

The following script opens SQL Server Management Studio from a command prompt, and opens the MonthlyReports solution:

```console
ssms "C:\solutionsfolder\ReportProj\MonthlyReports.ssmssln"
```

## Related content

- [What is SQL Server Management Studio (SSMS)?](sql-server-management-studio-ssms.md)
