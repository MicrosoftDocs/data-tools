---
title: Install Local Help Documentation for SQL Server Management Studio
description: Install and manage local help documentation by using the Microsoft Help Viewer, and add, remove, update, and move Help content installed on your computer.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan
ms.date: 05/19/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---
# Install local help documentation for SQL Server Management Studio

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

By using the Microsoft Help Viewer, you can add, remove, update, and move the Help content that is installed on your computer for use with SQL Server Management Studio (SSMS).

To manage content on your local computer, you must sign in with an account that has administrator permissions.

## Install the Help Viewer

In order to manage content on your local computer, you must have the Help Viewer installed. The Help Viewer is a component available during installation.

To modify your SSMS installation to install the Help Viewer, see [Modify SQL Server Management Studio workloads, components, and language packs](modify.md).

## Change installation source

By default, Help Viewer installs content by using a Microsoft online service as the source. You generally shouldn't change your content source unless you work in an enterprise environment for which a system administrator has already installed content in another location.

### Change the content installation source

To open the Help Viewer, open SSMS and then select **Help > Add and Remove Help Content**.

1. On the **Manage Content** tab, choose the **Disk** option button.

   > [!NOTE]  
   > The **Disk** option isn't available if your administrator has prevented you from modifying the content installation source. For more information, see the [Help Viewer administrator guide](/visualstudio/help-viewer/administrator-guide).

1. Perform one of the following steps:

   - Enter the path of an `.msha` file or the URL of a service endpoint.

   - Choose the Browse (**...**) button to navigate to an `.msha` file.

   - In the list, choose the entry that was used most recently.

## Download and install content locally

If you download and install content on your local computer, you can view articles when you don't have an internet connection.

> [!IMPORTANT]  
> To install content, you must log on with an account that has administrative permissions.

> [!NOTE]  
> If SSMS is set to a language other than English, you can install English content, localized content, or both. However, no content appears if you install only the English version and the **Include English content in all navigation tabs and F1 requests** check box in the **Viewer Options** dialog box is cleared.

### Download and install content

1. Choose the **Manage Content** tab.

1. In the content list, choose the **Add** link next to the book or books that you want to download and install.

   The book is added to the **Pending changes** list, and the estimated size of the book or books that you specified appear below that list. Because some books share articles, the total download size of multiple books might be smaller than the result of adding together the sizes of every book that you specified.

1. Choose the **Update** button.

   The book or books that you specified are installed along with any updates for books that you already have on your computer. Installation times vary, but you can view the progress in the status bar.

## Remove local content

You can save disk space by removing unwanted content from your computer.

> [!IMPORTANT]  
> You must have administrative permissions to remove content.

> [!NOTE]  
> No content appears if SSMS is set to a language other than English, you remove localized content, and the **Include English content in all navigation tab and F1 requests** check box in the **Viewer Options** dialog box is cleared.

### Remove content

1. Choose the **Manage Content** tab.

1. In the content list, choose the **Remove** link next to the book or books that you want to remove.

   The book is added to the **Pending changes** list.

1. Choose the **Update** button.

   The book or books that you specified are removed from your computer.

## Update local content

The status bar indicates when updates to your installed content are available.

> [!IMPORTANT]  
> If you want the **Help Viewer** to automatically check for online updates, you must open the **Viewer Options** dialog box and then select the **Go online to check for content updates** check box.

### Update local content

- In the lower-right corner of the status bar, choose the **Click here to download now** link.

Update times can vary, but you can view the update progress in the status bar.

## Move local content

You can save disk space by moving installed content from your local computer to a network share or to another partition on your local computer.

> [!IMPORTANT]  
> To move content, you must log on with an account that has administrative permissions.

### Move content

1. On the **Manage Content** tab, choose the **Move** button under **Local Store Path**.

   The **Move Content** dialog box opens.

1. In the **To** text box, enter a different location for the content, and then choose the **OK** button.

1. Choose the **Close** button when the content has moved.

[!INCLUDE [support](../includes/support.md)]

## Related content

- [Microsoft Help Viewer](/visualstudio/help-viewer/overview)
- [Override Help Viewer defaults](/visualstudio/help-viewer/behavior-overrides)
