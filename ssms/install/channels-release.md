---
title: Channels for SQL Server Management Studio
description: Channels for SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, mbarickman
ms.date: 10/14/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
---
# Channels for SQL Server Management Studio

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

SQL Server Management Studio (SSMS) follows a regular release cadence to ensure users have access to the latest features and improvements. This document outlines the different channels available for SSMS, expected release cadence, and how you can provide feedback on new features and updates.

We continually enhance the capabilities of SQL Server Management Studio with regular minor version updates, and we introduce new features according to our [roadmap of upcoming features](../roadmap.md). New features appear first on the **Preview channel** so that you can provide early feedback. When these new features are ready for widespread use, we release them on the **Release channel**. We might sometimes include **Preview Features** in the **Release channel**, to give you an opportunity to try out new features and share your feedback without doing another install.

This article describes our channels for releasing previews, preview features, general releases, and servicing fixes, and how you can [provide feedback](https://aka.ms/ssms-feedback) to us on the features and fixes we release.

You can control when to adopt feature updates by selecting a channel. There are two options for installing and updating SSMS. You might have both channels installed on a single machine:

- [Preview channel](https://aka.ms/ssms/21/preview/vs_SSMS.exe)
- [Release channel](https://aka.ms/ssms/21/release/vs_SSMS.exe)

## Determine your product version and channel

You can determine which channel and version of SSMS you're using by opening **Help** -> **About**. The version number indicates the major version of SSMS by using the first number ("`21`"), the minor update version by using the second number ("21.`0`"), and the servicing version by using the third number ("21.0.`1`"). If you're using the Preview channel, the preview release is also indicated after the version number ("21.0 **Preview**"), and within SSMS, **PREVIEW** appears near the top right of the SSMS window.

## Installing, updating, and switching channels

You might select a channel by either installing a release of SSMS from that channel or, in some cases, by configuring the [source location for updates](update.md#configure-source-location-of-updates). The following sections link to the installation location for each channel.

You can [install multiple channels side-by-side](side-by-side.md) on the same machine. For example, you might install and use Preview channel side-by-side with Release channel. Some shared components, for example Windows SDK, are used by all channels on a machine and are updated to whichever channel has the latest version.

Updates are delivered independently to each channel, and you'll receive a [separate notification](update.md) within each installed version of SSMS if there's an update available for its channel. You can also update each channel by using the Visual Studio Installer.

## Release channel

**Release channel** keeps you up to date with the features ready for widespread mainstream production use. The updates released to the Release channel fall into the following two categories:

- **Minor updates** ship to the Release channel after being available in the Preview channel. These updates might include new features, bug fixes, and changes to adapt to platform updates (for example, changes in Windows or Azure).

- **Servicing updates** are releases of targeted fixes for critical quality, performance, reliability, or security issues.

We stop servicing a minor version update on the Release channel when the next minor version update is released. For example, we won't provide additional servicing updates to version 21.0 once 21.1 has released.

We announce minor updates through the [SQL Server blog](https://techcommunity.microsoft.com/category/sql-server/blog/sqlserver). All minor and servicing updates are accompanied by [release notes](../release-notes-21.md). SSMS also alerts you that a new update is available from the [notification icon](/visualstudio/ide/visual-studio-notifications) in the bottom right corner of the application, by an entry in the notification hub, and by text in the Visual Studio Installer.

When you update your install of SSMS on the Release channel, you receive the latest servicing update for the latest available minor update.

## Preview channel

**Preview channel** is meant for customers who are eager to try out the latest SSMS features and fixes. It provides you with an early peek of what's coming in the next version update of the Release channel. You can learn about the features and fixes in the release notes. We also announce the availability of a new Preview release through the [SQL Server blog](https://techcommunity.microsoft.com/category/sql-server/blog/sqlserver).

The number of preview releases shipped from the Preview channel, before new features ship to the Release channel, varies. Sometimes we also release servicing updates to the Preview channel. You can install both Preview and Release channel versions of SSMS side-by-side on the same machine. At any given point, the Preview channel contains the same or newer features and fixes compared to the Release channel. SSMS notifies you as newer versions are available for install.

Even though previews aren't intended for use in production, they are at a sufficient quality level for you to generally use and provide feedback. We service only the latest preview release. For more information, see [SQL Server Management Studio (SSMS) support policy](../support-policy.md).

## Preview features

Although the Preview channel is recommended for trying out new features, we also encourage users in the Current channel to try out new features via **Preview Features**. Preview Features differ from the Preview channel in that each specific feature can be turned on or off. The Preview Features dialog includes description for each feature to help you determine if the feature is relevant to you. Additionally, we hope that you provide feedback on these features so that we can improve them before they're implemented for all customers.

You can turn Preview Features on or off by going to **Tools > Options > Environment > Preview Features**. We sometimes also run experiments with Preview Features, turning them on for a portion of customers to compare the impact against a control group.

## Update notifications

You'll receive notification of updates to the currently running SSMS through the [notification icon in the application](update.md#use-the-notifications-hub-in-the-application), through posts to the [SQL Server blog](https://techcommunity.microsoft.com/category/sql-server/blog/sqlserver), and from the Visual Studio Installer. The release notes document the features and fixes available in that release to help you make an informed decision about when to install it.

## How to provide feedback

You can report a problem or suggest a feature from **Help > Send Feedback**.

1. Open SQL Server Management Studio.
1. Select **Help > Send Feedback**.
1. Select **Report a Problem...** to report an issue with SSMS, or select **Suggest a Feature...** to suggest a feature or improvement in SSMS.

[!INCLUDE [support](../includes/support.md)]

## Related content

- [Install SQL Server Management Studio](install.md)
- [Update SQL Server Management Studio](update.md)
- [Modify SQL Server Management Studio workloads, components, and language packs](modify.md)
- [Uninstall or remove SQL Server Management Studio](uninstall.md)
