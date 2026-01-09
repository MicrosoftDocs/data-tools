---
title: Design Database Diagrams
description: "Design database diagrams (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
f1_keywords:
  - "65536"
helpviewer_keywords:
  - "Database Diagram Designer"
  - "Visual Database Tools [SQL Server], database diagrams"
  - "database diagrams [SQL Server], designing"
  - "diagrams [SQL Server], designing"
---

# Design database diagrams (Visual Database Tools)

[!INCLUDE [SQL Server Azure SQL Database PDW](../includes/applies-to-version/sql-asdb-asdbmi-pdw.md)]

The Database Designer is a visual tool that allows you to design and visualize a database to which you're connected. When designing a database, you can use Database Designer to create, edit, or delete tables, columns, keys, indexes, relationships, and constraints. To visualize a database, you can create one or more diagrams illustrating some or all of the tables, columns, keys, and relationships in it.

:::image type="content" source="media/design-database-diagrams-visual-database-tools/table-relationships.png" alt-text="Diagram showing table relationships in a database.":::

For any database, you can create as many database diagrams as you like; each database table can appear on any number of diagrams. Thus, you can create different diagrams to visualize different portions of the database, or to accentuate different aspects of the design. For example, you can create a large diagram showing all tables and columns, and you can create a smaller diagram showing all tables without showing the columns.

Each database diagram you create is stored in the associated database.

## Tables and columns in a database diagram

Within a database diagram, each table can appear with three distinct features: a title bar, a row selector, and a set of property columns.

#### Title bar

The title bar shows the name of the table.

If you have modified a table and haven't yet saved it, an asterisk (*) appears at the end of the table name to indicate unsaved changes. For information about saving modified tables and diagrams, see [Work with database diagrams](work-with-database-diagrams-visual-database-tools.md)

#### Row selector

You can select the row selector to select a database column in the table. The row selector displays a key symbol if the column is in the table's primary key. For information about primary keys, see [Primary and foreign key constraints](/sql/relational-databases/tables/primary-and-foreign-key-constraints).

#### Property columns

The set of property columns is visible only in the certain views of your table. You can view a table in any of five different views to help you manage the size and layout of your diagram.

For more information about table views, see [Customize the amount of information displayed in diagrams](customize-the-amount-of-information-displayed-in-diagrams-visual-database-tools.md).

## Relationships in a database diagram

Within a database diagram, each relationship can appear with three distinct features: endpoints, a line style, and related tables.

#### Endpoints

The endpoints of the line indicate whether the relationship is one-to-one or one-to-many. If a relationship has a key at one endpoint and a figure-eight at the other, it's a one-to-many relationship. If a relationship has a key at each endpoint, it's a one-to-one relationship.

#### Line style

The line itself (not its endpoints) indicates whether the Database Management System (DBMS) enforces referential integrity for the relationship when new data is added to the foreign-key table. If the line appears solid, the DBMS enforces referential integrity for the relationship when rows are added or modified in the foreign-key table. If the line appears dotted, the DBMS doesn't enforce referential integrity for the relationship when rows are added or modified in the foreign-key table.

#### Related tables

The relationship line indicates that a foreign-key relationship exists between one table and another. For a one-to-many relationship, the foreign-key table is the table near the line's figure-eight symbol. If both endpoints of the line attach to the same table, the relationship is a reflexive relationship. For more information, see [Draw reflexive relationships](draw-reflexive-relationships-visual-database-tools.md).

## In this section

- [Understand database diagram ownership](understand-database-diagram-ownership-visual-database-tools.md)
- [Navigate in Database Diagram Designer](navigate-in-database-diagram-designer-visual-database-tools.md)
- [Set up Database Diagram Designer](set-up-database-diagram-designer-visual-database-tools.md)
- [Upgrade database diagrams from previous editions](upgrade-database-diagrams-from-previous-editions-visual-database-tools.md)
- [Open Database Diagram Designer](open-database-diagram-designer-visual-database-tools.md)

## Related content

- [Work with database diagrams (Visual Database Tools)](work-with-database-diagrams-visual-database-tools.md)
- [Work with tables in database diagrams (Visual Database Tools)](work-with-tables-in-database-diagram-visual-database-tools.md)
- [Work with diagram layout (Visual Database Tools)](work-with-diagram-layout-visual-database-tools.md)
