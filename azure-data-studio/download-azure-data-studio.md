---
title: Download and install Azure Data Studio
description: Download and install Azure Data Studio for Windows, macOS, or Linux. This article provides release dates, version numbers, system requirements, and download links.
author: dlevy-msft
ms.author: dlevy
ms.reviewer: maghan, randolphwest
ms.date: 06/13/2024
ms.service: azure-data-studio
ms.topic: overview
ms.custom: intro-overview
---

# Download and install Azure Data Studio

Azure Data Studio is a lightweight, cross-platform data management and development tool with connectivity to popular cloud and on-premises databases. Azure Data Studio supports Windows, macOS, and Linux, with immediate capability to connect to Azure SQL and SQL Server.  Browse the extension library for more database support options including MySQL, PostgreSQL, and Cosmos DB.

Azure Data Studio's familiar interface offers a modern editor experience with IntelliSense, code snippets, source control integration, and an integrated terminal.  Engineered with the data platform user in mind, its extensibility allows users to customize their experience by installing the extensions relevant to their workflow, including database migrations, charting, GitHub Copilot, and more!

Use Azure Data Studio to query, design, and manage your databases and data warehouses wherever they are, on your local computer or in the cloud.

For more information about Azure Data Studio, visit [What is Azure Data Studio?](what-is-azure-data-studio.md).

## Download Azure Data Studio

Azure Data Studio 1.48.1 is the latest general availability (GA) version.

- Release number: 1.48.1
- Release date: June 13, 2024
  
| Platform | Type | Download |
| --- | --- | --- |
| Windows | User Installer | [x64](https://go.microsoft.com/fwlink/?linkid=2261569)&emsp;[ARM64](https://go.microsoft.com/fwlink/?linkid=2261845) |
| | System Installer | [x64](https://go.microsoft.com/fwlink/?linkid=2261844)&emsp;[ARM64](https://go.microsoft.com/fwlink/?linkid=2262106) |
| | .zip | [x64](https://go.microsoft.com/fwlink/?linkid=2262105)&emsp;[ARM64](https://go.microsoft.com/fwlink/?linkid=2261570) |
| macOS | .zip | [Universal](https://go.microsoft.com/fwlink/?linkid=2261571)&emsp;[Intel Chip](https://go.microsoft.com/fwlink/?linkid=2262107)&emsp;[Apple Silicon](https://go.microsoft.com/fwlink/?linkid=2261572) |
| Linux | .tar.gz | [x64](https://go.microsoft.com/fwlink/?linkid=2261846) |
| | .deb | [x64](https://go.microsoft.com/fwlink/?linkid=2261573) |
| | .rpm<sup>1</sup> | [x64](https://go.microsoft.com/fwlink/?linkid=2261574) |

<sup>1</sup> There's a known issue with install on RHEL. For more information, see the [release notes](release-notes-azure-data-studio.md#known-issues-in-1481).

If you have comments or suggestions or want to report a problem with downloading Azure Data Studio, submit an issue to our team on the [Azure Data Studio feedback page](https://github.com/microsoft/azuredatastudio/issues/).

## Install Azure Data Studio

#### [Windows](#tab/win-install)

[!INCLUDE [install-windows](includes/download-azure-data-studio/install-windows.md)]

#### [macOS](#tab/macOS-install)

### macOS installation

1. Download [Azure Data Studio for macOS](https://azuredatastudio-update.azurewebsites.net/latest/darwin-universal/stable).

1. To expand the contents of the .zip file, double-click it.

1. To make Azure Data Studio available in Launchpad, drag the *Azure Data Studio.app* file to the *Applications* folder.

> [!NOTE]  
> For Apple Silicon users, please make sure you have Rosetta 2 installed. Some backend services are yet to be converted to native ARM64 binaries. You can run the following command in a Terminal window to install Rosetta 2.
>  
> ```bash
> /usr/sbin/softwareupdate --install-rosetta --agree-to-license
> ```

#### [Linux](#tab/linux-install)

[!INCLUDE [install-linux](includes/download-azure-data-studio/install-linux.md)]

---

## What's new with Azure Data Studio

For details about the latest release of Azure Data Studio, see [Release notes for Azure Data Studio](./release-notes-azure-data-studio.md).

## Download the insiders build of Azure Data Studio

As an alternative, if you want to try out the beta features and send feedback, you can [download the insiders build of Azure Data Studio](https://github.com/microsoft/azuredatastudio#try-out-the-latest-insiders-build-from-main-branch).

## Supported operating systems

Azure Data Studio runs on Windows, macOS, and Linux. The following versions are supported:

- Windows: 10 and later versions
- Windows Server: 2016, 2019, 2022
- macOS: versions with Apple security update support. This is typically the latest release and the two previous versions.
- Linux: Debian 9+, RHEL 7+, SLES 15, Ubuntu 18.04+

> [!NOTE]  
> Incremental versions within a major operating system release may no longer be in support by the operating system. Consult the documentation for your operating system to ensure you have received applicable updates.

## System requirements

| Requirement level | CPU cores | RAM memory |
| --- | :---: | :---: |
| Recommended | 4 | 8 GB |
| Minimum | 2 | 4 GB |

## Check for updates

To check for the latest updates, on the left pane, select **Manage** (gear icon), and then select **Check for Updates**.

To apply environment updates offline, [install the latest version](#download-and-install-azure-data-studio) directly over your previously installed version. You don't need to uninstall earlier versions of Azure Data Studio. If an earlier version is present, the installer automatically updates to the latest version.

## Uninstall

#### [Windows](#tab/windows-uninstall)

**Windows**

If you installed Azure Data Studio by using the Windows installer, uninstall it just as you would any Windows application.

If you installed Azure Data Studio with a .zip file or other archive, delete that file.

#### [macOS](#tab/macOS-uninstall)

**macOS**

You can [uninstall apps](https://support.apple.com/guide/mac-help/install-and-uninstall-other-apps-mh35835/mac) from the Internet or drive on Mac by completing the following steps:

1. Select the **Finder icon** in the Dock, and then select **Applications** in the **Finder** sidebar.

1. Do one of the following steps:

   - If an app is in a folder, open the app's folder to check for an uninstaller. Double-click **Uninstall [App]** or **[App] Uninstaller**, and then follow the onscreen instructions.

   - If an app isn't in a folder or doesn't have an uninstaller, drag the app from the *Applications* folder to the Trash (at the end of the Dock).

To uninstall apps you've downloaded from the App Store, use Launchpad.

#### [Linux](#tab/linux-uninstall)

[!INCLUDE [uninstall-linux](includes/download-azure-data-studio/uninstall-linux.md)]

---

## Related content

To learn more about Azure Data Studio, see the following resources:

- [Azure Data Studio release notes](release-notes-azure-data-studio.md)
- [What is Azure Data Studio?](what-is-azure-data-studio.md)
- [SQL tools](/sql/tools/overview-sql-tools)
- [SSMS](/sql/ssms/download-sql-server-management-studio-ssms)
- [Azure Data Architecture Guide](/azure/architecture/data-guide/)

[!INCLUDE [contribute-to-content](includes/contribute-to-content.md)]

[Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=521839) and [Enable or disable usage data collection for Azure Data Studio](usage-data-collection.md).
