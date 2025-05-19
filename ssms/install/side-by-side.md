---
title: "Install SQL Server Management Studio (SSMS) Versions Side-by-Side"
description: Learn how to install SQL Server Management Studio (SSMS) on a computer that has an earlier or later version of SQL Server Management Studio (SSMS) already installed.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan
ms.date: 05/19/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---
# Install SQL Server Management Studio versions side-by-side

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

You can install [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] on a computer that has an earlier [major version](channels-release.md#determine-your-product-version-and-channel) of SQL Server Management Studio (SSMS) already installed.

Before you install versions side-by-side, review the following conditions:

- Use SSMS 21 to open a solution that was created in SSMS 20 or an earlier version. If you modify the solution, you're prompted to save it as a new solution (.sln). You can later open and modify the solution again in the earlier version unless you implement features that are specific to SSMS 21.

- Use SSMS 21 to open a solution that was created in SSMS 20 or an earlier version. You might need to modify your projects and files to be compatible with SSMS 21.

- If you uninstall a version of SSMS on a computer that has more than one version installed, the file associations for SSMS are removed for all versions.

## Install different channels of the same major SSMS version side-by-side

Each installation of SQL Server Management Studio 21 and higher must have a unique combination of major version and [channel](channels-release.md). For example, you can install SSMS 21 Preview alongside the generally available (GA) SQL Server Management Studio 21 Release.

With [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] and later versions, when you upgrade from one minor version of SSMS to the next, by default, the Visual Studio Installer updates your current installation to the latest version in that channel. For example, if Microsoft releases version 21.1.1 to the [release channel](channels-release.md), the installer tries to replace your current installation of SSMS with this latest version on the same channel.

### Manual installation

You can manually use another bootstrapper to install a new instance of SSMS, or you can select one of the options from the Visual Studio Installer's **Available** tab.

1. To use another bootstrapper, you can download and run the bootstrapper file for SSMS, from either the [installation](install.md) article or the [releases](../release-history.md#release-dates-and-build-numbers) article, for the version that you want to install side-by-side with your existing version of SSMS.

1. Using the installer's **Available** tab presumes that you already have another channel of SSMS installed. First find the **Visual Studio Installer** on your computer and launch it. After it updates itself, select the **Available** tab and install one of the offered products.

Then follow the steps to customize your installation. For more information, see [Install SSMS](install.md#step-4---choose-workloads-optional).

[!INCLUDE [support](../includes/support.md)]

## Related content

- [Install SQL Server Management Studio](install.md)
- [Update SQL Server Management Studio](update.md)
- [Modify SQL Server Management Studio workloads, components, and language packs](modify.md)
- [Uninstall or remove SQL Server Management Studio](uninstall.md)
