---
title: Command-Line Parameter Examples for SQL Server Management Studio Installation
description: Examples of using command-line parameters to install SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, mbarickman
ms.date: 11/11/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
---
# Command-line parameter examples for SQL Server Management Studio installation

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

There are numerous command-line parameters available for installing SQL Server Management Studio (SSMS). Included are several examples that can be customized to match your needs.

All commands require administrative elevation, and a User Account Control prompt is displayed if the process isn't started from an elevated prompt.

You can use the ^ character at the end of a command line to concatenate multiple lines into a single command. Alternatively, you can place these lines together onto a single row. In PowerShell, the equivalent is the backtick (`) character.

To execute commands in a non-interactive manner, you can use `--passive` or `--quiet`. For more information on these parameters, see [Use command-line parameters to install SQL Server Management Studio](command-line-parameters.md).

For lists of the workloads and components that you can install by using the command line, see [Workload and component IDs for SQL Server Management Studio](workload-component-ids.md).

## Install using `--installPath` and `--add` alongside the bootstrapper

Install a minimal instance of SSMS, with no interactive prompts, but progress displayed:

```console
vs_SSMS.exe --installPath C:\SSMS22 --passive --norestart
```

Install SSMS silently, with the Italian language pack, returning only when the product is installed:

```console
vs_SSMS.exe --installPath C:\SSMS22 --addProductLang it-it --quiet --wait
```

## Install workloads

Install SSMS with Git integration, with the user interface displayed in a non-interactive manner:

```console
vs_SSMS.exe --add Microsoft.SqlServer.Workload.SSMS.CodeTools --includeRecommended --passive
```

Install SSMS with all components in the Business Intelligence workload, with the user interface displayed in a non-interactive manner:

```console
vs_SSMS.exe --add Microsoft.SqlServer.Workload.SSMS.BI --includeRecommended --passive --norestart
```

## Update

Update an SSMS installation via the command line with progress displayed and no interactive prompts. You can't initiate the installer programmatically from the same folder that the installer resides in.

```console
vs_SSMS.exe update --passive --norestart --installPath "C:\SSMS22"
```

Update an SSMS installation via the command line quietly:

```console
vs_SSMS.exe update --noWeb --quiet --wait --norestart
```

## Use `--layout` to create a network layout or local cache

Create a layout that includes SSMS and Copilot in SSMS, and the English language pack:

```console
vs_SSMS.exe --layout C:\SSMS_Layout --lang en-US --add Microsoft.SqlServer.Workload.SSMS.AI --includeRecommended
```

Create a layout that includes SSMS and Integration Services in SSMS, and the English language pack:

```console
vs_SSMS.exe --layout C:\SSMS_Layout --lang en-US --add Microsoft.SSMS.Component.IS --includeRecommended
```

Create a layout with two workloads and one optional component in three languages:

```console
vs_SSMS.exe --layout C:\SSMS_Layout --lang en-US --add Microsoft.SqlServer.Workload.SSMS.HybridAndMigration --add Microsoft.SqlServer.Workload.SSMS.CodeTools --add Microsoft.Component.HelpViewer --lang en-US de-DE ja-JP
```

To create a complete local layout for SQL Server Management Studio and all languages, run:

```console
vs_SSMS.exe --layout C:\SSMS_Layout --all
```

To create a local layout for SQL Server Management Studio that limits the components to only the Integration Services and Reporting Services component, run:

```console
vs_SSMS.exe --layout C:\SSMS_Layout --add Microsoft.SSMS.Component.IS --add Microsoft.SSMS.Component.RS
```

To create a local layout for SQL Server Management Studio that limits the components to only the offline help content, run:

```console
vs_SSMS.exe --layout C:\SSMS_Layout --add Microsoft.Component.HelpViewer
```

## Install a layout

Once a layout is created, it can be copied to an offline machine for installation. To install specific components, those components must be included in the offline layout already. For more information, see the [complete local layout](#use---layout-to-create-a-network-layout-or-local-cache) example.

Make sure you're in the folder where the layout was saved. In these examples, it's `C:\SSMS_Layout`.

```console
C:\SSMS_Layout\vs_SSMS.exe --lang en-US --add Microsoft.SqlServer.Workload.SSMS.AI --includeRecommended
```

To install SSMS with Integration Services support from the layout, run:

```console
C:\SSMS_Layout\vs_SSMS.exe --noWeb --noUpdateInstaller --add Microsoft.SSMS.Component.IS --includeRecommended --passive
```

To install SSMS with Integration Services and Reporting Services support, run:

```console
C:\SSMS_Layout\vs_SSMS.exe --noWeb --noUpdateInstaller --add Microsoft.SSMS.Component.IS --add Microsoft.SSMS.Component.RS --includeRecommended --passive
```

## Update an existing installation using a layout

To update SSMS to the latest release, create a layout with the same components as the original installation.

1. Change to the layout folder:

   ```console
   cd C:\SSMS_Layout
   ```

1. Update to the latest released version:

   ```console
   vs_SSMS.exe update --noWeb
   ```

## Modify an existing installation using a layout

To update SSMS to include other components, create a layout with your desired components, using the previous examples.

1. Change to the layout folder:

   ```console
   cd C:\SSMS_Layout
   ```

1. Update to the latest released version:

   ```console
   vs_SSMS.exe update --noWeb --quiet --wait --norestart
   ```

1. Modify SSMS to add Analysis Services, Integration Services, and Reporting Services components, using the offline layout that includes these components, run:

   ```console
   vs_SSMS.exe modify --noWeb --productID Microsoft.VisualStudio.Product.SSMS --channelID SSMS.22.SSMS.Release --add Microsoft.SSMS.Component.AS --add Microsoft.SSMS.Component.IS --add Microsoft.SSMS.Component.RS --quiet --norestart
   ```

## Uninstall an existing installation

To uninstall the SSMS 22 GA release from a workstation, use the following example.

1. Change to the Visual Studio Installer folder:

   ```console
   cd "C:\Program Files (x86)\Microsoft Visual Studio\Installer"
   ```

1. Remove the SSMS 22 GA (Release) version:

   ```console
    setup.exe uninstall --passive --productId Microsoft.VisualStudio.Product.Ssms --channelId SSMS.22.SSMS.Release --noweb
   ```

## Related content

- [Create an offline installation of SQL Server Management Studio](create-offline.md)
- [Workload and component IDs for SQL Server Management Studio](workload-component-ids.md)
