---
title: Create Self-Joins Automatically
description: "Create self-joins automatically (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "automatic joins"
  - "self-joins"
  - "joins [SQL Server], self"
---
# Create self-joins automatically (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

If a table has a reflexive relationship in the database, you can join it to itself automatically.

## Create a self-join automatically

1. Add to the [Diagram pane (Visual Database Tools)](diagram-pane-visual-database-tools.md) the table you want to work with.

1. Add the same table again, so that the Diagram pane shows the same table twice within the Diagram pane.

   The [Query and View Designer Tools (Visual Database Tools)](query-and-view-designer-tools-visual-database-tools.md) assigns an alias to the second instance by adding a sequential number to the table name. In addition, the Query and View Designer creates a join line between the two rectangles representing the two different ways the table participates in the query.

## Related content

- [Query with joins (Visual Database Tools)](query-with-joins-visual-database-tools.md)
