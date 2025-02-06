---
title: Creating Memory-Optimized Tables in Azure Data Studio
description: How to use the Table Designer to create memory-optimized tables
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest, maghan
ms.date: 02/06/2025
ms.service: azure-data-studio
ms.topic: tutorial
---

# Creating a Memory-Optimized Table

[!INCLUDE [azure-data-studio-deprecation](includes/azure-data-studio-deprecation.md)]

[!INCLUDE [sql-asdb-asmi](includes/applies-to-version/sql-asdb-asmi.md)]

Memory-optimized tables are a feature of SQL Server in which the entire table resides in memory. A second copy of the table data is maintained on disk. Data in memory-optimized tables is only read from disk during database recovery, such as after a server restart. Memory-optimized tables must belong to a filegroup and can be created in the table designer in Azure Data Studio. To read more on this, check out this documentation on [the memory-optimized filegroup](/sql/relational-databases/in-memory-oltp/the-memory-optimized-filegroup).

Memory-optimized tables must have a nonclustered primary key. For an introduction to memory-optimized Tables, check out the [Introduction to Memory-Optimized Tables](/sql/relational-databases/in-memory-oltp/introduction-to-memory-optimized-tables) article. Additionally, all memory-optimized tables must have at least one index.

## Create a memory-optimized table

1. To create a memory-optimized Table, we must ensure a filegroup has been created for our database. In the object explorer, open a new query editor window from the server level, as we'll create an entirely new database in which our memory-optimized table resides. In the query editor, copy, paste, and execute the following code:

    ```sql
        CREATE DATABASE imoltp
        GO
       --------------------------------------
        -- create database with a memory-optimized
        -- filegroup and a container.
    
        ALTER DATABASE imoltp ADD FILEGROUP imoltp_mod
         CONTAINS MEMORY_OPTIMIZED_DATA;
    
        ALTER DATABASE imoltp ADD FILE (
            name='imoltp_mod1', filename='c:\data\imoltp_mod1')
            TO FILEGROUP imoltp_mod;
    
        ALTER DATABASE imoltp
            SET MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT = ON;
        GO
        --
    ```

    The code above creates a new database, adds a filegroup to the database, adds a file to the filegroup, and finally sets the isolation level for any memory-optimized table added to this database to Snapshot.

1. Next, create your table by opening the **imoltp** database from the object explorer, right-clicking the **Tables** folder, and selecting **New Table**. This opens up the table designer view. Assign the primary key for this table (ensure that this primary key is nonclustered by unchecking the **Clustered** checkbox in the **Primary Key** settings).

    :::image type="content" source="media/create-memory-optimized-tables-in-azure-data-studio/table-designer-create-memory-optimized-table-non-clustered-primary-key.png" alt-text="Screenshot of Table Designer showing how to create a memory-optimized table with nonclustered primary key." lightbox="media/create-memory-optimized-tables-in-azure-data-studio/table-designer-create-memory-optimized-table-non-clustered-primary-key.png":::

1. In the Table Properties pane, select the **Memory-Optimized** checkbox. This enables the durability dropdown, where you can choose whether you want only the Schema or both the schema and data stored in memory. Choosing "Schema" only saves the schema of your database to memory. As you can see below, the script is updated to reflect the changes.

    :::image type="content" source="media/create-memory-optimized-tables-in-azure-data-studio/table-designer-memory-optimized-schema-only.png" alt-text="Screenshot of Table Designer showing Memory-Optimized Table with Schema only configuration." lightbox="media/create-memory-optimized-tables-in-azure-data-studio/table-designer-memory-optimized-schema-only.png":::

    Choosing **Schema** saves only the schema to memory. Choosing **Schema and Data** saves the schema and data to memory. Notice the change in the script.

> [!NOTE]
> The table designer also supports hash indexes and column store indexes, which can be configured while creating the memory-optimized table.

## Next step

> [!div class="nextstepaction"]
> [Download Azure Data Studio](./download-azure-data-studio.md)
