---
title: Release History for SQL Server Management Studio
description: Learn about the release history for SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan
ms.date: 05/19/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
---
# Release history for SQL Server Management Studio

SQL Server Management Studio is updated regularly to provide new features, performance and reliability improvements, security updates, and bug fixes.

[!INCLUDE [ssms-21-md](includes/ssms-21-md.md)] introduces Preview and Release channels to provide customers the flexibility and control to determine when they adopt feature updates. The latest release on each channel is always, by definition, the most secure, so we highly encourage customers to stay up to date regardless of what channel they choose to get updates from.

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

If you need to install an earlier release of SQL Server Management Studio 21, you must uninstall your current installation and use one of the links later in this article to reinstall the version that you prefer.

1. On Windows, open the Visual Studio Installer.
1. Uninstall all instances of SQL Server Management Studio 21 listed in the Visual Studio Installer.
1. From Programs and Features in the Control Panel, find **SQL Server Management Studio 21**, and uninstall it.

If you need to install an earlier release of SQL Server Management Studio 20.x and earlier for a major version (for example, to downgrade from SSMS 20.2 to SSMS 19.3), then you must uninstall your current installation and use one of the links later in this article to reinstall the version that you prefer.

1. On Windows, from Programs and Features in the Control Panel, find your version of **Microsoft SQL Server Management Studio** and uninstall it.

Before attempting to install a previous version of SQL Server Management Studio, refer to our [support policy](support-policy.md). Microsoft doesn't guarantee support outside of this policy.

If you're unable to follow the previous steps due to a corrupted install, follow the steps to remove SQL Server Management Studio with the [InstallCleanup.exe tool](install/uninstall.md#remove-all-with-installcleanupexe).

Uninstalling SSMS doesn't remove standalone products and components such as .NET and Visual C++ Redistributables. These components might need to be removed manually from **Apps and Features** in Windows Settings.

## Release dates and build numbers

This section provides links to the publicly released bootstrappers for SQL Server Management Studio. The bootstrappers initiate Visual Studio's installation process. Only the latest release is supported.

To verify what version a given bootstrapper installs, right-click on the bootstrapper `vs_SSMS.exe`, choose **Properties** > **Details**, and look at the Product Version information. The version number should always be read as *latest of that version*. A bootstrapper with a Product Version of 21.0 would install the latest 21.0.x servicing release that is available.

### Evergreen bootstrapper

The bootstrapper in the following table always installs the latest release of SSMS from its respective channel.

| Channel | Version | Bootstrapper | End of Support date |
| --- | --- | --- | --- |
| Preview | 21.0 | [SQL Server Management Studio 21 Preview](https://aka.ms/ssms/21/preview/vs_SSMS.exe) | May 19, 2025 |
| Release | 21.0.0 | [SQL Server Management Studio 21](https://aka.ms/ssms/21/release/vs_SSMS.exe) | |

### Fixed version installers

This table lists latest build numbers of publicly released versions of SQL Server Management Studio, the release date, and download link.

| SSMS version | Build number | Release date |
| --- | --- | --- |
| [20.2.1](https://go.microsoft.com/fwlink/?linkid=2313753&clcid=0x409) | 20.2.37.0 | April 8, 2025 |
| [19.3](https://go.microsoft.com/fwlink/?linkid=2257624&clcid=0x409) | 19.3.4.0 | January 10, 2024 |
| [18.12.1](https://go.microsoft.com/fwlink/?linkid=2199013&clcid=0x409) | 15.0.18420.0 | June 21, 2022 |
| [17.9.1](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x409) | 14.0.17289.0 | November 21, 2018 |
| [16.5.3](https://go.microsoft.com/fwlink/?LinkID=840946) | 13.0.16106.4 | January 30, 2017 |

## Related content

- [Channels for SQL Server Management Studio](install/channels-release.md)
- [SQL Server Management Studio (SSMS) support policy](support-policy.md)
