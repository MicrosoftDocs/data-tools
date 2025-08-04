---
title: Table-Valued Object Properties
description: "Table-valued object properties (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
f1_keywords:
  - "vdt.designers.properties.TVO"
---
# Table-valued object properties (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

These properties appear in the Properties window when you select a table-valued object in **Query and View Designer**. The table-valued object could be a view, synonym, derived table, or table-valued function. Unless otherwise noted, these properties are read-only in the **Properties** window.

The properties in this article are ordered by category rather than alphabet.

> [!NOTE]  
> The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition. To change your settings, choose **Import and Export Settings** on the **Tools** menu.

#### Identity Category

Expands to show the **Name** and **TVO Type** properties.

#### Name

Shows the name of the selected table-valued object.

#### TVO Type

Shows which type of table-valued object. It can be either a base table, view, table-valued function, or a derived table.

#### Query DesignerCategory

Expands to show properties for **Alias**, **Column List**, **Full Name**, and **Parameter List**.

#### Alias

Shows the alias for the selected table-valued object. To add or change an alias, type it into the field.

#### Column List

Shows the columns included in the selected table-valued object. To see them in a separate window, select Column List and then select the ellipses (`...`) to the right of the property.

#### Full Name

Shows the name of the selected table-valued object, including additional information such as the schema or data source of the object.

#### Parameter List

Shows the parameters defined for selected table-valued function. To define a value for the parameters, select Parameter List and then select the ellipses (...) to the right of the property. In the Function Parameters dialog box, type in values. This property is only available when a table-valued function is selected.
