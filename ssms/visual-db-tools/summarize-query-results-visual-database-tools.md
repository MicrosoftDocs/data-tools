---
title: Summarize Query Results
description: "Summarize query results (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "summarizing query results"
  - "queries [SQL Server], results"
  - "aggregate queries [SQL Server]"
---
# Summarize query results (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

When you create aggregate queries, certain logical principles apply. For example, you can't display the contents of individual rows in a summary query. The Query and View Designer helps you comply with these principles in the way the [Diagram pane (Visual Database Tools)](diagram-pane-visual-database-tools.md) and [Criteria Pane (Visual Database Tools)](criteria-pane-visual-database-tools.md) behave.

By understanding the principles of aggregate queries and the Query and View Designer's behavior, you can create logically correct aggregate queries. The overriding principle is that aggregate queries can result only in summary information. Thus, most of the principles that follow describe the ways that you can reference individual data columns within an aggregate query.

## In this section

| Article | Description |
| --- | --- |
| [Work with columns in aggregate queries (Visual Database Tools)](work-with-columns-in-aggregate-queries-visual-database-tools.md) | Describes concepts about grouping and summarizing columns with the `GROUP BY`, `WHERE`, and `HAVING` clauses. |
| [Count rows in a table (Visual Database Tools)](count-rows-in-a-table-visual-database-tools.md) | Provides steps for counting the number of rows in a table or the number of rows in a table that meet a set of criteria. |
| [Summarize or aggregate values for all rows in a table (Visual Database Tools)](summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md) | Provides steps for summarizing all rows rather than for a set of grouped rows. |
| [Summarize or aggregate values using custom expressions (Visual Database Tools)](summarize-or-aggregate-values-using-custom-expressions-visual-database-tools.md) | Provides steps for using expressions to summarize or aggregate rather than using the predefined clauses. |

## Related content

- [Design queries and views how-to articles (Visual Database Tools)](design-queries-and-views-how-to-topics-visual-database-tools.md)
