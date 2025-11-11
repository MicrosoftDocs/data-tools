---
title: Create and Update Tables
description: Create and update database tables.
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "Visual Database Tools [SQL Server], Table Designer"
  - "Table Designer, designing tables"
  - "opening tables"
  - "opening Table Designer"
  - "tables [SQL Server], opening"
  - "Table Designer, opening"
---

# Create and update database tables (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

The Table Designer is a visual tool where you design and visualize [database tables](/sql/relational-databases/tables/tables). To create, edit, or delete tables, columns, keys, indexes, relationships, and constraints, use the Table Designer in [SQL Server Management Studio (SSMS)](../sql-server-management-studio-ssms.md).

## Create a table

1. Right-click the **Tables** node in your database and select **New** > **Table** in SSMS, or **New Table** in ADS.
1. Add [columns](column-properties-visual-database-tools.md) to your table, specifying name, data type, and whether `NULL` values are allowed for each column.
1. In SSMS, close the designer and specify a table name to save your changes.

## Update a table

1. Right-click the table under the **Tables** node of your database and select **Design**.
1. Update the desired table settings.
1. Close the designer and save your changes.

## Permissions

In order to create a table, you must have `CREATE TABLE` permissions in the database and `ALTER` permission on the schema in which the table is being created. For more information, see [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql).

To alter a table, you must have `ALTER` permissions on the table. For more information, see [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).

## Related content

- [Tables](/sql/relational-databases/tables/tables)
- [Table properties (Visual Database Tools)](table-properties-visual-database-tools.md)
- [Column Properties (Visual Database Tools)](column-properties-visual-database-tools.md)
- [Add Columns to a Table (Database Engine)](/sql/relational-databases/tables/add-columns-to-a-table-database-engine)
- [Primary and foreign key constraints](/sql/relational-databases/tables/primary-and-foreign-key-constraints)
- [Indexes](/sql/relational-databases/indexes/indexes)
- [Data types (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql)
- [Create a database and add tables in Visual Studio](/visualstudio/data-tools/create-a-sql-database-by-using-a-designer)
