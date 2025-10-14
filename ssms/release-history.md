---
title: Release History for SQL Server Management Studio
description: Learn about the release history for SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan, mbarickman
ms.date: 10/14/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
---

# Release history for SQL Server Management Studio

SQL Server Management Studio is regularly updated to provide new features, performance and reliability improvements, security updates, and bug fixes.

[!INCLUDE [ssms-21-md](includes/ssms-21-md.md)] introduces Preview and Release channels to give you the flexibility and control to decide when to adopt feature updates. The latest release on each channel is always the most secure version, so we encourage you to stay up to date regardless of the channel you choose.

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

To install an earlier release of SQL Server Management Studio 21, uninstall your current installation. Then, use one of the links later in this article to reinstall the version that you want.

1. On Windows, open the Visual Studio Installer.
1. Uninstall all instances of SQL Server Management Studio 21 listed in the Visual Studio Installer.
1. From Programs and Features in the Control Panel, find **SQL Server Management Studio 21**, and uninstall it.

To install an earlier release of SQL Server Management Studio 20.x or earlier for a major version (for example, to downgrade from SSMS 20.2 to SSMS 19.3), uninstall your current installation. Then, use one of the links later in this article to reinstall the version that you want.

- On Windows, from **Programs and Features** in the Control Panel, find your version of **SSMS** and uninstall it.

Before attempting to install a previous version of SQL Server Management Studio, refer to our [support policy](support-policy.md). Microsoft doesn't guarantee support outside of this policy.

If you're unable to follow the previous steps due to a corrupted install, follow the steps to remove SQL Server Management Studio with the [InstallCleanup.exe tool](install/uninstall.md#remove-all-with-installcleanupexe).

Uninstalling SSMS doesn't remove standalone products and components such as .NET and Visual C++ Redistributables. These components might need to be removed manually from **Apps and Features** in Windows Settings.

## Release dates and build numbers

This section provides links to the publicly released bootstrappers for SQL Server Management Studio. The bootstrappers initiate Visual Studio's installation process. Only the latest release is supported.

To verify what version a given bootstrapper installs, right-click on the bootstrapper `vs_SSMS.exe`, choose **Properties** > **Details**, and look at the Product Version information. The version number should always be read as *latest of that version*. A bootstrapper with a Product Version of 21.0 would install the latest 21.0.x servicing release that's available.

### Evergreen bootstrapper

The bootstrapper in the following table always installs the latest release of SSMS from its respective channel.

| Channel | Version | Bootstrapper |
| --- | --- | --- |
| Release | [!INCLUDE [latest-build](includes/latest-build.md)] | [SQL Server Management Studio](https://aka.ms/ssms/21/release/vs_SSMS.exe) |

### Fixed version installers

This table lists latest build numbers of publicly released versions of SQL Server Management Studio, the release date, and download link.

| SSMS version | Build number | Release date |
| --- | --- | --- |
| [21.5.14](https://download.visualstudio.microsoft.com/download/pr/c2e2845d-bdff-44fc-ac00-3d488e9f5675/9c65ae0a3cf651fda7feb726431b2737eb45a15023687caa047033cba0f86c09/vs_SSMS.exe) | 21.5.14 | September 9, 2025 |
| [21.4.12](https://download.visualstudio.microsoft.com/download/pr/df8b8a1d-60a9-4872-99a4-7b1bcd00b219/5c202483678778f63df9511799b7c7d1da90a8d1b7915e16b5fbc691b08af965/vs_SSMS.exe) | 21.4.12 | August 12, 2025 |
| [21.4.8](https://download.visualstudio.microsoft.com/download/pr/f55fba7b-3f02-49b7-9aca-a075049a807d/68223c53272acced87437bde86eff72237492d2ec25fb7a826bc2372fd17f3fc/vs_SSMS.exe) | 21.4.8 | July 8, 2025 |
| [21.3.7](https://download.visualstudio.microsoft.com/download/pr/13907dbe-8bb3-4cfe-b0ae-147e70f8b2f3/3d053fb9682894e3a96a8b78e629dad1067cc945b9ccfbabd5bee63cb274834f/vs_SSMS.exe) | 21.3.7 | June 23, 2025 |
| [21.3.6](https://download.visualstudio.microsoft.com/download/pr/4652b1eb-63f7-432d-84ab-06108c5d7cd7/f3e8b639888cf4e1f5d376ed5ef1b09f8162ed08647f29a74ef0b792fec1c3db/vs_SSMS.exe) | 21.3.6 | June 17, 2025 |
| [21.2.5](https://download.visualstudio.microsoft.com/download/pr/e98d75fa-91b1-47a1-9cb7-b6556de592c5/b9a12c1311597fff8ea7a692ee50c4756b4b59f81afa2d8f2bd7df423b5c4916/vs_SSMS.exe) | 21.2.5 | June 10, 2025 |
| [21.1.3](https://download.visualstudio.microsoft.com/download/pr/d2fa077f-a814-4fb2-b903-1fca7658d17e/25e7aadbb210cddfda34d886727aa5d3d3ba822ccdfd7c5e5ca0b0b30da6daf8/vs_SSMS.exe) | 21.1.3 | May 28, 2025 |
| [21.0.0](https://download.visualstudio.microsoft.com/download/pr/f50ab15d-99d5-43aa-b0b4-496b6cb1e574/4f15f0c3434b0e68ef9041f7e951d87da771e1af00f78dda01bae020c2fc5b26/vs_SSMS.exe) | 21.0.0 | May 19, 2025 |
| [20.2.1](https://go.microsoft.com/fwlink/?linkid=2313753&clcid=0x409) | 20.2.37.0 | April 8, 2025 |
| [19.3](https://go.microsoft.com/fwlink/?linkid=2257624&clcid=0x409) | 19.3.4.0 | January 10, 2024 |
| [18.12.1](https://go.microsoft.com/fwlink/?linkid=2199013&clcid=0x409) | 15.0.18420.0 | June 21, 2022 |
| [17.9.1](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x409) | 14.0.17289.0 | November 21, 2018 |
| [16.5.3](https://go.microsoft.com/fwlink/?LinkID=840946) | 13.0.16106.4 | January 30, 2017 |

## Related content

- [Channels for SQL Server Management Studio](install/channels-release.md)
- [SQL Server Management Studio (SSMS) support policy](support-policy.md)
