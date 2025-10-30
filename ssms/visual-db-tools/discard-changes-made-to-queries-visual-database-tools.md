---
title: Discard Changes Made to Queries
description: "Discard changes made to queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "reverting queries"
  - "queries [SQL Server], discarding changes"
  - "discarding query changes"
---
# Discard changes made to queries (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can discard changes made to a query definition prior to saving them. Once they have been saved, they can't be returned to a previous state.

> [!NOTE]  
> To undo a change you've made to values in the Results pane, press the **Esc** key before you move off of the record. If you move off of a record and receive a notice that the changes aren't committed to the database, you can also press the **Esc** key to revert to the previous value.

## Discard changes made to a query definition

1. With the query open in Query and View Designer, from the **File** menu, select **Close**.

1. In the **Microsoft SQL Server Management Studio** dialog box, select **No**.

   The query definition returns to the state it was in at the last save.

## Related content

- [Save queries (Visual Database Tools)](save-queries-visual-database-tools.md)
- [Design queries and views how-to articles (Visual Database Tools)](design-queries-and-views-how-to-topics-visual-database-tools.md)
- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
- [Work with data in the Results pane (Visual Database Tools)](work-with-data-in-the-results-pane-visual-database-tools.md)
