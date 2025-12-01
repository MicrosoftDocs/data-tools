---
title: "Options (Designers - Maintenance Plans Page)"
description: "Options (Designers - Maintenance Plans page)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/01/2025
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "VS.ToolsOptionsPages.Designers.MaintenancePlans"
---
# Options (Designers - Maintenance Plans page)

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

Use the **Options** dialog box to determine the default behavior of the designer when new shapes are added to the design surface. On the **Tools** menu, go to **Options** > **Designers** > **Maintenance Plans**.

## UI element list

#### Connect a new shape to the selected shape by default

When this check box is selected, new shapes automatically connect to other shapes when they're added to the design surface. When this check box is cleared, new shapes aren't connected when they're added. Selecting this check box enables the following boxes.

#### Specify the connection of the new shape

Select from this dropdown list box to designate the default for the type of connection made between shapes. The choices are:

- **Use a Success constraint for new shape**
- **Use a Failure constraint for new shape**
- **Use a Completion constraint for new shape**

#### Specify the location of the new shape

Select from this dropdown list box to designate the default location where a new shape is added to the design surface. The choices are:

- **Add the new shape to the left of the selected shape**
- **Add the new shape to the right of the selected shape**
- **Add the new shape above the selected shape**
- **Add the new shape below the selected shape**
