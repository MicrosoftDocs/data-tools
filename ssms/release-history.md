---
title: Release History for SQL Server Management Studio
description: Learn about the release history for SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mbarickman, erinstellato
ms.date: 02/24/2026
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
---

# Release history for SQL Server Management Studio

SQL Server Management Studio is regularly updated to provide new features, performance and reliability improvements, security updates, and bug fixes.

[!INCLUDE [ssms-21-md](includes/ssms-21-md.md)] introduces Preview and Release channels to give you the flexibility and control to decide when to adopt feature updates. The latest release on each channel is always the most secure version, so you should stay up to date regardless of the channel you choose.

For more information, see:

- [SQL Server Management Studio (SSMS) support policy](support-policy.md)
- [Channels for SQL Server Management Studio](install/channels-release.md)

## Release notes

Here are the release notes for different versions of SQL Server Management Studio:

- [SQL Server Management Studio 21 release notes](release-notes-21.md)
- [SQL Server Management Studio 20 release notes](release-notes-20.md)

## Update your installation to a specific release

If you need to install or update to a specific release of SSMS, you can find the available bootstrapper in the [Evergreen bootstrapper](#evergreen-bootstrapper) table.

## Uninstall SSMS to go back to an earlier release

<!--To install an earlier release of SQL Server Management Studio 22, uninstall your current installation. Then, use one of the links later in this article to reinstall the version that you want.

1. On Windows, open the Visual Studio Installer.
1. Uninstall all instances of SQL Server Management Studio 22 listed in the Visual Studio Installer.
1. From Programs and Features in the Control Panel, find **SQL Server Management Studio 22**, and uninstall it.-->

To install an earlier release of SQL Server Management Studio 21.x or earlier for a major version (for example, to downgrade from SSMS 21.6 to SSMS 20.2), uninstall your current installation. Then, use one of the links later in this article to reinstall the version that you want.

- On Windows, from **Programs and Features** in the Control Panel, find your version of **SSMS** and uninstall it.

Before attempting to install a previous version of SQL Server Management Studio, refer to the [support policy](support-policy.md). Microsoft doesn't guarantee support outside of this policy.

If a corrupted install prevents you from following the previous steps, follow the steps to remove SQL Server Management Studio with the [InstallCleanup.exe tool](install/uninstall.md#remove-all-with-installcleanupexe).

Uninstalling SSMS doesn't remove standalone products and components such as .NET and Visual C++ Redistributables. You might need to remove these components manually from **Apps and Features** in Windows Settings.

## Release dates and build numbers

This section provides links to the publicly released bootstrappers for SQL Server Management Studio. The bootstrappers initiate Visual Studio's installation process. Only the latest release is supported.

To verify what version a given bootstrapper installs, right-click on the bootstrapper `vs_SSMS.exe`, choose **Properties** > **Details**, and look at the Product Version information. The version number should always be read as *latest of that version*. A bootstrapper with a Product Version of 21.0 installs the latest 21.0.x servicing release that's available.

### Evergreen bootstrapper

The bootstrapper in the following table always installs the latest release of SSMS from its respective channel.

| Channel | Version | Bootstrapper |
| --- | --- | --- |
| Release | [!INCLUDE [latest-build](includes/latest-build.md)] | [SQL Server Management Studio GA](https://aka.ms/ssms/22/release/vs_SSMS.exe) |
| Release | 22.3.0 | [SQL Server Management Studio 22.3.0](https://download.visualstudio.microsoft.com/download/pr/50e56d52-cb9f-4891-880e-59ab5de5c80d/adeb6cf1c1f9b6c472b870eee7a4883efd1636c3a5457a7b36c69f2b1fd56e37/vs_SSMS.exe) |
| Release | 22.2.1 | [SQL Server Management Studio 22.2.1](https://download.visualstudio.microsoft.com/download/pr/98009c04-e4b8-4223-8794-58f961de75a4/75159abce36103c35f173e03b7b3ec0b004094013968f5980d77a4c0436e36c7/vs_SSMS.exe) |
| Release | 22.1 | [SQL Server Management Studio 22.1](https://download.visualstudio.microsoft.com/download/pr/451b234a-4e25-491d-a007-bf3e55b2562f/4a7eda53a20fecf4d012d8b845bf4b7e2c94a4bced41f979b85cdee1b517021f/vs_SSMS.exe) |
| Release | 22.0 | [SQL Server Management Studio 22.0](https://download.visualstudio.microsoft.com/download/pr/d3b4e0f6-4bc0-4ec0-ba9c-20b355d61cc4/b50e52759454345ab17bdafcb40774f9bc635cf8fd933dacc4097909f3dbccf7/vs_SSMS.exe) |

### Fixed version installers

This table lists latest build numbers of publicly released versions of SQL Server Management Studio, the release date, and download link.

| SSMS version | Build number | Release date |
| --- | --- | --- |
| [21.6.17](https://download.visualstudio.microsoft.com/download/pr/5967a899-96aa-47e2-a7c5-1b7192f292ee/cb58e449b5f554b28fa66a2a04d7c1bf55073f16242c8eb3b4d63fbfc10de5d0/vs_SSMS.exe) | 21.6.17 | October 14, 2025 |
| [20.2.1](https://go.microsoft.com/fwlink/?linkid=2313753&clcid=0x409) | 20.2.37.0 | April 8, 2025 |
| [19.3](https://go.microsoft.com/fwlink/?linkid=2257624&clcid=0x409) | 19.3.4.0 | January 10, 2024 |
| [18.12.1](https://go.microsoft.com/fwlink/?linkid=2199013&clcid=0x409) | 15.0.18420.0 | June 21, 2022 |
| [17.9.1](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x409) | 14.0.17289.0 | November 21, 2018 |
| [16.5.3](https://go.microsoft.com/fwlink/?LinkID=840946) | 13.0.16106.4 | January 30, 2017 |

## Related content

- [Channels for SQL Server Management Studio](install/channels-release.md)
- [SQL Server Management Studio (SSMS) support policy](support-policy.md)
