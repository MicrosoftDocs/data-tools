---
title: Create Table Aliases
description: "Create table aliases (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "table aliases [SQL Server]"
  - "aliases [SQL Server], tables"
---
# Create table aliases (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

Aliases can make it easier to work with table names. Using aliases is helpful when:

- You want to make the statement in the [SQL Pane (Visual Database Tools)](sql-pane-visual-database-tools.md) shorter and easier to read.

- You refer to the table name often in your query - such as in qualifying column names - and want to be sure you stay within a specific character-length limit for your query. (Some databases impose a maximum length for queries.)

- You're working with multiple instances of the same table (such as in a self-join) and need a way to refer to one instance or the other.

For example, you can create an alias `"e"` for a table name `employee_information`, and then refer to the table as `"e"` throughout the rest of the query.

## Create an alias for a table or table-valued object

1. Add the table or table-valued object to your query.

1. In the **Diagram Pane**, right-click the object for which you want to create an alias, then select **Properties** from the shortcut menu.

1. In the **Properties** window, enter the alias in the **Alias** field.

## Related content

- [Add tables to queries (Visual Database Tools)](add-tables-to-queries-visual-database-tools.md)
- [Sort and group query results (Visual Database Tools)](sort-and-group-query-results-visual-database-tools.md)
- [Summarize query results (Visual Database Tools)](summarize-query-results-visual-database-tools.md)
- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
