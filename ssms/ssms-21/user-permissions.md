---
title: User Permissions and SQL Server Management Studio
description: Learn how to install SQL Server Management Studio on a computer that has an earlier or later version of SQL Server Management Studio already installed.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan
ms.date: 11/12/2024
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
---
# User permissions and SQL Server Management Studio 21 Preview

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

For reasons of security, you should run SQL Server Management Studio (SSMS) as a typical user whenever possible.

> [!WARNING]  
> Be sure not to launch or run any SSMS solution that doesn't come from a trusted person or a trusted location.

You can do nearly everything in the SSMS application as a typical user. You need administrator permissions to complete the following tasks:

| Area | Task | For more information |
| --- | --- | --- |
| Installation | Initial installation and configuration of SSMS | [Install SQL Server Management Studio](../install/install.md) |
| Installation | Modify or update SSMS. Requires administrator permissions by default | [Update SQL Server Management Studio](../install/update.md), [Modify SQL Server Management Studio](../install/modify.md) |
| Help | Install, update, or remove local Help content. | [Install and manage local Help content](../install/local-help-content.md) |

## Run SSMS as an administrator

If you need to run SSMS as an administrator, here's how.

### Use the Start menu

1. Depending on the version of Windows you're using, perform one of the following steps:

   - In **Windows 10**, open the **Start** menu, and then scroll to **[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)]**.
   - In **Windows 11**, select the **Start** button, and then in the **Search** box, type **[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)]**.

1. Next, right-click **[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)]**, and then select **Run as administrator**.

   When SSMS starts, **(Administrator)** appears after the product name in the title bar, and **ADMIN** appears near the top right of the SSMS window, in the same area where **PREVIEW** appears if you're using a preview build of SSMS. You can select this button to view the **About** dialog.

### Modify the shortcut

You can also modify the application shortcut to always run with administrative permissions. Here's how.

#### [Windows 10](#tab/windows-10)

1. Open the **Start** menu, scroll to **[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)]**, and then select **More** > **Open file location**.

1. In **File Explorer**, locate the **[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)]** shortcut for the version that you're using. Then, right-click the shortcut and select **Send to** > **Desktop (create shortcut)**.

1. On the **Windows 10** desktop, right-click the **[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)]** shortcut, and then select **Properties**.

1. Select the **Advanced** button, and then select the **Run as administrator** check box.

1. Select **OK**, and then select **OK** again.

#### [Windows 11](#tab/windows-11)

1. Select the **Start** button, and then in the **Search** box, enter **[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)]**.

1. From the search results, right-click **[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)]**, and then select **Open file location**.

1. In **File Explorer**, locate the **[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)]** shortcut for the version that you're using. Then, right-click the shortcut and select **Show more options** > **Send to** > **Desktop (create shortcut)**.

1. On the **Windows 11** desktop, right-click the **[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)]** shortcut, and then select **Properties**.

1. Next, select the **Advanced** button, and then select the **Run as administrator** check box.

1. Select **OK** two times to close the dialog.

---

[!INCLUDE [support](../includes/support.md)]

## Related content

- [Install SQL Server Management Studio 21 Preview](../install/install.md)
- [Update SQL Server Management Studio 21 Preview](../install/update.md)
- [Modify SQL Server Management Studio 21 Preview components and language packs](../install/modify.md)
- [Uninstall or remove SQL Server Management Studio 21 Preview](../install/uninstall.md)
