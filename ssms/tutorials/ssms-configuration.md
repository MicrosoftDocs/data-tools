---
title: Components and Configuration
titleSuffix: SQL Server Management Studio
description: A tutorial that describes the components and basic configuration options for your SQL Server Management Studio environment.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mbarickman
ms.date: 09/03/2026
ms.service: sql-server-management-studio
ms.topic: tutorial
ms.collection:
  - data-tools
keywords:
  - SQL Server
  - SSMS
  - SQL Server Management Studio
---

# SQL Server Management Studio components and configuration

This tutorial describes the various window components in SQL Server Management Studio (SSMS), and a set of basic configuration options for your workspace. In this article, you learn how to:

> [!div class="checklist"]
> - Identify the components that make up the SSMS environment
> - Change the environment layout, and reset it to the default
> - Maximize the query editor
> - Change the font
> - Configure startup options

## Prerequisites

Install the latest version of [SQL Server Management Studio](../install/install.md).

## SQL Server Management Studio components

This section describes the various window components that are available in the workspace and how to use them.

- To close a window, select the **X** in the right corner of the title bar.
- To reopen a window, select the window in the **View** menu.

  :::image type="content" source="media/ssms-configuration/viewmenu.png" alt-text="Screenshot of the View menu.":::

- **Object Explorer** (<kbd>F8</kbd>): Object Explorer is a tree view of all the objects for a database or server. This view includes the databases of the SQL Server Database Engine, SQL Server Analysis Services, SQL Server Reporting Services, and SQL Server Integration Services. Object Explorer displays information for all servers to which there's a connection.

  :::image type="content" source="media/ssms-configuration/objectexplorer.png" alt-text="Screenshot of Object Explorer.":::

- **Query Window** (<kbd>Ctrl</kbd>+<kbd>N</kbd>): After you select **New Query**, enter your Transact-SQL (T-SQL) queries in this window. The results of your queries also appear in the Results pane.

  :::image type="content" source="media/ssms-configuration/newquery.png" alt-text="Screenshot of the New Query window." lightbox="media/ssms-configuration/newquery.png":::

- **Current connection properties** (<kbd>F4</kbd>): You can see the Current connection properties pane when the Query Window is open. The view displays properties for the connection. For example, it shows the Server name, the start time for the query last executed, the number of rows returned, and other connection details.

  :::image type="content" source="media/ssms-configuration/properties.png" alt-text="Screenshot of the configuration properties.":::

- **Template Browser** (<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>T</kbd>): The Template Browser has an extensive set of prebuilt T-SQL templates. You can use these templates to perform various functions, such as creating or backing up a database, or creating an index.

  :::image type="content" source="media/ssms-configuration/templates.png" alt-text="Screenshot of the template browser." lightbox="media/ssms-configuration/templates.png":::

- **Object Explorer Details** (<kbd>F7</kbd>): The details pane provides more granular information compared to Object Explorer. You can use the Object Explorer Details pane to manipulate multiple objects at the same time. For example, you can select multiple databases and then script them out simultaneously.

  :::image type="content" source="media/ssms-configuration/objectexplorerdetails.PNG" alt-text="Screenshot of Object Explorer Details.":::

## Change the environment layout

This section describes how to change the environment layout, such as how to move a window.

- To move a window, select and hold the title, and then drag the window.
- To pin or unpin a window, select the pushpin icon in the title bar:

  :::image type="content" source="media/ssms-configuration/pushpin.png" alt-text="Screenshot showing how to pin an object.":::

- Each window component has a dropdown list that you can use to manipulate the window in various ways:

  :::image type="content" source="media/ssms-configuration/windowoptions.png" alt-text="Screenshot of window options.":::

- When two or more query windows are open, you can separate them into multiple tab groups so that all the query windows are visible. Tab groups can be vertical or horizontal. To create a tab group, right-click the title of the query, and then select the tabbed option that you want:

  :::image type="content" source="media/ssms-configuration/querytabbedoptions.png" alt-text="Screenshot of query tab options.":::

  - Horizontal Tab Group:

    :::image type="content" source="media/ssms-configuration/horizontaltab.png" alt-text="Screenshot of an example of the Horizontal Tab Group.":::

  - Vertical Tab Group:

    :::image type="content" source="media/ssms-configuration/verticaltabgroup.png" alt-text="Screenshot of an example of the Vertical Tab Group.":::

    - To merge a query window into another tab group, right-click the query title, and then select **Move to Previous Tab Group** or **Move to Next Tab Group**:

      :::image type="content" source="media/ssms-configuration/mergetabgroups.png" alt-text="Screenshot of merging query tabs." lightbox="media/ssms-configuration/mergetabgroups.png":::

- To restore the default environment layout, in the **Window** menu, select **Reset Window Layout**:

  :::image type="content" source="media/ssms-configuration/resetwindowlayout.png" alt-text="Screenshot of restoring window layout.":::

## Maximize Query Editor

To maximize Query Editor to full-screen mode:

1. Select anywhere in the Query Editor window.

1. Press <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>Enter</kbd> to toggle between full-screen mode and regular mode.

This keyboard shortcut works with any document window.

## Change basic settings

This section describes how to modify some basic settings in SSMS from the **Tools** menu.

:::image type="content" source="media/ssms-configuration/tools.png" alt-text="Screenshot of the Tools menu.":::

- To modify a toolbar, select **Tools** > **Customize**, or right-click the toolbar and select **Customize...**:

  :::image type="content" source="media/ssms-configuration/toolbar.png" alt-text="Screenshot of customizing a toolbar." lightbox="media/ssms-configuration/toolbar.png":::

  - Use the **Toolbars** pane to enable or disable the toolbars displayed under the menu bar.

  - Use the **Commands** pane to customize the icons displayed for a toolbar.

### Change the font

- To change the font for a window, select **Tools** > **Options** > **Fonts and Colors**:

  :::image type="content" source="media/ssms-configuration/fontsandcolors.png" alt-text="Screenshot of changing fonts and colors." lightbox="media/ssms-configuration/fontsandcolors.png":::

### Change startup options

- The startup options determine what your workspace looks like when you first open SSMS. To change startup options, select **Tools** > **Options** > **Startup**:

  :::image type="content" source="media/ssms-configuration/startup.png" alt-text="Screenshot of changing startup options.":::

## Related content

- [Quickstart: Connect and query a SQL Server instance using SQL Server Management Studio (SSMS)](../quickstarts/ssms-connect-query-sql-server.md)
- [Script objects in SQL Server Management Studio](scripting-ssms.md)
- [Use templates in SQL Server Management Studio](../template/templates-ssms.md)
- [Import and export settings for SQL Server Management Studio (SSMS)](import-export-settings.md)
- [Tips and tricks for using SQL Server Management Studio (SSMS)](ssms-tricks.md)
