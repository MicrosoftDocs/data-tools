---
title: "User Assistance in SQL Server Management Studio"
description: "User Assistance in SQL Server Management Studio"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/15/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "Help [SQL Server Management Studio]"
  - "SQL Server Management Studio [SQL Server], user assistance"
---
# User assistance in SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

User assistance is available in [!INCLUDE [ssManStudioFull](includes/ssmanstudiofull-md.md)] through the Help menu and Microsoft Learn. The Help menu in [!INCLUDE [ssManStudio](includes/ssmanstudio-md.md)] offers several different routes to information about [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)]. It also provides access to [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] community and Microsoft Learn resources not previously available from within the Help environment. In addition, the Help environment is now configurable to launch either within the [!INCLUDE [ssManStudioFull](includes/ssmanstudiofull-md.md)] environment or in an associated external window of its own.

## The Help interface

The **Contents** and **Index** provide functionality and an interface already familiar to [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] users. The other options are:

- **How Do I**

  Provides a hierarchical set of linked pages containing useful articles related to common [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] tasks. The content is organized by component and task, for example, Replication articles, and so on.

- **Search**

  Searches for articles, with or without predefined filters. Search in [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] is a separate tabbed page. Users can refine their searches with one or more predefined article type, language, or technology filters. By default, Search doesn't use any of the predefined filters, and only articles in the installed collections are searched.

  Users can include online resources in their search by enabling online Help. For more information, see [Microsoft Learn and SQL Server communities](#microsoft-learn-and-sql-server-communities) later in this article.

- **Dynamic Help**

  Automatically displays links to relevant information while users work in the [!INCLUDE [ssManStudio](includes/ssmanstudio-md.md)] environment.

- **Help Favorites**

  Stores user article bookmarks for easy access later.

Help on Help (Microsoft Document Explorer Help) links users to the documentation about the Help Viewer, but the articles are in a collection separate from [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] Documentation. For information about the Help Viewer, select **Help on Help** from the Help menu of [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] Documentation.

## Microsoft Learn and SQL Server communities

Help in [!INCLUDE [ssManStudio](includes/ssmanstudio-md.md)] also provides users ways to contact Microsoft Learn and [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)]-focused communities on the Web for information. You can:

- Access [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] communities from the How Do I page.

- Search Microsoft Learn and [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] community sites.

### Access SQL Server-focused communities from the How Do I page

1. In [!INCLUDE [ssManStudioFull](includes/ssmanstudiofull-md.md)], on the **Help** menu, select **How Do I**.

1. The [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] **How Do I** page opens. In the Community Links sidebar, select the name of the community site you want to access.

   > [!NOTE]  
   > The computer running [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] must have a direct connection to the Web.

   Before you can search Microsoft Learn or the [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] communities, you must enable online search.

### Enable online search

1. On the **Tools** menu, select **Options**. In the **Options** dialog box, expand the **Environment** and **Help** nodes if necessary, and then select **Online**.

1. In the **When loading Help content** area, select an online option.

1. In the **Search these providers** list, select the search providers you want to search, and clear those you don't.

1. Select **OK**.

### Search Microsoft Learn and SQL Server-focused communities from the Search page

1. On the **Help** menu, select **Search**.

1. Enter your search terms in the **Search for** text box, and then select **Search**.

Whether or not you perform a search using the filters available (technology, language, and article type), your search is run against all the search providers you selected.

## Launch Help

There are two ways to display Help from [!INCLUDE [ssManStudioFull](includes/ssmanstudiofull-md.md)]. By default, when [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] Documentation is opened from within [!INCLUDE [ssManStudio](includes/ssmanstudio-md.md)], it opens in a document window external to the [!INCLUDE [ssManStudio](includes/ssmanstudio-md.md)] environment. This window is still associated with the [!INCLUDE [ssManStudio](includes/ssmanstudio-md.md)]; it can respond to some [!INCLUDE [ssManStudio](includes/ssmanstudio-md.md)] events; and when you close [!INCLUDE [ssManStudio](includes/ssmanstudio-md.md)], the documentation closes as well. Opening the documentation this way is useful when you're using two monitors; you can drag the documentation window to the second monitor, out of the way of work you're doing in the first one, but still easily referenced.

You can also open the documentation as a document window inside [!INCLUDE [ssManStudio](includes/ssmanstudio-md.md)]. This is preferable when you have limited screen space and want to take advantage of [!INCLUDE [ssManStudio](includes/ssmanstudio-md.md)] and its ability to hide windows.

> [!NOTE]  
> If you want the documentation to be independent of [!INCLUDE [ssManStudio](includes/ssmanstudio-md.md)], open [!INCLUDE [ssNoVersion](includes/ssnoversion-md.md)] Documentation from the **Start** menu, and it doesn't react to your actions in the [!INCLUDE [ssManStudio](includes/ssmanstudio-md.md)] environment, nor does it close if you exit [!INCLUDE [ssManStudio](includes/ssmanstudio-md.md)].

### Configure Help and SQL Server Documentation to launch inside the Management Studio window

1. On the **Tools** menu, select **Options**, expand **Environment**, expand **Help**, and then select **General**.

1. In the **Show Help Using** box, select **Integrated Help Viewer**.
