---
title: "Color Coding in Query Editors"
description: Learn how text categories are color coded to help you more easily find specific text, and how you can configure a custom color scheme.
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/15/2025
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "Query Editor [SQL Server Management Studio], color coding"
  - "color coding [Query Editor]"
---

# Color coding in query editors

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

The text entered in the code editors is assigned a category; each category is identified by a color. The colors help you quickly find text in your code. For example, comments stand out in dark green. The following table lists the most common colors. You can view the whole list of colors and their categories, and configure a custom color scheme by using the **Tools** > **Options** menu. For more information about how to change the default colors, see [Change font color, size, and style](change-font-color-size-and-style.md).

## Default code colors

| Color | Category |
| --- | --- |
| Red | Transact-SQL string |
| Dark green | Comment |
| Black on silver background | `SQLCMD` command |
| Magenta | System function |
| Green | System table, view, or table-valued function. Also, the system schemas `sys` and `INFORMATION_SCHEMA`. |
| Blue | Keyword |
| Teal | Line numbers or template parameter |
| Maroon | [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] stored procedure |
| Dark gray | Operators |

## Status bar

You can configure registered servers or [!INCLUDE [ssDE](../includes/ssde-md.md)] servers in Object Explorer to have different colors in the [!INCLUDE [ssDE](../includes/ssde-md.md)] Query Editor status bar. This helps you identify which server each editor window is connected to when you have many windows open at the same time. For more information about setting status bar colors, see [Status Bar (Database Engine Query Editor)](status-bar-database-engine-query-editor.md).

Some types of editors don't display the status bar, or don't support multiple colors.
