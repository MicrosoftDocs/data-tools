---
title: Install SQL Server Management Studio 21 Preview
description: Learn how to use the Visual Studio installer to install SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan
ms.date: 11/12/2024
ms.service: sql-server-management-studio
ms.topic: how-to
---
# Install SQL Server Management Studio 21 Preview

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

Welcome to [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)]. In this version, it's easy to choose and install only the features you need, using the Visual Studio Installer.

> [!NOTE]  
> If you need to programmatically install SQL Server Management Studio, see [Use command-line parameters](/visualstudio/install/use-command-line-parameters-to-install-visual-studio).

Want to know more about what else is new in this version? See the [release notes](../ssms-21/release-notes-21.md).

You can download and install a specific version from the [release history](../ssms-21/release-history.md) page.

Ready to install? This article walks you through it, step-by-step.

## Step 1 - Make sure your computer is ready for SQL Server Management Studio 21 Preview

Before you begin installing SQL Server Management Studio (SSMS):

- Check the [system requirements](../ssms-21/system-requirements.md). These requirements help you know whether your computer supports [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)].

- Make sure that the user who performs the initial installation has administrator permissions on the machine. For more information, see [User permissions and SQL Server Management Studio 21 Preview](/visualstudio/ide/user-permissions-and-visual-studio).

- Apply the latest Windows updates. These updates ensure that your computer has both the latest security updates and the required system components for SSMS.

- Restart. Restarting ensures that any pending installs or updates don't hinder your SSMS install.

- Free up space. Remove unneeded files and applications from your system drive by, for example, running the Disk Cleanup application.

You can install [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] side-by-side with other versions. For more information, see [Install SQL Server Management Studio versions side-by-side](side-by-side.md).

## Step 2 - Determine which version of SQL Server Management Studio 21 to install

Decide which version of SSMS to install. The most common options are:

- The latest release of [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] that is hosted on Microsoft servers. To install this version, select the following link. The installer downloads a small *bootstrapper* to your *Downloads* folder.

[Download SSMS 21 Preview](https://aka.ms/ssms/21/preview/vs_SSMS.exe)

- If you already have SQL Server Management Studio 21 installed, you can [install another version alongside it](side-by-side.md).

- You can download a bootstrapper or installer for a specific version from the [Release history](../ssms-21/release-history.md) page and use it to install another version of SSMS.

## Step 3 - Initiate the installation

If you downloaded a bootstrapper file, you can use it to install SSMS. You need administrator permissions. The bootstrapper installs the latest version of the Visual Studio Installer. The installer is a separate program that provides everything you need to both install and customize SSMS.

1. From your *Downloads* folder, double-click the bootstrapper named `vs_ssms.exe` to start the installation.

1. If you receive a User Account Control notice, choose **Yes**. The dialog box asks you to acknowledge the [Microsoft Privacy Statement](https://www.microsoft.com/privacy/privacystatement) and [Microsoft Software License Terms](/legal/sql/ssms/sql-server-management-studio-license-terms). Choose **Continue**.

The Visual Studio Installer opens. In addition to SQL Server Management Studio, you can also install any product that [Visual Studio Installer's](/visualstudio/install/install-visual-studio-versions-side-by-side#install-different-editions-of-the-same-major-visual-studio-version-side-by-side) **Available** tab offers.

## Step 4 - Customize installation (optional)

After you install the Visual Studio Installer, you can use it to customize your installation SQL Server Management Studio by selecting different options on the tabs of the installer. Here's how.

- SQL Server Management Studio 21 Preview 1 doesn't have any feature sets, or *workloads* available to install on the **Workloads** tab.
- You can add individual components to your installation from the **Individual components** tab. Select the components that you want to install.

## Step 5 - Install language packs (optional)

By default, the installer program tries to match the language of the operating system when it runs for the first time. To install SSMS in a language of your choosing, choose the **Language packs** tab from the Visual Studio Installer, and then follow the prompts.

### Change the installer language from the command line

Another way that you can change the default language is by running the installer from the command line. For example, you can force the installer to run in English by using the following command:

```cmd
vs_ssms.exe --locale en-US
```

The installer remembers this setting when you run it again. The installer supports these language locales: `zh-cn`, `zh-tw`, `cs-cz`, `en-us`, `es-es`, `fr-fr`, `de-de`, `it-it`, `ja-jp`, `ko-kr`, `pl-pl`, `pt-br`, `ru-ru`, and `tr-tr`.

## Step 6 - Select the installation location (optional)

You can reduce the installation footprint of SSMS on your system drive. For more information, see [Select installation locations for SQL Server Management Studio 21 Preview](select-install-location.md).

You can select a different drive for **SQL Server Management Studio** or **Download cache** only when you first install SSMS. If you already installed it and want to change drives, you must uninstall SSMS and then reinstall it.

If SSMS or Visual Studio is already installed on your computer, you can't change the Shared components, tools, and SDKs path. It appears greyed out. This location is shared by all installations of SSMS and Visual Studio.

## Step 7 - Sign in to your account (optional)

While you don't have to sign in, there are many advantages to doing so, such as synchronizing your settings across devices. See [Sign in or switch user accounts in SQL Server Management Studio 21 Preview](../ssms-21/sign-in.md).

[!INCLUDE [support](../includes/support.md)]

## Related content

- [Update SQL Server Management Studio 21 Preview](update.md)
- [Modify SQL Server Management Studio 21 Preview components and language packs](modify.md)
- [Uninstall or remove SQL Server Management Studio 21 Preview](uninstall.md)
- [Create an offline installation of SQL Server Management Studio 21 Preview](create-offline.md)
- [Use command-line parameters to install SQL Server Management Studio 21 Preview](command-line-parameters.md)
