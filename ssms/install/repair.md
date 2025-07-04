---
title: Repair SQL Server Management Studio
description: Learn how to uninstall SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan
ms.date: 05/19/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---
# Repair installation for SQL Server Management Studio

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

Your SQL Server Management Studio (SSMS) installation could become damaged or corrupted. A repair is useful for fixing a wide variety of install-time issues, including update issues.

Repairing SSMS resets its environment. Repairing removes local customizations such as extensions installed without elevation, user settings, and profiles. It restores your synchronized settings such as themes, colors, and key bindings.

## When to use repair

Use repair if you're having issues with:

- Installation payload, which can happen when writing a file to disk is unsuccessful and the file gets corrupted. Repair can reacquire needed files.

- Client-side download, assuming that you fixed any internet connection or proxy issues.

- Updating SQL Server Management Studio. Repair fixes many common update issues.

> [!TIP]  
> An unstable internet connection or an issue in a Windows service, like Windows Installer, can cause install issues. In those scenarios, repair might also be affected. To check for underlying issues, review the error report generated by the Visual Studio Installer.

Repairing SSMS resets user settings and reinstalls your existing assemblies. If you experience a product issue and repair doesn't fix it, see [How to report a problem with Visual Studio Installer](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

## How to repair

To repair your installation, follow these steps.

1. Find the **Visual Studio Installer** on your computer.

1. In the Windows Start menu, you can search for installer, and then select **Visual Studio Installer** from the results.

   > [!NOTE]  
   > You can also find the Visual Studio Installer in the following location:
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\setup.exe`

   You might be prompted to update the Visual Studio Installer before you continue. If so, follow the prompts.

1. In the Visual Studio Installer, look for the installation of SQL Server Management Studio (SSMS) that you want to repair. Then choose **Repair** from the More dropdown list menu.

   The **Repair** option appears only for installed instances of SSMS. If you don't see the **Repair** option, check whether you selected **More** in a version that appears in the Visual Studio Installer as **Available** rather than **Installed**.

[!INCLUDE [support](../includes/support.md)]

## Related content

- [Install SQL Server Management Studio](install.md)
- [Update SQL Server Management Studio](update.md)
- [Uninstall or remove SQL Server Management Studio](uninstall.md)
- [Troubleshoot installation and upgrade issues for SQL Server Management Studio](troubleshoot.md)
