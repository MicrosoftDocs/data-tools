---
title: Install SQL Server Management Studio
description: Learn how to use the Visual Studio installer to install SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 08/21/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---
# Install SQL Server Management Studio

[!INCLUDE [sql-asdb-asdbmi-asa-fabricsqldb](../includes/applies-to-version/sql-asdb-asdbmi-asa-fabricsqldb.md)]

This article describes how to install SQL Server Management Studio (SSMS).

| Key information | Action required |
| --- | --- |
| **SSMS 21 is installed with the Visual Studio Installer** | The **Download SSMS 21** link downloads a stub installer (`vs_SSMS.exe`) that opens **Visual Studio Installer** to install SSMS. There's no standalone MSI. |
| **How&nbsp;to&nbsp;install&nbsp;SSMS** | [Download SSMS 21](https://aka.ms/ssms/21/release/vs_SSMS.exe), run `vs_SSMS.exe`, pick any optional workloads/components, then select **Install**. |
| **Use the Visual Studio Installer to update SSMS 21** | To update SSMS 21, follow the instructions in [Update SQL Server Management Studio](update.md). |
| **Offline or enterprise deployment** | To create an offline layout for disconnected or managed installs, see [Create an offline installation of SQL Server Management Studio](create-offline.md). |
| **Database&nbsp;Engine&nbsp;compatibility** | SSMS 21 works with [!INCLUDE [sssql14-md](../includes/sssql14-md.md)] and later versions. If you need to manage older versions, see the [Release history](../release-history.md). SSMS 21 also works with [!INCLUDE [ssazure-sqldb](../includes/ssazure-sqldb.md)], [!INCLUDE [ssazuremi-md](../../azure-data-studio/includes/ssazuremi-md.md)], [!INCLUDE [ssazuresynapse-md](../includes/ssazuresynapse-md.md)], and [!INCLUDE [fabric-sqldb](../includes/fabric-sqldb.md)]. |

For more information, see [SQL Server Management Studio 21 Frequently Asked Questions (FAQ)](../faq.yml).

Find out what's new in this version in the [release notes](../release-notes-21.md).

Download and install a specific version from the [release history](../release-history.md) page.

Programmatically install SQL Server Management Studio with [command-line parameters](/visualstudio/install/use-command-line-parameters-to-install-visual-studio).

Ready to install? This article walks you through it, step-by-step.

## Step 1 - Make sure your computer is ready for SQL Server Management Studio

Before you begin installing SQL Server Management Studio (SSMS):

- Check the [system requirements](../system-requirements.md). These requirements help you determine whether your computer supports [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)].

- Make sure that the user who performs the initial installation has administrator permissions on the machine. For more information, see [User permissions and Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).

- Apply the latest Windows updates. These updates ensure that your computer has both the latest security updates and the required system components for SSMS.

- Restart. Restarting ensures that any pending installs or updates don't hinder your SSMS install.

- Free up space. Remove unneeded files and applications from your system drive by, for example, running the Disk Cleanup application.

You can install [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] side-by-side with other versions. For more information, see [Install SQL Server Management Studio versions side-by-side](side-by-side.md).

## Step 2 - Determine which version of SQL Server Management Studio to install

Decide which version of SSMS to install. The most common options are:

- The latest release of [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] that is hosted on Microsoft servers. To install this version, select the following link, which downloads a stub installer, or *bootstrapper*, to your *Downloads* folder.

  **[Download SSMS 21](https://aka.ms/ssms/21/release/vs_SSMS.exe)**

- If you already have SQL Server Management Studio 21 installed, you can [install another version alongside it](side-by-side.md).

You can download a bootstrapper or installer for a specific version from the [Release history](../release-history.md) page and use it to install another version of SSMS.

## Step 3 - Initiate the installation

If you downloaded a bootstrapper file, you can use it to install SSMS. You need administrator permissions. The bootstrapper installs the latest version of the Visual Studio Installer. The installer is a separate program that provides everything you need to both install and customize SSMS.

1. From your *Downloads* folder, double-click the bootstrapper named `vs_SSMS.exe` to start the installation.

1. If you receive a User Account Control notice, choose **Yes**. The dialog box asks you to acknowledge the [Microsoft Privacy Statement](https://www.microsoft.com/privacy/privacystatement) and [Microsoft Software License Terms](/legal/sql/ssms/sql-server-management-studio-license-terms). Choose **Continue**.

The Visual Studio Installer opens. In addition to SQL Server Management Studio, you can also install any product that [Visual Studio Installer's](/visualstudio/install/install-visual-studio-versions-side-by-side#install-different-editions-of-the-same-major-visual-studio-version-side-by-side) **Available** tab offers.

## Step 4 - Choose workloads (optional)

After you install the Visual Studio Installer, you can use it to customize your installation SQL Server Management Studio by selecting different options on the tabs of the installer. Here's how.

1. Select the workload that you want in the **Visual Studio Installer**.

   :::image type="content" source="media/install/ssms-installation-1.png" alt-text="Screenshot of the Visual Studio Installer window, showing workload selection." lightbox="media/install/ssms-installation-1.png":::

1. Review the workload summaries to decide which workload supports the features you need. For example, choose the Hybrid and Migration workload to assess your upgrade readiness and migrate your data.

1. After you choose the workloads that you want, select **Install**. Status screens appear that show the progress of your SSMS installation.

## Step 5 - Choose individual components (optional)

If you don't want to use the workloads feature to customize your SSMS installation, or you want to add more components, you can install or add individual components from the **Individual components** tab. Choose the components that you want, and then follow the prompts.

:::image type="content" source="media/install/ssms-installation-2.png" alt-text="Screenshot of the Visual Studio Installer window, showing component selection." lightbox="media/install/ssms-installation-2.png":::

## Step 6 - Install language packs (optional)

By default, the installer program tries to match the language of the operating system when it runs for the first time. To install SSMS in a language of your choosing, choose the **Language packs** tab from the Visual Studio Installer, and then follow the prompts.

### Change the installer language from the command line

Another way that you can change the default language is by running the installer from the command line. For example, you can force the installer to run in English by using the following command:

```console
vs_SSMS.exe --locale en-US
```

The installer remembers this setting when you run it again. The installer supports these language locales: `zh-cn`, `zh-tw`, `cs-cz`, `en-us`, `es-es`, `fr-fr`, `de-de`, `it-it`, `ja-jp`, `ko-kr`, `pl-pl`, `pt-br`, `ru-ru`, and `tr-tr`.

## Step 7 - Select the installation location (optional)

You can reduce the installation footprint of SSMS on your system drive. For more information, see [Select installation locations for SQL Server Management Studio](select-install-location.md).

You can select a different drive for **SQL Server Management Studio** or **Download cache** only when you first install SSMS. If you already installed it and want to change drives, you must uninstall SSMS and then reinstall it.

If SSMS or Visual Studio is already installed on your computer, you can't change the Shared components, tools, and SDKs path. It appears greyed out. This location is shared by all installations of SSMS and Visual Studio.

## Step 8 - Sign in to your account (optional)

While you don't have to sign in, there are many advantages to doing so, such as synchronizing your settings across devices. See [Sign in or switch user accounts in SQL Server Management Studio](../sign-in.md).

[!INCLUDE [support](../includes/support.md)]

## Related content

- [Update SQL Server Management Studio](update.md)
- [Modify SQL Server Management Studio workloads, components, and language packs](modify.md)
- [Uninstall or remove SQL Server Management Studio](uninstall.md)
- [Create an offline installation of SQL Server Management Studio](create-offline.md)
- [Use command-line parameters to install SQL Server Management Studio](command-line-parameters.md)
