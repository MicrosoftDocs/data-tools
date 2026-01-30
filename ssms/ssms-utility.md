---
title: Use Command-Line Parameters to Open SQL Server Management Studio
description: Learn about opening SSMS from a command line.
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/30/2026
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

# Open SQL Server Management Studio from a command prompt

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

SQL Server Management Studio (SSMS) can be opened from a command prompt. If you specify connection information, SSMS connects to a server. You can also specify a file for SSMS to open.

You can specify files that contain queries, projects, or solutions. If you provide connection information, query files automatically connect to a server. The file type determines the associated server type. For example, `.sql` files open a Query Editor window, and `.mdx` files open an MDX Query Editor window. Solution and project files open in Solution Explorer.

> [!NOTE]  
> The command prompt doesn't run queries. To run queries from the command line, use the **sqlcmd** utility.

## Syntax

```syntax
ssms
[ scriptfile ] [ projectfile ] [ solutionfile ]
[ -S servername ] [ -d databasename ] [ -G ] [ -U username ] [ -E ] [ -nosplash ] [ -log [ filename ] ? ] [ -? ]
```

| **Command** | **Description** |
| --- | --- |
| `-?` | Displays command-line help. |
| `-S <servername>` | Server name. |
| `-d <databasename>` | Database name. |
| `-U <username>` | User name when connecting with SQL Authentication. |
| `-E` | Connect using Windows Authentication. |
| `-A` | Connect using Active Directory authentication such as `ActiveDirectoryInteractive`. For a full list of values, see Microsoft.Data.SqlClient's [SqlAuthenticationMethodEnum](/dotnet/api/microsoft.data.sqlclient.sqlauthenticationmethod). The type of connection is determined by whether `-U` is included. |
| `-N <option>` | Specifies the encryption option for the connection: **Optional**, **Mandatory** (default), or **Strict**. |
| `-C` | Specifies that the connection trusts the server certificate without validation. |
| `-i <hostname>` | Specifies a different, expected Common Name (CN) or Subject Alternative Name (SAN) in the server certificate to use during server certificate validation. |
| `-nosplash` | Prevents SSMS from displaying the splash screen graphic while opening. Use this option when connecting to the computer running SSMS over Terminal Services, on a connection with limited bandwidth. This argument isn't case-sensitive and can appear before or after other arguments. |
| `-log <file>*` | Logs SSMS activity to the specified file for troubleshooting. This argument must be the *last* switch. |
| `scriptfile` | Specifies one or more script files to open. The parameter must contain the full path to the files. |
| `projectfile` | Specifies a script project to open. The parameter must contain the full path to the script project file. |
| `solutionfile` | Specifies a solution to open. The parameter must contain the full path to the solution file. |

> [!NOTE]
> The `-P` parameter was removed in SSMS version 18.0. Connect to the server with your username and password. You can save your password by enabling **Remember Password** in the connection dialog. This step bypasses entering the password manually.

## Remarks

All of the switches are optional. The switches are separated by a space, except for files, which are separated by commas. If you don't specify any switches, `ssms` opens SQL Server Management Studio as specified in **Tools** > **Options** > **Environment** > **Startup**. For example, if the **At startup** option specifies **Open new query window**, SSMS opens with a blank Query Editor.

If you provide connection information, files that contain queries prompt to be connected to a server. The file type is associated with that type of server. For instance, `.sql` files open a SQL Query Editor window, `.mdx` files open an MDX Query Editor window, and Solutions and Projects open in Solution Explorer.

The following table maps server types to file extensions.

| Server type | Extension |
| --- | --- |
| SQL Server | `.sql` |
| SQL Server Analysis Services | `.mdx`, `.xmla` |
| SQL Server Solution | `.slnx` |
| SQL Server Project | `.ssmssqlproj` |

The `-log` switch must appear at the end of the command line, after all other switches. The filename argument is optional. If you specify a filename and the file doesn't exist, the file is created. If the file can't be created (for example, due to insufficient write access), the log is written to the nonlocalized `APPDATA` location instead. If you don't specify the filename argument, two files are written to the current user's nonlocalized application data folder.

You can find the nonlocalized application data folder for SQL Server from the `APPDATA` environment variable. In SSMS 22 for example, the folder is `%APPDATA%\Microsoft\SSMS\<installid>` and the file is named `ActivityLog.xml`.

## Examples

These examples assume that the location of the SSMS installation is in your default path, or that you navigate to that location within Command Prompt. For SSMS 22, the default installation location is `C:\Program Files\Microsoft SQL Server Management Studio 22\Release\Common7\IDE`.

The following script opens SSMS from a command prompt with the default settings:

```console
ssms
```

The following script opens SSMS from a command prompt using *Active Directory Interactive*:

```console
ssms.exe -S servername.database.windows.net -U username -A ActiveDirectoryInteractive
```

The following script opens SSMS from a command prompt, connecting to the server `ACCTG` and the database [!INCLUDE [sssampledbobject-md](includes/sssampledbobject-md.md)] with Windows Authentication and trusting the connection, without showing the splash screen:

```console
ssms -S ACCTG -d AdventureWorks2025 -A ActiveDirectoryIntegrated -C -nosplash
```

The following script opens SSMS from a command prompt, and opens the MonthEndQuery script.

```console
ssms "C:\FinanceScripts\MonthEndQuery.sql"
```

The following script opens SSMS from a command prompt, and opens the NewReportsProject project:

```console
ssms "C:\Projects\Reports\NewReportsProject.ssmssqlproj"
```

The following script opens SSMS from a command prompt, and opens the MonthlyReports solution:

```console
ssms "C:\Solutions\Reports\MonthlyReports.ssmssln"
```

> [!NOTE]  
> If you don't see the Project or Solution when SSMS opens, go to **View** > **Solution Explorer**.

## Related content

- [What is SQL Server Management Studio (SSMS)?](sql-server-management-studio-ssms.md)
- [Use command-line parameters to install SQL Server Management Studio](install/command-line-parameters.md)
- [Command-line parameter examples for SQL Server Management Studio installation](install/command-line-examples.md)
