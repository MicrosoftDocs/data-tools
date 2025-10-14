---
title: Select Installation Locations for SQL Server Management Studio
description: Reduce the installation footprint of SQL Server Management Studio (SSMS) by changing the location of the download cache and components to different drives.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 05/19/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---
# Select installation locations for SQL Server Management Studio

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

You can reduce the installation footprint of SQL Server Management Studio (SSMS) on your system drive by changing the location of some of its files. Specifically, you can use a different location for the **download cache** and **shared components, tools, and SDKs**.

> [!NOTE]  
> There are some tools and SDKs that have different rules on where they can be installed. Such tools and SDKs are installed on your system drive even if you choose another location.

## Get started

1. When you install SSMS, choose the **Installation locations** tab.

1. The default path is shown in **Product**. If you accept the default path, the core product and files that are specific to this version of SSMS are installed in that location.

   If your system drive is a solid-state drive (SSD), we recommend that you keep the core product on your system drive. When you use SSMS, you can read from and write to a lot of files, which increases the disk I/O activity. It's best to choose your fastest drive to handle the load.

   > [!IMPORTANT]  
   > You can select a different location only when you first install SSMS. If you've already installed it and want to change the location, you must uninstall SSMS and then reinstall it.

1. In the **Download cache** section, decide whether you want to keep the download cache after installation, and if so, where you want to store its files.

   - Check or uncheck **Keep download cache after the installation**.

     If you decide not to keep the download cache, the download cache location is only temporarily used. This action doesn't affect or delete files from previous installations.

   - Specify the folder path, including the drive, where you want to store the installation files and manifests from the download cache.

   > [!IMPORTANT]  
   > You can select a different location only when you first install SSMS. If you've already installed it and want to change the location, you must uninstall SSMS and then reinstall it.

1. In the **Shared components, tools, and SDKs** section, select the folder where you want to store the files that are shared by side-by-side SSMS installations. SDKs and tools are also stored in this directory.

   > [!IMPORTANT]  
   > If you've installed SSMS or Visual Studio on your computer before, you won't be able to change the **Shared components, tools, and SDKs** path and it will appear greyed out.

[!INCLUDE [support](../includes/support.md)]

## Related content

- [Install SQL Server Management Studio](install.md)
- [Update SQL Server Management Studio](update.md)
- [Modify SQL Server Management Studio workloads, components, and language packs](modify.md)
- [Uninstall or remove SQL Server Management Studio](uninstall.md)
