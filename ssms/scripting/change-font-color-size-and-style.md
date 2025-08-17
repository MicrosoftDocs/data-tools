---
title: "Change Font Color, Size, and Style"
description: Learn how to change font color, size, and style for the SQL Server Management Studio editors. The color can be different for different text types (such as comments and statements).
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/15/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "size [SQL Server], fonts"
  - "modifying fonts"
  - "fonts [SQL Server Management Studio]"
  - "customizing fonts [SQL Server]"
  - "Query Editor [SQL Server Management Studio], managing fonts"
  - "text fonts [SQL Server Management Studio]"
---
# Change font color, size, and style

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

You can customize the way the text appears in the Editor and other places in [!INCLUDE [ssManStudioFull](../includes/ssmanstudiofull-md.md)].

## Change font color, size, and style in the Editor

1. Select **Options** on the **Tools** menu. Select **Environment**, and then select **Fonts and Colors**.

1. In the **Show settings for** list, select **Text Editor**.

1. Change the font, size, display item, foreground, and background colors.

> [!NOTE]  
> Select **Use Defaults** to return to the default settings.

There's only one font setting for the Editor and it affects all editors in SQL Server Management Studio. You can change the color based on the text type (such as comments and statements). Monospace fonts appear in bold in the Font list, and you can apply bold settings on a per-text-type basis. For example, you can format comments and operators bold, and the other text types are unaffected.

The settings for text color and font type are global for all text element types, such as comments, strings, and so on.

## Related content

- [Print Code and Results](print-code-and-results.md)
- [Color coding in query editors](color-coding-in-query-editors.md)
