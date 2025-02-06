---
title: Creating System-Versioned Tables in Azure Data Studio
description: How to use the Table Designer to create a system-versioned table
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest, maghan
ms.date: 02/06/2025
ms.service: azure-data-studio
ms.topic: tutorial
# CustomerIntent: As a <type of user>, I want <what?> so that <why?>.
---

# Create system-versioned tables in Azure Data Studio

[!INCLUDE [azure-data-studio-deprecation](includes/azure-data-studio-deprecation.md)]

[!INCLUDE [sql-asdb-asmi](includes/applies-to-version/sql-asdb-asmi.md)]

System-versioned tables, also known as temporal tables, can also be configured directly on Azure Data Studio. If you're new to system versioning, check out the [temporal tables on SQL Server documentation.](/sql/relational-databases/tables/creating-a-system-versioned-temporal-table) System-versioning tables must have the period columns defined.

## Create a system-versioned table

1. Create a table called "Department" with the column properties as seen below. To do this, right-click on the Tables folder in the Connections pane and select "New Table." Next, in the Table Properties pane, select the "System Versioning Enabled" check box. You can decide to rename this history table or leave the default name as is.

    :::image type="content" source="media/create-temporal-tables-in-azure-data-studio/table-designer-create-a-system-versioned-table-column-properties.png" alt-text="Screenshot of Table Designer showing how to create a system-versioned-table." lightbox="media/create-temporal-tables-in-azure-data-studio/table-designer-create-a-system-versioned-table-column-properties.png":::

1. The period columns, ***ValidFrom***, and ***ValidTo*** are enabled by default on system-versioned tables. The script pane will now be updated to show the T-SQL version of this system-versioned table.

    :::image type="content" source="media/create-temporal-tables-in-azure-data-studio/table-designer-system-versioning-row-start.png" alt-text="Screenshot of Table Designer showing how to define period columns." lightbox="media/create-temporal-tables-in-azure-data-studio/table-designer-system-versioning-row-start.png":::

> [!NOTE]
> System-versioned tables require a primary key.

## Next step

> [!div class="nextstepaction"]
> [Download Azure Data Studio](./download-azure-data-studio.md)
