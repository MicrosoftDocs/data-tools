---
title: Use the Properties Window
titleSuffix: SQL Server Management Studio
description: Learn how to use the Properties window to see information about a SQL Server Management Studio item, such as a connection, and about database objects.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mbarickman
ms.date: 09/03/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "viewing properties"
  - "Properties window [SQL Server Management Studio]"
  - "complex properties [SQL Server Management Studio]"
ai-usage: ai-assisted
---
# Use the Properties window in SQL Server Management Studio

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

The **Properties** window shows the state of an item in [!INCLUDE [ssManStudioFull](../includes/ssmanstudiofull-md.md)], such as a connection or a Showplan operator. It also shows information about database objects, such as tables and views, and about designers.

Many properties in the **Properties** window are read-only, but you can change them in a different part of [!INCLUDE [ssManStudio](../includes/ssmanstudio-md.md)].

> [!NOTE]  
> If the **Properties** window isn't visible, select **Properties Window** on the **View** menu, or press <kbd>F4</kbd>.

## View the properties of an object

1. Select the object that you want to view.

1. Find the property in the **Properties** window.

## View the connection properties of a query window

The **Properties** window shows all the connection properties of the query window.

- Open a query window.

## View the properties of a Showplan operator

1. On the **Query** menu, select **Include Actual Execution Plan**.

1. In the query editor, enter a query and run it.

1. On the **Execution plan** tab, select an operator icon. The **Properties** window shows the properties of that operator.

## Related content

- [Properties window (SSMS)](../properties-window-management-studio.md)
- [Properties window F1 help (SSMS)](../menu-help/properties-window-f1-help-management-studio.md)
