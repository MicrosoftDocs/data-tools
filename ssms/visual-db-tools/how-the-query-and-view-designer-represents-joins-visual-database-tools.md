---
title: How the Query and View Designer Represents Joins
description: "How the Query and View Designer represents joins (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "SQL pane [Visual Database Tools]"
  - "joins [SQL Server], Query and View Designer"
  - "Diagram pane [Visual Database Tools]"
---
# How the Query and View Designer represents joins (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

If tables are joined, the [Query and View Designer Tools (Visual Database Tools)](query-and-view-designer-tools-visual-database-tools.md) represents the join graphically in the [Diagram pane (Visual Database Tools)](diagram-pane-visual-database-tools.md) and by using SQL syntax in the [SQL Pane (Visual Database Tools)](sql-pane-visual-database-tools.md).

## Diagram pane

In the Diagram pane the Query and View Designer displays a join line between the data columns involved in the join. The Query and View Designer displays one join line for each join condition. For example, the following illustration shows a join line between two tables that are joined:

:::image type="content" source="media/how-the-query-and-view-designer-represents-joins-visual-database-tools/relationship-two-tables.png" alt-text="Diagram of join line showing relationship between two tables.":::

If tables are joined using more than one join condition, the Query and View Designer displays multiple join lines, as in the following example:

:::image type="content" source="media/how-the-query-and-view-designer-represents-joins-visual-database-tools/join-more-than-one.png" alt-text="Diagram of tables joined using more than one join condition.":::

If the joined data columns aren't displayed (for example, the rectangle representing the table or table-structured object is minimized or the join involves an expression), the Query and View Designer places the join line at the title bar of the rectangle representing the table or table-structured object.

The shape of the icon in the middle of the join line indicates how the tables or table-structured objects are joined. If the join clause uses an operator other than equal (=), the operator appears in the join line icon. The following table lists the icons that appear in the join line.

| Join line icon | Description |
| --- | --- |
| :::image type="icon" source="media/how-the-query-and-view-designer-represents-joins-visual-database-tools/join-inner.png" border="false"::: | Inner join (created using equal `=` sign). |
| :::image type="icon" source="media/how-the-query-and-view-designer-represents-joins-visual-database-tools/join-inner-greater.png" border="false"::: | Inner join based on the "greater than" `>` operator. |
| :::image type="icon" source="media/how-the-query-and-view-designer-represents-joins-visual-database-tools/join-outer-left.png" border="false"::: | Outer join in which all rows from the table represented on the left are included, even if they don't have matches in the related table. |
| :::image type="icon" source="media/how-the-query-and-view-designer-represents-joins-visual-database-tools/join-outer-right.png" border="false"::: | Outer join in which all rows from the table represented on the right are included, even if they don't have matches in the related table. |
| :::image type="icon" source="media/how-the-query-and-view-designer-represents-joins-visual-database-tools/join-outer-full.png" border="false"::: | A full outer join in which all rows from both tables are included, even if they don't have matches in the related table. |

The symbols on the ends of the join line indicate the type of join. The following table lists the types of joins and the icons displayed on the ends of the join line.

| Icon on ends of join line | Type of join |
| --- | --- |
| :::image type="icon" source="media/how-the-query-and-view-designer-represents-joins-visual-database-tools/join-one-to-one.png" border="false"::: | One-to-one join. |
| :::image type="icon" source="media/how-the-query-and-view-designer-represents-joins-visual-database-tools/join-one-to-many.png" border="false"::: | One-to-many join. |
| :::image type="icon" source="media/how-the-query-and-view-designer-represents-joins-visual-database-tools/join-cannot-determine.png" border="false"::: | Query and View Designer can't determine the join type. This situation occurs most often when you have created a join manually. |

## SQL pane

A join can be expressed in a number of ways in a SQL statement. The exact syntax depends on the database you're using and on how you have defined the join.

Syntax options for joining tables include:

- `JOIN` qualifier for the `FROM` clause.   The keywords INNER and `OUTER` specify the join type. This syntax is standard for ANSI 92 SQL.

  For example, if you join the `publishers` and `pub_info` tables based on the `pub_id` column in each table, the resulting SQL statement might look like this:

  ```sql
  SELECT * FROM publishers
  INNER JOIN pub_info ON publishers.pub_id = pub_info.pub_id;
  ```

  If you create an outer join, the words `LEFT OUTER` or `RIGHT OUTER` appear in place of the word INNER.

- `WHERE` clause compares columns in both tables. A `WHERE` clause appears if the database doesn't support the `JOIN` syntax (or if you entered it yourself). If the join is created in the `WHERE` clause, both table names appear in the `FROM` clause.

  For example, the following statement joins the `publishers` and `pub_info` tables.

  ```sql
  SELECT * FROM publishers, pub_info
  WHERE publishers.pub_id = pub_info.pub_id;
  ```

## Related content

- [Query with joins (Visual Database Tools)](query-with-joins-visual-database-tools.md)
