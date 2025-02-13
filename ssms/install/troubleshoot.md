---
title: Troubleshoot Installation and Upgrade Issues for SQL Server Management Studio
description: Learn how to troubleshoot issues with SQL Server Management Studio (SSMS) installation and upgrades.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 05/19/2025
ms.service: sql-server-management-studio
ms.topic: troubleshooting-general
ms.collection:
  - data-tools
---
# Troubleshoot installation and upgrade issues for SQL Server Management Studio

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

This troubleshooting guide includes step-by-step instructions to resolve common issues with SQL Server Management Studio (SSMS) installation and upgrade.

## Online installations or updates

Try the following possible resolutions that apply to a typical online installation issue in order.

#### 1. Check whether the problem is a known issue

The first thing to check is whether or not the issue you're encountering is a known issue with the Visual Studio Installer that Microsoft is working on fixing.

To see if there's a workaround for your problem, check [Known issues in SQL Server Management Studio](../known-issues.md).

#### 2. Try repairing SSMS

Try to [repair your installation](repair.md). It might fix many common update issues.

#### 3. Delete the installer folder (update issues)

If you encounter an issue when updating, try deleting the Visual Studio Installer folder, and then rerunning the installation bootstrapper. Doing so reinstalls the Visual Studio Installer files and resets the installation metadata.

1. Close the Visual Studio Installer.

1. Delete the Visual Studio Installer folder. Typically, the folder path is `C:\Program Files (x86)\Microsoft Visual Studio\Installer`.

1. Run the SSMS bootstrapper. You might find the bootstrapper in your *Downloads* folder with a file name `vs_SSMS.exe`. Or, you can download the bootstrapper from the [installation page](install.md) for SSMS. Then, run the executable to reset your installation metadata.

1. Try to install or update SSMS again. If the installer continues to fail, report the problem to support.

#### 4. Report the problem to support

In some situations, when there are corrupted files, issues might require case-by-case troubleshooting.

Follow these steps to submit the problem to Microsoft Support:

1. Collect your setup logs. See [Collect installation logs for Microsoft Support](#collect-installation-logs-for-microsoft-support) for details.

1. Open the Visual Studio Installer, and then choose **Report a problem** to open the Feedback tool.

1. This step opens the Developer Community site, and requires you to sign in.

1. Give your problem report a title, and provide the relevant details. See [Collect installation logs for Microsoft Support](#collect-installation-logs-for-microsoft-support) to capture the installation logs for the Visual Studio Installer, and add them as an attachment to the problem report.

1. Choose **Submit**.

#### 5. Remove all SSMS installation files

As a last resort, you can remove all SSMS installation files and product information:

1. Remove all with [InstallCleanup.exe](uninstall.md#remove-all-with-installcleanupexe).

1. Rerun the SSMS bootstrapper. You might find the bootstrapper in your Downloads folder with a file name `vs_SSMS.exe`. Or, you can download the bootstrapper from the [installation page](install.md).

1. Try to reinstall SSMS.

## Network layout or offline installations

To resolve issues with a [network installation](/visualstudio/install/create-a-network-installation-of-visual-studio), see [Error Codes](/visualstudio/install/create-a-network-installation-of-visual-studio#error-codes) or [Troubleshoot network-related errors when you install or use Visual Studio](/troubleshoot/developer/visualstudio/installation/troubleshoot-network-related-errors).

## Collect installation logs for Microsoft Support

If you contact Microsoft Support, you might be asked to collect setup logs by using the [Microsoft Visual Studio and .NET Framework log collection tool](https://aka.ms/vscollect). The log collection tool collects setup logs from all components installed by SSMS and Visual Studio, including .NET Framework. The collection tool also collects computer information, a Windows Installer inventory, and Windows event log information for the Visual Studio Installer, Windows Installer, and System Restore.

To collect the logs, follow these steps:

1. Download the tool from <https://aka.ms/vscollect>.

1. Open an administrative command prompt.

1. Run `collect.exe` in the folder where you saved the tool.

The tool must be run under the same user account that the failed installation was run under. If you're running the tool from a different user account, set the `-user:<name>` option to specify the user account under which the failed installation was run. Run `collect.exe -?` from an administrator command prompt for more options and usage information.

The tool generates a `vslogs.zip` file in your `%TEMP%` folder, typically at `C:\Users\YourName\AppData\Local\Temp\vslogs.zip`.

Report product issues to us using the [Report a Problem](/visualstudio/ide/how-to-report-a-problem-with-visual-studio) tool that appears both in the Visual Studio Installer and in the SSMS IDE.
