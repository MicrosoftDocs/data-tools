---
title: Azure SQL Migration Extension for Azure Data Studio
description: This article describes how you can migrate your data using the Azure SQL migration extension with Azure Data Studio.
author: nilabjaball
ms.author: niball
ms.reviewer: randolphwest, maghan
ms.date: 02/06/2025
ms.service: azure-data-studio
ms.subservice: migration-extension
ms.topic: conceptual
ms.collection:
  - sql-migration-content
---

# Azure SQL migration extension for Azure Data Studio

[!INCLUDE [azure-data-studio-deprecation](../includes/azure-data-studio-deprecation.md)]

[!INCLUDE [database-migration-services-ads](../includes/database-migration-services-ads.md)]

This article describes installing the Azure SQL migration extension through [!INCLUDE [azure-data-studio-short](../includes/azure-data-studio-short.md)].

## Prerequisites

If you don't have an Azure subscription, create a [free Azure account](https://azure.microsoft.com/free/) before you begin.

The following prerequisites are also required to install this extension:

- [Download and install Azure Data Studio](../download-azure-data-studio.md)

## Install the Azure SQL migration extension

Follow these steps to install the Azure SQL migration extension in [!INCLUDE [azure-data-studio-short](../includes/azure-data-studio-short.md)]. You can choose the standard installation method, or an offline mode when the computer is disconnected from the Internet.

### [Connected mode](#tab/connected)

### Connected mode installation

1. Open the extensions manager in [!INCLUDE [azure-data-studio-short](../includes/azure-data-studio-short.md)]. You can either select the extensions icon or select **Extensions** in the View menu.

    :::image type="content" source="media/azure-sql-migration-extension/extension-icon.png" alt-text="Screenshot showing the migration extension icon.":::

1. Type in *Azure SQL Migration* in the search bar.

1. Select the **Azure SQL Migration** extension and view its details.

1. Select **Install**.

    :::image type="content" source="media/azure-sql-migration-extension/azure-sql-migration-extension-market-place.png" alt-text="Screenshot showing the Azure SQL migration extension from the Azure Marketplace.":::

1. You can see the Azure SQL migration extension in the extension list once installed.

    :::image type="content" source="media/azure-sql-migration-extension/azure-sql-migration-icon.png" alt-text="Screenshot showing the Azure SQL migration extension.":::

1. You can connect to the SQL Server instance in [!INCLUDE [azure-data-studio-short](../includes/azure-data-studio-short.md)]. Right-click the instance name and select **Manage** to see the dashboard and the **Azure SQL Migration** extension landing page.

    :::image type="content" source="media/azure-sql-migration-extension/azure-sql-migration-extension-landing-page.png" alt-text="Screenshot showing the extension landing page." lightbox="media/azure-sql-migration-extension/azure-sql-migration-extension-landing-page.png":::

### Set up auto update for the extension

[!INCLUDE [auto-update-extension](includes/auto-update-extension.md)]

### [Disconnected mode](#tab/disconnected)

### Download installation files

To install the Azure SQL migration extension on a disconnected computer, you must manually download [!INCLUDE [azure-data-studio-short](../includes/azure-data-studio-short.md)], the Azure SQL migration extension VSIX file, and the SQL tool service binaries, on a machine connected to the Internet, and then copy the file to the disconnect machine.

1. Download [!INCLUDE [azure-data-studio-short](../includes/azure-data-studio-short.md)] for the disconnected machine, from [Download and install Azure Data Studio](../download-azure-data-studio.md), and take note of the platform.

1. Download the latest Azure SQL migration extension VSIX file from the following location: [https://sqlopsextensions.blob.core.windows.net/extensions/sql-migration/sql-migration-1.5.4.vsix](https://sqlopsextensions.blob.core.windows.net/extensions/sql-migration/sql-migration-1.5.4.vsix).

   > [!NOTE]  
   > You can change the version number, which is `1.5.4` in this example, if you download a later version.

1. Download the required SQL tool service binaries. Follow this step after you install the Azure SQL migration extension on your disconnected machine.

   1. On the disconnected machine, open the following path:

      ```output
      %USERPROFILE%\.azuredatastudio\extensions\microsoft.sql-migration-1.5.4
      ```

      > [!NOTE]  
      > You can change the version number, which is `1.5.4` in this example, if you download a later version.

   1. Open the `config.json` file to find the version number for SQL tool service binaries to be downloaded. For example:

      ```json
      "version": "4.12.0.4"
      ```

   1. Visit the releases tab of the GitHub repository using this version number. For example, <https://github.com/microsoft/sqltoolsservice/releases/tag/4.12.0.4>.

   1. Depending upon the disconnected machine platform, download the `Microsoft.SqlTools.Migration` zip file. For example:

      - For 64-bit Windows (x64), download the file named `Microsoft.SqlTools.Migration-win-x64-net7.0.zip`
      - For 32-bit Windows (x86), download the file named `Microsoft.SqlTools.Migration-win-x86-net7.0.zip`

### Install Azure Data Studio and Azure SQL migration extension offline

1. Copy the three files you downloaded, to the disconnected machine where you want to run [!INCLUDE [azure-data-studio-short](../includes/azure-data-studio-short.md)].

1. Install [!INCLUDE [azure-data-studio-short](../includes/azure-data-studio-short.md)].

1. To install the Azure SQL migration extension, open [!INCLUDE [azure-data-studio-short](../includes/azure-data-studio-short.md)] and navigate to **File** > **Install Extension from VSIX package**. Locate the VSIX file you copied to the disconnected machine.

1. On the disconnected machine, navigate to the following path:

   ```output
   %USERPROFILE%\.azuredatastudio\extensions\microsoft.sql-migration-1.5.4
   ```

   > [!NOTE]  
   > You can change the version number, which is `1.5.4` in this example, if you download a later version.

1. Create folders in the path to add the following subdirectories: `\migrationService\windows\4.12.0.4\`. Your folder structure should look similar to the following example:

   ```output
   %USERPROFILE%\.azuredatastudio\extensions\microsoft.sql-migration-1.5.4\migrationService\Windows\4.12.0.4
   ```

   > [!NOTE]  
   > You can change both the version number (which is `4.12.0.4` in this example) and platform (which is `windows` in this example), to match the version and platform downloaded the previous steps.

1. Extract the zipped `Microsoft.SqlTools.Migration` file under the above mentioned path.

1. Restart [!INCLUDE [azure-data-studio-short](../includes/azure-data-studio-short.md)].

---

## Features

### Azure SQL target readiness assessment and database migrations

The Azure SQL migration extension supports assessment and generates Azure recommendations (Preview) and database migrations for the following Azure SQL targets.

- SQL Server on Azure Virtual Machines
- Azure SQL Managed Instance
- Azure SQL Database

### Migration modes

The following migration modes are supported for the corresponding Azure SQL targets.

| Migration mode | Description |
| --- | --- |
| **Online** | The source SQL Server database is available for reading and writing activity, while database backups are continuously restored on target Azure SQL. Application downtime is limited to the duration of the cutover at the end of migration. |
| **Offline** | The source database can't be used for writing activity while backup files are restored on the target Azure SQL database. Application downtime persists from the start until the completion of the migration process. |

### Support matrix

| Azure SQL target | Migration mode |
| --- | --- |
| Azure SQL Managed Instance | [Online](/azure/dms/tutorial-sql-server-managed-instance-online-ads) / [Offline](/azure/dms/tutorial-sql-server-managed-instance-offline-ads) |
| SQL Server on Azure Virtual Machine | [Online](/azure/dms/tutorial-sql-server-to-virtual-machine-online-ads) / [Offline](/azure/dms/tutorial-sql-server-to-virtual-machine-offline-ads) |
| Azure SQL Database | [Offline](/azure/dms/tutorial-sql-server-azure-sql-database-offline-ads) |

> [!TIP]  
> For information on pre-requisites, features and migration workflow, see [Migration using Azure Data Studio](/azure/dms/migration-using-azure-data-studio)

### Get help from Microsoft support

You can raise a support request to get Microsoft support assistance if you encounter issues or errors with your database migrations using the Azure SQL migration extension.

Select the **New support request** button in the upper section of the extension. It automatically takes you to the Azure portal, where you can fill in the details and then submit a support request.

:::image type="content" source="media/azure-sql-migration-extension/extension-support.png" alt-text="Screenshot of Get help from Microsoft support for the extension." lightbox="media/azure-sql-migration-extension/extension-support.png":::

You can submit ideas/suggestions for improvement, and other feedback, including bugs, in the [Azure Community forum - Azure Database Migration Service](https://feedback.azure.com/d365community/forum/2dd7eb75-ef24-ec11-b6e6-000d3a4f0da0).

> [!NOTE]  
> You can also use the **Feedback** button if you have any suggestions or feedback to improve the extension.

## Related content

- [Database migrations using Azure Data Studio](/azure/dms/migration-using-azure-data-studio)
- [Download and install Azure Data Studio](../download-azure-data-studio.md)
- [Release notes for Azure Data Studio](../release-notes-azure-data-studio.md)
- [Extend the functionality of Azure Data Studio](add-extensions.md)
