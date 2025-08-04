---
title: Select Rows That Do Not Match a Value
description: "Select rows that do not match a value (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "search conditions [SQL Server], rows not matching value"
  - "row not matching value [SQL Server]"
  - "NOT operator [Visual Database Tools]"
  - "search criteria [SQL Server], rows not matching value"
---
# Select rows that don't match a value (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

To find rows that don't match a value, use the `NOT` operator.

## Find rows that don't match a value

1. If you haven't done so already, add the columns or expressions that you want to use within your search condition to the [Criteria Pane (Visual Database Tools)](criteria-pane-visual-database-tools.md).

1. Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter the `NOT` operator followed by a search value.

For example, to find all the rows in a `products` table where the values in the product code column begin with a character other than "A," you can enter a search condition such as the following:

```sql
NOT LIKE 'A%'
```

## Related content

- [Rules for entering search values (Visual Database Tools)](rules-for-entering-search-values-visual-database-tools.md)
- [Specify search criteria (Visual Database Tools)](specify-search-criteria-visual-database-tools.md)
