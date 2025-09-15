---
title: "Choose Toolbox Items (Maintenance Tasks Page)"
description: "Choose Toolbox Items (Maintenance Tasks Page)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/15/2025
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "vs.chooseitems.maintenance_tasks"
  - "VS.ToolboxPages.Maintenance_Tasks"
helpviewer_keywords:
  - "Customize Toolbox dialog box"
---
# Choose toolbox items (Maintenance Tasks page)

[!INCLUDE [SQL Server Azure SQL Database Azure SQL Managed Instance Synapse Analytics PDW Fabric SE Fabric DW Fabric SQL DB](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw-fabricse-fabricdw-fabricsqldb.md)]

This tab of the **Customize Toolbox** dialog box displays a list of all maintenance task components registered on your computer and makes it possible for you to change the ones that are displayed in the Toolbox. You can open the **Customize Toolbox** dialog box from the **Tools** menu. To sort the list of components, select any column heading.

## Maintenance tasks

The **Maintenance Tasks** tab includes the following columns of information.

#### Name

Displays the names of available components. Preceding each name is a check box. If selected, a check box indicates that SQL Server Management Studio has found an entry for the component in your computer's registry. The component is either already displayed on the active **Toolbox** tab, or it is added when you select **OK**. If cleared, a check box indicates that the component isn't currently displayed in the **Toolbox**, or that it is removed from the **Toolbox** when you select **OK**.

#### Path

Displays the full path to the component. To identify the default components that shipped with the product, sort on this column and then locate the components stored on the Visual Studio installation path.

#### Last Modified

Displays the date when the component was last modified.

Select a name to show the attributes of the component in the **Language** and **Version** boxes, along with the icon.

#### Language

The language of the component.

#### Version

The version of the component.
