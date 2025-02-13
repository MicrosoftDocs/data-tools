---
title: Create an offline installation of SQL Server Management Studio 21 Preview
description: Create an offline installation package to install SQL Server Management Studio (SSMS) offline when you have an unreliable internet connection or low bandwidth.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan
ms.date: 11/12/2024
ms.service: sql-server-management-studio
ms.topic: concept-article
---
# Create an offline installation of SQL Server Management Studio 21 Preview

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] is designed to work well in various computer configurations. In this article, you learn how to create an offline installation package of files for installation on the *local machine*.

## Use the "Download all, then install" feature

Sometimes online access is problematic. For example, you might have an unreliable internet connection or your internet connection might have low bandwidth. For situations like these, you have other methods available for acquiring SQL Server Management Studio (SSMS). You can use the **Download all, then install** feature from the Visual Studio Installer to download an installation package on the local machine *before* you install it locally, or you can use the command line to create a local installation package to install locally later.

After you [download the bootstrapper](#step-1---download-the-ssms-bootstrapper), run it to install SSMS. It first installs and then launches the latest version of the Visual Studio Installer, which you can use to customize and configure your installation, download installation packages, and install the product.

To complete downloading the product before installation starts, select the **Download all, then install** option in the dropdown list at the bottom of the default **Workloads** tab of the Visual Studio Installer. The purpose of this feature is to download the SSMS packages in advance on the computer where SSMS is eventually installed. By downloading the packages locally first, you can then safely disconnect from the internet before you install SSMS.

## Use the command line to create a local layout

### Step 1 - Download the SSMS bootstrapper

[Download the correct bootstrapper](install.md) for the version of SSMS you want, and copy it into the directory you want to use as the source location for your local layout. The bootstrapper is the executable you use to create, update, or modify your local layout. You must have an internet connection to complete this step.

### Step 2 - Create a local layout

Open a command prompt with administrator privileges, navigate to the directory where you downloaded the bootstrapper, and use the [bootstrapper's parameters](command-line-parameters.md#layout-command-and-command-line-parameters) to create your local layout. You must have an internet connection to complete this step.

You can install a language other than English by changing `en-US` to a locale from the [list of language locales](command-line-parameters.md#list-of-language-locales), and you can use the [list of component IDs](workload-component-ids.md) to further customize your local layout.

To create a complete local layout for SQL Server Management Studio, run:

```cmd
vs_ssms.exe --layout c:\localSSMSlayout --add Microsoft.Component.HelpViewer
```

After the bootstrapper has finished downloading the layout files, the local layout folder can be moved to any other machine or environment you want to install SQL Server Management Studio on without requiring an internet connection.

> [!NOTE]  
> Make sure that your full installation path is less than 80 characters and that your machine has ample storage. SQL Server Management Studio requires a minimum of 4-GB of disk space. For more information, see [System requirements for SQL Server Management Studio 21 Preview](../ssms-21/system-requirements.md).

### Step 3 - Install SSMS from the local layout

When you install SSMS from a local layout, the Visual Studio Installer uses the local versions of the files. If you select components during installation that aren't in the layout, then the Visual Studio Installer attempts to download them from the internet. To make sure you install only the files you previously downloaded, use the same [command-line options](command-line-parameters.md) you used to create the local layout. To make sure your installer doesn't try to access the internet when it's installing the product, use the `--noweb` switch.

For example, if you created a local installation layout using the command from step 2, then use the following command to run the installation and prevent the client machine from accessing the internet:

```cmd
c:\localSSMSlayout\vs_ssms.exe --noWeb --add Microsoft.Component.HelpViewer
```

[!INCLUDE [support](../includes/support.md)]

## Related content

- [Use command-line parameters to install SQL Server Management Studio 21 Preview](command-line-parameters.md)
- [Install SQL Server Management Studio 21 Preview](install.md)
- [Modify SQL Server Management Studio 21 Preview components and language packs](modify.md)
