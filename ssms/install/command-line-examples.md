---
title: Command-Line Parameter Examples for SQL Server Management Studio Installation
description: Examples of using command-line parameters to install SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan, mbarickman
ms.date: 06/25/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
---
# Command-Line parameter examples for SQL Server Management Studio installation

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

There are numerous command-line parameters available for installing SQL Server Management Studio (SSMS). Included are several examples that can be customized to match your needs.

All commands require administrative elevation, and a User Account Control prompt is displayed if the process isn't started from an elevated prompt.

You can use the ^ character at the end of a command line to concatenate multiple lines into a single command. Alternatively, you can place these lines together onto a single row. In PowerShell, the equivalent is the backtick (`) character.

To execute commands in a non-interactive manner, you can use `--passive` or `--quiet`. For more information on these parameters, see [Use command-line parameters to install SQL Server Management Studio](command-line-parameters.md).

For lists of the workloads and components that you can install by using the command line, see [Workload and component IDs for SQL Server Management Studio](workload-component-ids.md).

## Install using --installPath and --add alongside the bootstrapper

Install a minimal instance of SSMS, with no interactive prompts, but progress displayed:

```cmd
vs_SSMS.exe --passive --norestart
```

Install SSMS silently, with the Italian language pack, returning only when the product is installed:

```cmd
vs_SSMS.exe --addProductLang it-it --quiet --wait
```

## Install workloads

Install SSMS with Git integration, with the user interface displayed in a non-interactive manner:

```cmd
vs_SSMS.exe --add Microsoft.SqlServer.Workload.SSMS.CodeTools --includeRecommended --passive
```

Install SSMS with all components in the Business Intelligence workload, with the user interface displayed in a non-interactive manner:

```cmd
vs_SSMS.exe --add Microsoft.SqlServer.Workload.SSMS.BI --includeRecommended --passive --norestart
```

## Update

Update an SSMS installation via the command line quietly

```cmd
vs_SSMS.exe update --noWeb --quiet --wait --norestart
```

## Use --layout to create a network layout or local cache

Create a layout that includes SSMS and Integration Services in SSMS, and the English language pack:

```cmd
vs_SSMS.exe --layout "C:\SSMS_Layout" --lang en-US --add Microsoft.SSMS.Component.IS --includeRecommended
```

Create a layout with two workloads and one optional component in three languages:

```cmd
vs_SSMS.exe --layout "C:\SSMS_Layout" --lang en-US --add Microsoft.SqlServer.Workload.SSMS.HybridAndMigration --add Microsoft.SqlServer.Workload.SSMS.CodeTools --add Microsoft.Component.HelpViewer --lang en-US de-DE ja-JP
```

To create a complete local layout for SQL Server Management Studio and all languages, run:

```cmd
vs_SSMS.exe --layout C:\SSMS_Layout --all
```

To create a local layout for SQL Server Management Studio that limits the components to only the Integration Services and Reporting Services component, run:

```cmd
vs_SSMS.exe --layout C:\SSMS_Layout --add Microsoft.SSMS.Component.IS --add Microsoft.SSMS.Component.RS
```

To create a local layout for SQL Server Management Studio that limits the components to only the offline help content, run:

```cmd
vs_SSMS.exe --layout C:\SSMS_Layout --add Microsoft.Component.HelpViewer
```


## Install a layout

Once a layout is created, it can be copied to an offline machine for installation. Components identified will need to be lincluded in the offline layout already (see 'complete local layout' mentioned in a prior example):

```cmd
vs_SSMS.exe --layout "C:\SSMS_Layout" --lang en-US --add Microsoft.SSMS.Component.IS --includeRecommended
```

To install SSMS with Integration Services support from the layout, run:

```cmd
vs_SSMS.exe --noWeb --noUpdateInstaller --add Microsoft.SSMS.Component.IS --includeRecommended --passive
```

To install SSMS with Integration Services and Reporting Services support, run:

```cmd
vs_SSMS.exe --noWeb --noUpdateInstaller --add Microsoft.SSMS.Component.IS --add Microsoft.SSMS.Component.RS --includeRecommended --passive
```

## Modifying an existing installation

To update SSMS using an offline layout to ensure desired components are included in the installation, and then modify SSMS to add Analysis Services, Integration Services, and Reporting Services components, run:

```cmd
cd C:\SSMSLayout
vs_SSMS.exe update --noWeb --quiet --wait --norestart
vs_SSMS.exe modify --noWeb --productID Microsoft.VisualStudio.Product.SSMS --channelID SSMS.21.SSMS.Release --add Microsoft.SSMS.Component.AS --add Microsoft.SSMS.Component.IS --add Microsoft.SSMS.Component.RS --quiet --norestart
```


## Related content

- [Create an offline installation of SQL Server Management Studio](create-offline.md)
- [Workload and component IDs for SQL Server Management Studio](workload-component-ids.md)
