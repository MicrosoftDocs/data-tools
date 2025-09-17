---
title: Create an Offline Installation of SQL Server Management Studio
description: Create an offline installation package to install SQL Server Management Studio (SSMS) offline when you have an unreliable internet connection or low bandwidth.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan, mbarickman
ms.date: 09/25/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
---
# Create an offline installation of SQL Server Management Studio

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] is designed to work well in various computer configurations. In this article, you learn how to create an offline installation package of files for installation on the *local machine*.

## Use the command line to create a local layout

### Step 1 - Download the SSMS bootstrapper

[Download the correct bootstrapper](install.md) for the version of SSMS you want, and copy it into the folder you want to use as the source location for your local layout. The bootstrapper is the executable you use to create, update, or modify your local layout. You must have an internet connection to complete this step.

### Step 2 - Create a local layout

Open a command prompt with administrator privileges, navigate to the folder where you downloaded the bootstrapper, and use the [bootstrapper's parameters](command-line-parameters.md#layout-command-and-command-line-parameters) to create your local layout. You must have an internet connection to complete this step.

You can install a language other than English by changing `en-US` to a locale from the [list of language locales](command-line-parameters.md#list-of-language-locales), and you can use the [list of component IDs](workload-component-ids.md) to further customize your local layout.

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

After the bootstrapper has finished downloading the layout files, the local layout folder can be moved to any other machine or environment you want to install SQL Server Management Studio on without requiring an internet connection.

> [!NOTE]  
> Make sure that your full installation path is less than 80 characters and that your machine has ample storage. SQL Server Management Studio requires a minimum of 4-GB of disk space. For more information, see [System requirements for SQL Server Management Studio](../system-requirements.md).

### Step 3 - Install SSMS from the local layout

When you install SSMS from a local layout, the Visual Studio Installer uses the local versions of the files. If you select components during installation that aren't in the layout, then the Visual Studio Installer attempts to download them from the internet. To make sure you install only the files you previously downloaded, use the same [command-line options](command-line-parameters.md) you used to create the local layout. To make sure your installer doesn't try to access the internet when it's installing the product, use the `--noweb` switch.

For example, if you created a local installation layout using the command from step 2, then use the following command to run the installation and prevent the client machine from accessing the internet:

```console
C:\SSMS_Layout\vs_SSMS.exe --noWeb --add Microsoft.Component.HelpViewer
```

## Validate a certificate for offline installations

Installing SSMS on an offline machine can require a valid certificate. If you try to install SSMS on an offline machine using a layout, and the installer exits with no exception, it might be due to an invalid certificate. Go to the `%TEMP%` folder and open the most recent bootstrapper file named `dd_bootstrapper_yyyyMMddHHmmss.log`. The following messages indicate the installation is failing because of an invalid certificate:

```output
Certificate is invalid: <YourSSMSFolder>\vs_installer.opc
Error: Unable to verify the certificate: InvalidCertificate
Error 0x80131509: Signature verification failed. Error: Unable to verify the integrity of the installation files: the certificate could not be verified.
```

To ensure the installation completes successfully, follow these steps:

1. On a machine with internet connection, download the [Microsoft Windows Code Signing PCA 2024 certificate](https://www.microsoft.com/pkiops/certs/Microsoft%20Windows%20Code%20Signing%20PCA%202024.crt).
1. Move the .crt file to the offline machine.
1. From the offline machine, right-click the .crt file and select **Install Certificate**.
1. Select **Local Machine** as Store Location and then **Next**.
1. Keep **Automatically select the certificate store based on the type of certificate**, then select **Next**.
1. Select **Finish**.
1. You see the prompt, **The import was successful**.
1. Install SSMS using the local layout.

## Use the "Download all, then install" feature

Sometimes online access is problematic. For example, you might have an unreliable internet connection or your internet connection might have low bandwidth. For situations like these, you can use the **Download all, then install** feature from the Visual Studio Installer to download an installation package on the local machine *before* you install it locally. Alternatively, you can use the command line to create a local installation package to install locally later.

After you [download the bootstrapper](#step-1---download-the-ssms-bootstrapper), run it to install SSMS. It first installs and then launches the latest version of the Visual Studio Installer. Within the Visual Studio Installer, customize your installation of SSMS by selecting the workloads or components you want to install, as well as the installation location and language packs.

Once you have completed your selection, select the **Download all, then install** option in the dropdown list next to the **Install** button of the Visual Studio Installer. Selecting this option will download the SSMS packages needed for installation on the local machine. By downloading the packages locally first, you can then safely disconnect from the internet before you install SSMS.

[!INCLUDE [support](../includes/support.md)]

## Related content

- [Use command-line parameters to install SQL Server Management Studio](command-line-parameters.md)
- [Workload and component IDs for SQL Server Management Studio](workload-component-ids.md)
- [Install SQL Server Management Studio](install.md)
- [Modify SQL Server Management Studio workloads, components, and language packs](modify.md)
