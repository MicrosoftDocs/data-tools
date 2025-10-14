---
title: Modify SQL Server Management Studio
description: Learn how to modify the SQL Server Management Studio (SSMS) installation.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 05/19/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---
# Modify SQL Server Management Studio workloads, components, and language packs

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

It's easy to modify [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] so that it includes only what you want. To do so, open the Visual Studio Installer, and then add or remove workloads, components, and language packs. This article walks you through the process.

## Prerequisites

- By default, to install, update, or modify SQL Server Management Studio (SSMS), the account performing the update must have administrative permissions on the machine. It must also have permissions to the source where the product updates are located (either the internet or an internal location). If you're logged in as a typical user and try to perform one of these commands, you get a User Account Control notice prompting you for admin credentials. An admin can delegate control of modifying SSMS to standard users by configuring the [AllowStandardUserControl policy](/visualstudio/install/configure-policies-for-enterprise-deployments#controlling-installation-download-and-update-behavior). For more information, see [User Permissions and Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).

- The following procedures assume you have an internet connection. For information about how to modify a previously created [offline installation](create-offline.md) of SSMS, see:

  - [Update a network-based installation of SSMS](/visualstudio/install/update-a-network-installation-of-visual-studio)
  - [Control updates to network-based SSMS deployments](/visualstudio/install/controlling-updates-to-visual-studio-deployments)

## Open the Visual Studio Installer to modify your installation

To modify your SSMS installation, you need to open the Visual Studio Installer, and then select an SSMS installation to modify.

1. There are many ways to open the Visual Studio Installer:

   - On the Windows Start menu, you can search for "installer" and then select **Visual Studio Installer** from the results.

   - Run the **Visual Studio Installer** executable file, which is located at `C:\Program Files (x86)\Microsoft Visual Studio\Installer\setup.exe`.

   You might be prompted to update the Visual Studio Installer before continuing. If you are, follow the prompts.

In the Visual Studio Installer, look for the installation of SSMS that you want to modify and then select **Modify**.

## Change workloads or individual components

Workloads group components that are commonly used together. Use workloads to modify SSMS so that it supports the work you want to do.

1. In the Visual Studio Installer, on the **Workloads** tab, select the workloads that you want.

1. To add individual components, on the **Individual components** tab, select the individual components that you want.

1. You can select the default **Install while downloading** or **Download all, then install**.

1. Select **Modify**.

1. After the modified workloads or components are installed, select **Launch** in the Visual Studio Installer to open SQL Server Management Studio.

You can also use a [configuration file to modify an existing installation to add or remove components](/visualstudio/install/import-export-installation-configurations#programmatically-use-a-configuration-file-to-add-components-to-an-existing-installation). For more information, see [Import or export installation configurations](/visualstudio/install/import-export-installation-configurations).

## Modify language packs

The Visual Studio Installer selects a default language pack for SSMS that matches the language of your operating system. You can change the default language at any time.

To change the default language:

1. Select the **Language packs** tab in the Visual Studio Installer.
1. Select the language you prefer.
1. Follow the prompts.

[!INCLUDE [support](../includes/support.md)]

## Related content

- [Update SQL Server Management Studio](update.md)
- [Uninstall or remove SQL Server Management Studio](uninstall.md)
- [Repair installation for SQL Server Management Studio](repair.md)
