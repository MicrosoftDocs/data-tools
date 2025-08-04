---
title: Modify Join Operators
description: "Modify join operators (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "joins [SQL Server], operators"
  - "modifying join operators"
  - "join operators"
---
# Modify join operators (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

By default, the [Query and View Designer Tools (Visual Database Tools)](query-and-view-designer-tools-visual-database-tools.md) joins tables using an equal sign (an equijoin), which matches values in the two join columns. If you want, you can change the operator used to compare values in the join columns.

## Modify join operators

1. In the [Diagram pane (Visual Database Tools)](diagram-pane-visual-database-tools.md), right-click the join line you want to modify, and then choose **Properties** from the shortcut menu.

1. In the Property window, select **Join Condition and Type** and select the **ellipses (...)** to the right of the property.

1. In the **Join** dialog box, select a new operator.

## Related content

- [Join tables automatically (Visual Database Tools)](join-tables-automatically-visual-database-tools.md)
- [Join tables manually (Visual Database Tools)](join-tables-manually-visual-database-tools.md)
- [Query with joins (Visual Database Tools)](query-with-joins-visual-database-tools.md)
