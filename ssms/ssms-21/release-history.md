---
title: Release history for SQL Server Management Studio 21 Preview
description: Learn about the release history for SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan
ms.date: 11/12/2024
ms.service: sql-server-management-studio
ms.topic: concept-article
---
# Release history for SQL Server Management Studio

SQL Server Management Studio is updated regularly to provide new features, performance and reliability improvements, security updates, and bug fixes.

With [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)], we introduce Preview and Release channels to provide customers the flexibility and control to determine when they adopt feature updates. The latest release on each channel is always, by definition, the most secure, so we highly encourage customers to stay up to date regardless of what channel they choose to get updates from. Refer to our [support policy](../support-policy.md) or our [channels documentation](../install/channels-release.md) for additional information.

## Release notes

Here are the release notes for different versions of SQL Server Management Studio:

- [SQL Server Management Studio 21 Preview release notes](release-notes-21.md)
- [SQL Server Management Studio 20 release notes](../release-notes-ssms.md)

## Update your installation to a specific release

If you need to install or update to a specific release of SSMS, you can find the available bootstrapper in the [Evergreen bootstrapper](#evergreen-bootstrapper)] table.

## Uninstall SSMS to go back to an earlier release

If you need to install an earlier release of SQL Server Management Studio 21, you must uninstall your current installation and use one of the links below to reinstall the version that you prefer.

1. On Windows, open the Visual Studio Installer.
1. Uninstall all instances of SQL Server Management Studio 21 listed in the Visual Studio Installer.
1. From Programs and Features in the Control Panel, find **SQL Server Management Studio 21**, and uninstall it.

If you need to install an earlier release of SQL Server Management Studio 20.x and earlier for a major version (for example, to downgrade from SSMS 20.2 to SSMS 20.1), then you must uninstall your current installation and use one of the links below to reinstall the version that you prefer.

1. On Windows, from Programs and Features in the Control Panel, find your version of **Microsoft SQL Server Management Studio** and uninstall it.

Before attempting to install a previous version of SQL Server Management Studio, refer to our [support policy](../support-policy.md). Microsoft doesn't guarantee support outside of this policy.

If you're unable to follow the steps above due to a corrupted install, follow the steps to remove SQL Server Management Studio with the [InstallCleanup.exe tool](../install/uninstall.md#remove-all-with-installcleanupexe).

Uninstalling SSMS won't remove standalone products and components such as .NET and Visual C++ Redistributables. These might need to be removed manually from **Apps and Features** in Windows Settings.

## Release dates and build numbers

This section provides links to the publicly released bootstrappers for SQL Server Management Studio. The bootstrappers initiate Visual Studio's installation process. Only the latest release is supported.

To verify what version a given bootstrapper installs, right-click on the bootstrapper `vs_ssms.exe`, choose **Properties** > **Details**, and look at the Product Version information. The version number should always be read as "latest of that version". A bootstrapper with a Product Version of 21.0 would install the latest 21.0.x servicing release that is available.

### Evergreen bootstrapper

The bootstrapper in the following table will always install the latest release of SSMS from its respective channel.

| Channel | Version | Bootstrapper | End of Support date |
| --- | --- | --- | --- |
| Preview | 21.0 | [SQL Server Management Studio 21 Preview](https://aka.ms/ssms/21/preview/vs_SSMS.exe) | |

### Fixed version installers

This table lists latest build numbers of publicly released versions of SQL Server Management Studio, the release date, and download link.

| SSMS version | Build number | Release date |
| --- | --- | --- |
| [20.2](https://go.microsoft.com/fwlink/?linkid=2278035&clcid=0x409) | 20.2.30.0 | July 9, 2024 |
| [19.3](https://go.microsoft.com/fwlink/?linkid=2257624&clcid=0x409) | 19.3.4.0 | January 10, 2024 |
| [18.12.1](https://go.microsoft.com/fwlink/?linkid=2199013&clcid=0x409) | 15.0.18420.0 | June 21, 2022 |
| [17.9.1](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x409) | 14.0.17289.0 | November 21, 2018 |
| [16.5.3](https://go.microsoft.com/fwlink/?LinkID=840946) | 13.0.16106.4 | January 30, 2017 |

## Related content

- [Channels for SQL Server Management Studio 21 Preview](../install/channels-release.md)
- [SQL Server Management Studio (SSMS) support policy](../support-policy.md)
