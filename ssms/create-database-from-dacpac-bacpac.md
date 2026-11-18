---
title: Create a Database from a DACPAC or BACPAC in SQL Server Management Studio
description: Create a database and apply a DACPAC or BACPAC with the preview command in SQL Server Management Studio (SSMS).
author: mahyon
ms.author: mahyon
ms.reviewer: mahyon
ms.date: 11/05/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---

# Create a database from a DACPAC or BACPAC in SQL Server Management Studio

Use **Create database from bacpac/dacpac** to create an empty database with the **New Database** dialog, then apply a `.dacpac` or `.bacpac` file with the Apply wizard.

> [!NOTE]
> The **Create database from bacpac/dacpac** command is in preview.

## Prerequisites

- [SQL Server Management Studio (SSMS)](install/install.md).
- A connection to SQL Server or Azure SQL Managed Instance.
- Permissions to create a database and apply the package. See [Create a database](/sql/relational-databases/databases/create-a-database#permissions) and the [Apply wizard prerequisites](apply-dacpac-bacpac.md#prerequisites).
- A local `.dacpac` or `.bacpac` file.

This command uses the existing **New Database** dialog. It isn't available for Azure SQL Database. To apply a package to an existing Azure SQL Database, use [Apply a DACPAC or BACPAC to an existing database](apply-dacpac-bacpac.md).

## Create the database

1. In **Object Explorer**, right-click the **Databases** folder and select **Create database from bacpac/dacpac (Preview)**.

   :::image type="content" source="media/database-devops/databases-context-menu.png" alt-text="Screenshot of the Databases context menu showing Create database from bacpac/dacpac in preview.":::

1. In the **New Database** dialog, enter the **Database name**. Configure the owner, database files, options, and filegroups as needed.

   > [!IMPORTANT]
   > Select the same collation as defined in the bacpac/dacpac file.

   :::image type="content" source="media/database-devops/create-db-new-database.png" alt-text="Screenshot of the New Database dialog showing the database name, owner, and database files.":::

1. Select **OK** to create the database. When creation succeeds, the Apply wizard opens with the new database selected as the target.

## Apply the package

In the Apply wizard, select **Bacpac** or **Dacpac**, and enter the local file path or select **Browse**.

:::image type="content" source="media/database-devops/create-db-apply-wizard.png" alt-text="Screenshot of the Apply wizard with the newly created database as the target and Bacpac selected.":::

The remaining steps are the same as [Apply a DACPAC or BACPAC to an existing database](apply-dacpac-bacpac.md#select-the-source-file).

> [!NOTE]
> Database creation and package application are separate operations. If you cancel the Apply wizard or the package application fails, the created database remains.

## Related content

- [Apply a DACPAC or BACPAC to an existing database](apply-dacpac-bacpac.md)
- [Create a DACPAC or BACPAC file](create-dacpac-bacpac.md)
- [Data-tier applications (DAC) overview](/sql/tools/sql-database-projects/concepts/data-tier-applications/overview)
- [Deploy a data-tier application](/sql/tools/sql-database-projects/concepts/data-tier-applications/deploy-data-tier-application)
- [Import a BACPAC file to create a new database](/sql/tools/sql-database-projects/concepts/data-tier-applications/import-bacpac-file-create-new-database)
