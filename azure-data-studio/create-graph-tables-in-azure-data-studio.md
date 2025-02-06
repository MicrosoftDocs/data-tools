---
title: Creating Graph Tables in Azure Data Studio
description: How to use the Table Designer to create graph tables
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest, maghan
ms.date: 02/06/2025
ms.service: azure-data-studio
ms.topic: tutorial
---

# Use the Table Designer to Create Graph Tables in Azure Data Studio

[!INCLUDE [azure-data-studio-deprecation](includes/azure-data-studio-deprecation.md)]

[!INCLUDE [sql-asdb-asmi](includes/applies-to-version/sql-asdb-asmi.md)]

Graph tables establish relationships between entities in your database using node and edge table relationships. In Azure Data Studio, you can easily create these relationships directly in the GUI without manually typing out long lines of T-SQL code. To learn more about graph tables, check out [this documentation on SQL Graph Architecture](/sql/relational-databases/graphs/sql-graph-architecture). The table type can be seen in the Connections Pane by the icon shown to the left of the table name. A single dot represents a node graph table, while the two unshaded dots represent edge graph tables, as shown below:

:::image type="content" source="media/create-graph-tables-in-azure-data-studio/table-designer-node-vs-edge.png" alt-text="Screenshot of Table Designer showing node and edge graph table types.":::

Creating a graph table is done directly in the Properties pane. A new table has to be created to create graph tables. Graph tables can't be implemented for existing tables.

In this example below, we use the table designer GUI to create two node tables: Person, City, and an edge table called "lives" with an edge constraint to establish the relationship between the two node tables (for example: **Person** ***lives in*** **City**). For a T-SQL script version of this example, see [Create a graph database and run some pattern matching queries using T-SQL](/sql/relational-databases/graphs/sql-graph-sample).

## Create the node tables

1. Create a table and name it ***City***. Before saving this new table, in the Table Properties pane, change the Graph Table option to **Node** from the dropdown.

    :::image type="content" source="media/create-graph-tables-in-azure-data-studio/table-designer-create-a-node-graph-table.png" alt-text="Screenshot of Table Designer showing how to create a Cities node graph table." lightbox="media/create-graph-tables-in-azure-data-studio/table-designer-create-a-node-graph-table.png":::

    The script is updated to include the "as node" syntax.

    Once this configuration is set, publish this update to the database. Once published, a new column for the node ID is created, and this ID is referenced in the script pane, as shown above.

1. Create another node table and name it ***Person***, with the same settings as above.

## Create the edge table

1. As mentioned earlier, we create our edge table, "lives." To do this, right-click on the Tables folder to create a new table. Change the name of this table from its default to "lives." To indicate that this is an edge table, select the Graph Table Type dropdown in the Table Properties pane and select "Microsoft Edge." See below.

    :::image type="content" source="media/create-graph-tables-in-azure-data-studio/table-designer-create-lives-edge-table.png" alt-text="Screenshot of Table Designer showing how to create an edge table." lightbox="media/create-graph-tables-in-azure-data-studio/table-designer-create-lives-edge-table.png":::

1. To create the relationship between the node and edge graphs, select "Microsoft Edge Constraints." Refer to the [edge constraints documentation](/sql/relational-databases/tables/graph-edge-constraints) to learn more about edge constraints. Select the plus sign next to "New Microsoft Edge Constraint" to create a new constraint. A default name for "EC-1" is provided, as seen below. Feel free to change the name for you, please. In this tutorial, we leave this as is.

    :::image type="content" source="media/create-graph-tables-in-azure-data-studio/table-designer-create-edge-constraint-without-clause.png" alt-text="Screenshot of Table Designer showing how to create edge constraint." lightbox="media/create-graph-tables-in-azure-data-studio/table-designer-create-edge-constraint-without-clause.png":::

1. As seen in the script pane in the image above, a warning indicates that a clause hasn't been specified. We must create the clause to establish the edge constraint between our ***Person*** and ***City*** node graph tables. On the "Microsoft Edge Constraint Properties" pane, under **Clauses**, select **+New Clause**. The ***From*** and ***To*** values will now appear in the clauses section. Hover over the **From Table** to view the dropdown, and select ***dbo.Persons*** and from the **To Table** drop-down, select ***dbo.City***. Be sure to publish changes to save your work. See below for the overview of what the Table Designer view should look like after performing the above steps.

    :::image type="content" source="media/create-graph-tables-in-azure-data-studio/table-designer-create-edge-constraint-with-clause.png" alt-text="Screenshot of Table Designer showing how to add clause to edge constraint." lightbox="media/create-graph-tables-in-azure-data-studio/table-designer-create-edge-constraint-with-clause.png":::

 You can add as few or as many constraints as needed depending on the nature of the relationships between the different tables in your database.

## Next step

> [!div class="nextstepaction"]
> [Download Azure Data Studio](./download-azure-data-studio.md)
