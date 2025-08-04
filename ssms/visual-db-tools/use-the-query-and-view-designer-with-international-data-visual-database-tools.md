---
title: Use the Query and View Designer with International Data
description: "Use the Query and View Designer with International Data (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "Visual Database Tools [SQL Server], international data"
  - "queries [SQL Server], international data"
  - "languages [SQL Server], Query and View Designer"
  - "international considerations [SQL Server], Query and View Designer"
  - "Criteria pane"
  - "View Designer, international data"
  - "Query Designer [SQL Server], international data"
  - "localized information in Query and View Designer [SQL Server]"
  - "global considerations [SQL Server], Query and View Designer"
  - "SQL pane [Visual Database Tools]"
  - "multiple language support [SQL Server], Query and View Designer"
---
# Use the Query and View Designer with international data (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can use the [Query and View Designer Tools (Visual Database Tools)](query-and-view-designer-tools-visual-database-tools.md) with data in any language and in any version of the Windows operating system. The following guidelines outline the differences you notice and provide information about managing data in international applications.

## Localized information in the Criteria and SQL panes

If you're using the Criteria pane to create your query, you can enter information in the format that corresponds to the Windows Regional Settings for you computer. For example, if you're searching for data, you can enter the data in the Criteria columns using whatever format you're accustomed to using, with these exceptions:

- Long data formats aren't supported.

- Currency symbols shouldn't be entered in the Criteria pane.

- Currency symbols don't display in the Results pane.

  > [!NOTE]  
  > In the Results pane, you can actually enter the currency symbol that corresponds to the Windows Regional Settings for your computer, but the symbol is removed and doesn't display in the Results pane.

- Unary minus always appears on the left side (for example, `-1`) regardless of the Regional Settings options.

In contrast, data and keywords in the SQL pane must always be in ANSI (U.S.) format. For example, as the Query and View Designer builds a query, it inserts the ANSI form of all SQL keywords such as `SELECT` and `FROM`. If you add elements to the statement in the SQL pane, be sure to use the ANSI standard form for the elements.

When you enter data using local-specific format in the Criteria pane, the Query and View Designer automatically translates it to ANSI format in the SQL pane. For example, if your Regional Settings are set to Standard German, you can enter data in the Criteria pane in a format such as "31.12.96." However, the date appears in the SQL pane in ANSI datetime format as `{ ts '1996-12-31 00:00:00' }.` If you enter data directly in the SQL pane, you must enter it in ANSI format.

## Sort order

The sort order of data in your query is determined by the database. Options that you set in the Windows Regional Settings dialog box don't affect sort order for queries. Within any particular query, however, you can request that rows be returned in a particular order.

## Use double-byte characters

You can enter DBCS characters for literals and for database object names such as table and view names or aliases. You can also use DBCS characters for parameter names and parameter marker characters. However, you can't use DBCS characters in SQL language elements such as function names or SQL keywords.

## Related content

- [Design queries and views how-to articles (Visual Database Tools)](design-queries-and-views-how-to-topics-visual-database-tools.md)
