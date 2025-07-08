---
title: Export Registered Server Information
description: How to export registered server information in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.date: 07/08/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.exportregisteredservers.f1"
helpviewer_keywords:
  - "Registered Servers [SQL Server], exporting"
  - "exporting registered server information"
  - "transferring registered server information"
---

# Export registered server information in SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This article describes how to save and export registered server information in SQL Server Management Studio (SSMS), and distribute it to other colleagues or servers. You can use this export feature to present a consistent user interface on multiple computers.

Exporting and then importing registered server information lets you easily configure several computers with the same servers in Registered Servers. This is useful when managing a large number of servers from computers in several locations, or when you want to configure a less experienced user with basic connection settings.

> [!NOTE]  
> Server registrations that use SQL Server Authentication store passwords on a per-user basis. After you export and import the server registrations, you must enter the password for each server the first time you connect, storing the passwords in your list of registered servers. This step isn't necessary for servers registered using Windows Authentication.

## Export registered server information

If the Registered Servers tool window isn't visible in SSMS, select **View** > **Registered Servers**, or type **Ctrl** + **Alt** + **G**.

1. In Registered Servers, right-click a server group, and then select **Tasks** > **Export...**.

   > [!NOTE]  
   > You can export an individual server, all of the registered server tree, or a subset of the registered server tree.

1. In the **Export Registered Servers** dialog box, specify the **Server group** to export. Export all registered servers, registered servers in a particular server group, or a single registered server to the export file.

   The export functionality is recursive; for example, if server group A contains server group B, and server group B contains server groups C and D, exporting server group A exports all entries in A, B, C, and D. The server group displays only the server groups of the current registered server tree.

1. Type the path and name of the export file in the **Export file** text box, or use the Browse button (**...**) to select a location on the client computer and name for the export file. Use the `.regsrvr` extension for the file.

   - If you select an existing file as your export file, the contents of the file are overwritten.

   - If you want your registered server information to be available to other users or another computer, you can save the file in a network location. Other users can access the file and import part or all of the registered server information.

1. To exclude user names when exporting the file, select the option **Do not include user names and passwords in the export file**.

   > [!IMPORTANT]  
   > Passwords in the export files are encrypted, but if user names and SQL Server Authentication passwords are included in the file, access to the file should be carefully controlled. User names and passwords are excluded from the export file by default.

## Related content

- [Import registered server information in SQL Server Management Studio](import-registered-server-information-sql-server-management-studio.md)
- [Create a new registered server in SQL Server Management Studio](create-a-new-registered-server-sql-server-management-studio.md)
