---
title: Uninstall or Remove SQL Server Management Studio
description: Learn how to repair an installation of SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 05/19/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---
# Uninstall or remove SQL Server Management Studio

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

This article walks you through uninstalling [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)].

> [!TIP]  
> If you're having trouble with your instance of SQL Server Management Studio (SSMS), try the [repair](repair.md) option.
>
> To change the location for some of your SSMS files, it's possible to do so without uninstalling your current instance as described in Select the installation locations.

## Uninstall by using Visual Studio Installer

You can use the Visual Studio Installer can uninstall versions of SSMS.

1. Find the **Visual Studio Installer** on your computer.

1. In the Windows Start menu, you can search for installer.

   > [!NOTE]  
   > You can also find the Visual Studio Installer in the following location:
   > 
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\setup.exe`

   You might have to update the installer before you continue. If so, follow the prompts.

1. In the installer, look for the version of SSMS that you installed. Next, choose **More**, and then choose **Uninstall**.

1. Select **OK** to confirm your choice.

If you change your mind later and want to reinstall SSMS, start the Visual Studio Installer again, choose the **Available** tab, choose SQL Server Management Studio, and then select **Install**.

## Uninstall SSMS

To remove all installations of SSMS, and the Visual Studio Installer from your machine, uninstall it from **Installed apps**.

1. In Windows 10 and later versions, type **Add or remove programs** in the Windows search box.
1. Find **SQL Server Management Studio**.
1. Choose **Uninstall**.
1. Repeat these steps for all versions of SSMS installed on the machine.
1. Then, find **Microsoft Visual Studio Installer**.
1. Choose **Uninstall**.

## Remove all with InstallCleanup.exe

If you experience a catastrophic error and *can't repair or uninstall SSMS*, you can run the `InstallCleanup.exe` tool to remove installation files and product information for all installed instances of SSMS and Visual Studio.

> [!WARNING]  
> Use the InstallCleanup tool only *as a last resort* if repair or uninstall fail. This tool might uninstall features from other Visual Studio installations or other products, which you then might need to repair or reinstall.

Here's how to run the `InstallCleanup.exe` tool:

1. Close the Visual Studio Installer.

1. Open an administrator command prompt. To open an administrator command prompt, follow these steps:

   1. Type `cmd` in the Windows search box.
   1. Right-click **Command Prompt**, and then choose **Run as administrator**.

1. Enter the full path of the `InstallCleanup.exe` tool and add the command-line parameters that you prefer. By default, the path of the tool is as follows. The double quotes enclose a command that contains spaces:

   ```cmd
   "C:\Program Files (x86)\Microsoft Visual Studio\Installer\InstallCleanup.exe"
   ```

   > [!NOTE]  
   > The Visual Studio Installer directory is always located at `%ProgramFiles(x86)%\Microsoft Visual Studio`. If you can't find `InstallCleanup.exe` there, follow the instructions to [install SSMS](install.md). Then, when the workload selection screen is displayed, close the window and follow the steps in this section again.

   These options are available:

   | Parameter | Behavior |
   | --- | --- |
   | `-i [version]` | If you don't specify a value, uses the default version. Removes only the main installation directory and product information. Use this parameter if you intend to reinstall the same version of SSMS. If you specify a `[version]` value, the tool removes only products with a version that start with this string value. For example, use the value `-i 21` with to remove all products of version 21. |
   | `-f` | Removes the main installation directory, product information, and most other features installed outside the installation directory that might also be shared with other Visual Studio installations or other products. Use this parameter if you intend to remove SSMS and Visual Studio without reinstalling it later. |

[!INCLUDE [support](../includes/support.md)]

## Related content

- [Modify SQL Server Management Studio workloads, components, and language packs](modify.md)
- [Update SQL Server Management Studio](update.md)
- [Install SQL Server Management Studio](install.md)
