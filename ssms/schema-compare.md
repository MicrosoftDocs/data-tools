---
title: Schema Compare (Preview) in SQL Server Management Studio
description: Compare database schemas between databases, .dacpac files, and SQL database projects in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: drskwier, mbarickman
ms.date: 06/09/2026
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
---

# Schema Compare (preview) in SQL Server Management Studio

[!INCLUDE [SQL Server ASDB, ASDBMI, ASDW](includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

Schema Compare enables you to compare two database definitions. The source and target of the comparison can be any combination of connected database, SQL database project, or `.dacpac` file. After the comparison finishes, the results appear as a set of actions that make the target the same as the source. Differences between the database models are presented like a source control diff.

If the schema compare target is a SQL project or a database, you can update the target directly from the Schema Compare interface or generate an update script that has the same effect.

:::image type="content" source="media/schema-compare/schema-compare-window.png" alt-text="Screenshot of the Schema Compare window in SQL Server Management Studio showing a comparison between a source and target." lightbox="media/schema-compare/schema-compare-window.png":::

Schema Compare provides the following capabilities:

- Compare schemas between two `.dacpac` files, databases, or SQL database projects.
- View results as a set of actions to match a target against the source.
- Selectively exclude actions listed in results.
- Set options that control the scope of the comparison.
- Apply changes directly to the target, or generate a script to apply changes at a later time.
- Save the comparison as an `.scmp` file for reuse.

## Prerequisites

- [SQL Server Management Studio 22.7 or a later version](install/install.md)
- [Database DevOps workload](install/modify.md) (required only when comparing SQL database projects)

## Launch Schema Compare

You can open Schema Compare in SSMS from several entry points.

### Object Explorer

Right-click a database in **Object Explorer** and select **Tasks** > **Schema Compare (Preview)**. The selected database is automatically set as the source.

### Solution Explorer

Right-click a SQL database project in **Solution Explorer** and select **Schema Compare (Preview)**. The selected project is automatically set as the source.

> [!NOTE]
> To work with SQL database projects in Solution Explorer, you need the [Database DevOps workload](install/modify.md).

### Tools menu

On the **Tools** menu, select **Schema Compare (Preview)**. The Schema Compare window opens without a preset source or target.

## Select source and target

After Schema Compare opens, select the source and target for the comparison. Each can be a connected database, a `.dacpac` file, or a SQL database project.

:::image type="content" source="media/schema-compare/comparison-options.png" alt-text="Screenshot of the source and target selection options showing Database, Data-tier Application (.dacpac), and Database Project choices.":::

- **Database**: Connect to a running database instance. The source is the database definition that you want to use as the basis for changes to the target.
- **Data-tier Application (.dacpac)**: Browse to a compiled `.dacpac` file. A `.dacpac` contains a snapshot of a database schema.
- **Database Project**: Select an open SQL database project. Requires the [Database DevOps workload](install/modify.md).

The target is the database definition that you want to evaluate and potentially apply changes to.

## Run and review comparison

Select **Compare** in the toolbar to start the comparison process.

When the comparison finishes, the **Results** pane shows the structural differences between the source and target. The comparison results group all the differences by action, such as Delete, Change, or Add.

Each row identifies the object in the source or target schema (or both) and the action that the process takes on the target schema, to make the target object the same as the source object. If you rename an object or move it to a new schema, the source and target names are different. The source name appears in bold font to highlight the difference.

By default, the results list hides objects that are the same in both schemas or that aren't supported for update (for example, built-in objects). Select the appropriate filter buttons in the toolbar to show these objects.

To change the grouping preference, select the **Group Results** dropdown list in the toolbar. Select **Type** to group the results by object type, such as by tables, views, or stored procedures.

### Exclude differences

By default, the Update Target action includes all differences in its scope. To exclude differences that you don't want to synchronize, clear the Include column of each row. The row immediately grays out. When Schema Compare updates the target, it doesn't consider that row for any pending changes.

If an excluded row has dependent objects, such as a *Table* row referenced by a *View* row, the excluded row is disabled but its checkbox isn't cleared until you also uncheck all dependent rows. If you refactor a row, such as renaming or moving it to another schema, the checkbox is disabled for that row and its dependent child rows.

## Comparison options

Select **Options** in the toolbar to configure which objects are compared and what types of differences are ignored. Options include:

- Ignore whitespace
- Ignore partition schemes
- Ignore column order

You can also configure which object types are included in the comparison, such as tables, stored procedures, indexes, permissions, and user-defined types.

## Apply changes

To update the schema of the target, you have two options:

- **Apply**: Apply changes directly to the target database or project from the Schema Compare window.
- **Generate Script**: Generate a Transact-SQL script that captures the same changes, which you can review and run at a later time.

A generated script appears in the Transact-SQL Editor, where you can inspect and run it against a database.

## Save comparisons

You can save the comparison definition for Schema Compare as an `.scmp` file, known as a *schema compare file*. This file stores information about the comparison settings in XML and includes:

- Source and target connection information
- Comparison options
- Excluded object types

You can open an `.scmp` file in SSMS to run the same comparison again later, or to share the comparison with others.

## Related content

- [Schema comparison overview](/sql/tools/sql-database-projects/concepts/schema-comparison)
- [Database DevOps (preview) in SQL Server Management Studio](database-devops.md)
- [SQL database projects](/sql/tools/sql-database-projects/sql-database-projects)
