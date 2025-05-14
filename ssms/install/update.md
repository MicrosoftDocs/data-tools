---
title: Update SQL Server Management Studio
description: Update your SQL Server Management Studio (SSMS) installation to the most recent release to access the latest feature changes and fixes for known issues.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan
ms.date: 05/19/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---
# Update SQL Server Management Studio

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] must be [installed on the machine](install.md) in order to update it.

## Before you update

By default, in order to install, update, or modify SSMS, the account performing the update must have administrative permissions on the machine, and also must have permissions to the source where the product updates are located (either the internet or an internal location). If you're logged in as a typical user and try to perform one of these commands, then you get a User Account Control notice prompting you for admin credentials.

SQL Server Management Studio (SSMS) must be closed before performing an update. We highly recommend saving your work before performing an update.

We encourage you to update to the most [recent release](../release-notes-21.md) of SQL Server Management Studio (SSMS) so that you always get the latest features, security fixes, and improvements.

There are many different ways to update an installation of SSMS:

- Update using the Visual Studio Installer
- Within SSMS, check for updates or use the notification hub
- Configure SSMS to automatically update upon close
- Update by running a [specific version of the bootstrapper](../release-history.md)
- Update SSMS programmatically.

Here's how to update SQL Server Management Studio (SSMS) using these various methods.

## Use the Visual Studio Installer

1. Find the **Visual Studio Installer** on your computer.

   In the Windows Start menu, search for "installer", and then select **Visual Studio Installer** from the results.

   If you're prompted to update the Visual Studio Installer before continuing, do so by following the prompts.

   > [!NOTE]  
   > SSMS setup features and bug fixes are typically implemented in the installer. The installer ships the most current release for the latest supported SSMS version. This means that in general (unless otherwise specified), all new setup functionality is automatically available and works seamlessly in older versions of the product.

1. In the Visual Studio Installer, look for the installation of SSMS that you want to update.

   For example, if you previously installed [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] and there's an update for it, then an **Update available** message appears in the Visual Studio Installer.

1. Choose **Update** to install the update.

1. After the update is complete, the Visual Studio Installer might prompt you to restart your computer. If so, do so, and then start SSMS as you typically would.

   If you aren't asked to restart your computer, choose **Launch** to start SSMS from the Visual Studio Installer.

## Use the message box in the application

1. When you open SSMS, the application checks to see if an update is available. In certain situations, a **SQL Server Management Studio update** message will briefly appear. If you want to update immediately, select **View details**. If you want to defer the update until when you close SSMS, select **Update on Close**.

1. If you select **View details**, then in the subsequent **Update available** dialog, select **Update** to update now.

## Use the Notifications hub in the application

1. Choose the notification icon from the lower-right corner of SSMS to open the **Notifications hub**.

1. In the **Notifications hub**, select the update that you want to install. If you want to update immediately, select **View details**. If you want to defer the update until when you close SSMS, select **Update on Close**.

1. If you select **View details**, then in the subsequent **Update available** dialog, select **Update**.

> [!NOTE]  
> The **Update on Close** command that is found in both the update notification message box or in the **Notification** hub isn't a permanent setting; it applies only to the current update. It's a way to defer the update to when you voluntarily close SSMS. To learn how to configure this setting permanently, see the [Customize update settings](#always-update-on-close-and-other-download-behaviors) section.

## Manually check for updates

You can check to see if an update is available by choosing **Help** from the menu bar, and then choosing **Check for Updates**. You can also use the search box by selecting **Ctrl**+**Q**, typing **check for updates**, and then select the search result that matches. In the subsequent **Update available** dialog box, choose **Update**.

## Run a specific bootstrapper to update the product to a specific version

You can update your instance of SQL Server Management Studio to any specific version that has been released, as long as it's a higher version than what is currently installed. To update your instance of SQL Server Management Studio via this method, see the [release history](../release-history.md), download the bootstrapper that corresponds to the desired update version into your product installation directory, and then double-click on the file to initiate the update.

## Customize update settings

There are several different settings that can be customized to control the update behavior, such as how and when the product bits are downloaded and installed, or where the update source is located.

### Always Update on Close and other download behaviors

On the menu bar, select **Tools** > **Options** > **Environment** > **Product Updates**. Observe the configuration options that are available to set in this dialog.

- You can select the **Automatically download updates** setting, which allows updates to download while your machine is idle.

- You can configure SSMS to automatically apply the latest available update upon close. This setting is configurable on a per-installation basis of SSMS. For example, you can set your Preview installation to apply updates when SSMS closes, but your Release installation can continue to be updated on demand. After you configure SSMS to **Always update on close**, updates begin once SSMS and all related processes are closed. If any extensions have been scheduled for installation or update, the SSMS update doesn't start until the next time SSMS closes.

- There are also two installation modes to choose from: **Install while downloading** and **Download all, then install**.

### Configure source location of updates

With [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)], you can now configure the location from where your clients get their updates. These update source locations are called *channels*, and you can find more information about channel purpose and availability in the [Channels for SQL Server Management Studio](channels-release.md) documentation. Microsoft makes both the Release and the Preview channels available to everyone.

There are two ways to bring up the Update Settings dialog, which allows you to manually change the channel from which your SSMS installation should get its updates.

1. Open the Visual Studio Installer, select the installation you want to configure, select **More**, and then select the **Update settings** menu option. Refer to previous instructions for how to find the Visual Studio Installer.

1. An alternative way to invoke the Update Settings dialog is to open SSMS, bring up the Update available dialog (either **View details** on an update notification or **Check for updates** on the Help menu) and select the **Change update settings** link.

By selecting the correct value in the **Update channel** dropdown list, you can control the source location of future updates for this installation of SSMS. Also keep in mind the following items:

- The Preview and Release channels are available for SQL Server Management Studio 21 and later versions.

- You can choose to update your installation of SSMS immediately after you configure the **Update channel** location, or you can defer the actual product update until a later time. The act of configuring the update channel and the act of updating the product are two independent events. For information on how to programmatically control the update channel, refer to [Use the modifySettings command](/visualstudio/install/use-command-line-parameters-to-install-visual-studio#modifysettings-command-and-command-line-parameters).

- You can only change the update channel if the version of the product that's available in the channel is **greater** than the version you installed. For example, you can always transition from the Release channel to the Preview channel, but you can't transition from the Preview channel to the Release channel until the latest release on the Release channel surpasses the version of Preview that you have installed.

- When you update to a new channel, you install the most recent release on that channel. If you want to install a particular version of the product on that channel, then follow the [Run a specific bootstrapper instructions](#run-a-specific-bootstrapper-to-update-the-product-to-a-specific-version) described previously.

- All Microsoft channels are hosted on Microsoft servers and require access to the internet.

- Each installation of SSMS has the ability to independently configure its source for updates. If you have two SQL Server Management Studio (SSMS) installations, each can update from a different channel.

## Use the latest installer

The most current release of the installer in the latest version of SSMS typically has the most robust and reliable feature set. This functionality often seamlessly works on lower versioned products. In order to manually acquire the latest version of the installer onto a client machine, [download any recent bootstrapper for the latest version of SSMS](install.md#step-2---determine-which-version-of-sql-server-management-studio-to-install) and then either:

- Run the bootstrapper to initiate the installation. The latest installer is installed onto the machine first. Once the **Choose Workloads** tab appears, cancel the installation.

- In a command window, use the bootstrapper to update the installer:

  ```cmd
  vs_ssms.exe --update --quiet
  ```

[!INCLUDE [support](../includes/support.md)]

## Related content

- [Install SQL Server Management Studio versions side-by-side](side-by-side.md)
- [Modify SQL Server Management Studio workloads, components, and language packs](modify.md)
- [Uninstall or remove SQL Server Management Studio](uninstall.md)
