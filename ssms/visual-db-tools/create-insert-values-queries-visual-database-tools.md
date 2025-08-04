---
title: Create Insert Values Queries
description: "Create Insert Values queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "inserting values"
  - "queries [SQL Server], types"
  - "adding values"
  - "row additions [SQL Server], Insert Values query"
  - "inserting rows"
  - "Insert Values query"
  - "adding rows"
  - "table values [SQL Server]"
---
# Create Insert Values queries (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

You can create a new row in the current table using an Insert Values query. When you create an Insert Values query, you specify:

- The database table to add the row to.

- The columns whose contents you want to add.

- The value or expression to insert into the individual columns.

For example, the following query adds a row to the `titles` table, specifying values for the title, type, publisher, and price:

```sql
INSERT INTO titles (title_id, title, type, pub_id, price)
VALUES ('BU9876', 'Creating Web Pages', 'business', '1389', '29.99');
```

When you create an Insert Values query, the Criteria pane changes to reflect the only options available for inserting a new row: the column name and the value to insert.

> [!CAUTION]  
> You can't undo the action of executing an Insert Values query. As a precaution, back up your data before executing the query.

## Create an Insert Values query

1. Add the table you want to update to the Diagram pane.

1. From the **Query Designer** menu point to **Change Type**, and then select **Insert Values**.

   > [!NOTE]  
   > If more than one table is displayed in the Diagram pane when you start the Insert Values query, the Query and View Designer displays the Choose Target Table for Insert Values dialog box to prompt you for the name of the table to update.

1. In the Diagram pane, select the check box for each column for which you want to supply new values. Those columns show in the Criteria pane. Columns are updated only if you add them to the query.

1. In the **New Value** column of the Criteria pane, enter the new value for the column. You can enter literal values, column names, or expressions. The value must match (or be compatible with) the data type of the column you're updating.

   > [!CAUTION]  
   > The Query and View Designer can't check that a value fits within the length of the column you're inserting. If you provide a value that is too long, it might be truncated without warning. For example, if a `name` column is 20 characters long but you specify an insert value of 25 characters, the last 5 characters might be truncated.

When you execute an Insert Values query, no results are reported in the [Results pane (Visual Database Tools)](results-pane-visual-database-tools.md). Instead, a message appears indicating how many rows were changed.

## Related content

- [Supported Query Types (Visual Database Tools)](supported-query-types-visual-database-tools.md)
- [Design queries and views how-to articles (Visual Database Tools)](design-queries-and-views-how-to-topics-visual-database-tools.md)
- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
