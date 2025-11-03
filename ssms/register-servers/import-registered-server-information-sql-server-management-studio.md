---
title: Import Registered Server Information
description: Learn how to import saved registered server information in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.importregisteredservers.f1"
helpviewer_keywords:
  - "transferring registered server information"
  - "Registered Servers [SQL Server], importing"
  - "importing registered server information"
---

# Import registered server information in SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This article describes how to import saved registered server information in SQL Server Management Studio (SSMS). Exporting and then importing registered server files lets you easily configure several computers with the same servers in Registered Servers. This option is useful when managing a large number of servers from computers in several locations, or when you want to configure basic connection settings for a less experienced user.

> [!NOTE]  
> You can't import registered server information from earlier versions of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] than the version you're currently using.

If the Registered Servers tool window isn't visible in SSMS, select **View** > **Registered Servers**, or type **Ctrl**+**Alt**+**G**.

1. In Registered Servers, select the server type on the Registered Servers toolbar. The server type must be the same as the registered server export file type. For example, if you exported [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] registered server information, you must select **SQL Server** on the Registered Servers toolbar.

1. Right-click a server group, and select **Tasks** > **Import...**.

1. In the **Import Registered Servers** dialog, type the path and name of the import file in the **Import file** text box, or select the Browse button (**...**) to locate the import file. The import file can only be a previously exported registered server file. Registered server files have a `.regsrvr` extension.

1. Within the **Select the server group to import to** pane, select the root node, or a particular server group, to which the registered server entries in the file will be imported. The server group displays only the server groups of the current registered server tree.

   - You can import all registered servers, registered servers in a particular server group, or a single registered server to the export file.

   - The import functionality is recursive. For example, if server group `A` contains server group `B`, and server group `B` contains server groups `C` and `D`, importing server group `A` imports all entries in `A`, `B`, `C`, and `D`.

   - If you select to import an existing server group or server, a message confirms that you want to overwrite the existing server or server group.

Local server registrations that use [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Authentication store passwords on a per-user basis. After you import the server registrations, you must enter the password for each server the first time you connect, storing the passwords in your lists of registered servers. This isn't necessary for servers registered through Windows Authentication.

## Related content

- [Change a server's registration in SQL Server Management Studio](change-a-server-s-registration-sql-server-management-studio.md)
- [Export registered server information in SQL Server Management Studio](export-registered-server-information-sql-server-management-studio.md)
- [Create a new registered server in SQL Server Management Studio](create-a-new-registered-server-sql-server-management-studio.md)
