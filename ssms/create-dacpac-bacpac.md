---
title: Create a DACPAC or BACPAC File in SQL Server Management Studio
description: Create a DACPAC containing a database schema or a BACPAC containing schema and data with the preview wizard in SQL Server Management Studio (SSMS).
author: mahyon
ms.author: mahyon
ms.reviewer: mahyon
ms.date: 11/05/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---

# Create a DACPAC or BACPAC file in SQL Server Management Studio

Use the **Create bacpac/dacpac** wizard to save a database schema as a `.dacpac` file or save the schema with data as a `.bacpac` file. You can save the file to local disk or Azure Blob Storage.

> [!NOTE]
> The **Create bacpac/dacpac** wizard is in preview.

For more information about the package formats, see [Data-tier applications (DAC) overview](/sql/tools/sql-database-projects/concepts/data-tier-applications/overview).

## Prerequisites

- [SQL Server Management Studio (SSMS)](install/install.md).
- Access to a source database on SQL Server, Azure SQL Database, or Azure SQL Managed Instance.
- Permissions to extract the schema or export schema and data. See [Extract a DACPAC from a database](/sql/tools/sql-database-projects/concepts/data-tier-applications/extract-dacpac-from-database#permissions) and [Export a BACPAC file](/sql/tools/sql-database-projects/concepts/data-tier-applications/export-bacpac-file#permissions).
- Write access to the destination folder or, for Azure Blob Storage, access to the storage account and container.

## Launch the wizard

In **Object Explorer**, right-click the source database and select **Tasks** > **Create bacpac/dacpac (Preview)**.

:::image type="content" source="media/database-devops/tasks-context-menu.png" alt-text="Screenshot of the database Tasks menu showing the preview Create and Apply bacpac/dacpac commands.":::

## Select contents

On **Select Contents**, confirm the source server and database.

- Select **Include data** to create a `.bacpac` containing schema and data.
- Clear **Include data** to create a schema-only `.dacpac`.

The **File format** section shows the format that will be created. Select **Next**.

:::image type="content" source="media/database-devops/create-select-contents.png" alt-text="Screenshot of Select Contents with Include data selected to create a BACPAC file.":::

## Choose a destination

On **Destination**, choose where to save the file:

- **Local disk**: Enter a file path or select **Browse**. To replace a file at that path, select **Overwrite existing file**.
- **Azure Blob Storage**: Select **Connect** to connect to a storage account, select a **Container**, and enter a **File name**.

Select **Next**.

:::image type="content" source="media/database-devops/create-destination.png" alt-text="Screenshot of Destination showing local disk and Azure Blob Storage options.":::

> [!IMPORTANT]
> DACPAC and BACPAC files aren't encrypted. Store them in a location with appropriate access controls.

## Configure settings

On **Settings**, select **Exclude Azure SQL Database Incompatible Objects** if you want to exclude objects that aren't compatible with Azure SQL Database.

For a BACPAC, use **Select tables for data export** to choose which tables' data to include. Expand a schema to select individual tables, or use **Select All**. Table selection isn't shown for a schema-only DACPAC.

Select **Execute** to create the file.

:::image type="content" source="media/database-devops/create-settings.png" alt-text="Screenshot of Settings showing the compatibility option and tables selected for data export.":::

## Review results

On **Execute**, check the status of each operation. Select **Save Logs** to save the operation output, including any errors.

After the operation completes, select **Close** to finish. You can optionally apply the file to another database.

:::image type="content" source="media/database-devops/create-execute.png" alt-text="Screenshot of completed BACPAC export operations with Save Logs, Apply bacpac, and Close buttons.":::

## Apply the created file

Applying the created file is optional. To apply it after a successful operation, select **Apply bacpac** or **Apply dacpac**, depending on the file format.

On **Apply File**, select **Connect** to connect to the target server and database, and then select **Start**. The Apply wizard opens with the created file selected.

:::image type="content" source="media/database-devops/create-apply.png" alt-text="Screenshot of Apply File showing the created BACPAC path and a Connect button for the target server.":::

Continue with [Apply a DACPAC or BACPAC to an existing database](apply-dacpac-bacpac.md#select-the-source-file). A BACPAC requires an empty target database.

## Related content

- [Apply a DACPAC or BACPAC to an existing database](apply-dacpac-bacpac.md)
- [Create a database from a DACPAC or BACPAC](create-database-from-dacpac-bacpac.md)
- [Projects in SQL Server Management Studio](build-database-projects-by-using-sql-server-management-studio.md)
- [Extract a DACPAC from a database](/sql/tools/sql-database-projects/concepts/data-tier-applications/extract-dacpac-from-database)
- [Export a BACPAC file](/sql/tools/sql-database-projects/concepts/data-tier-applications/export-bacpac-file)
