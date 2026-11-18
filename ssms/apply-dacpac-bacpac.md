---
title: Apply a DACPAC or BACPAC to an Existing Database in SQL Server Management Studio
description: Deploy a DACPAC to an existing database or import a BACPAC into an empty database with the preview wizard in SQL Server Management Studio (SSMS).
author: mahyon
ms.author: mahyon
ms.reviewer: mahyon
ms.date: 11/05/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---

# Apply a DACPAC or BACPAC to an existing database in SQL Server Management Studio

Use the **Apply bacpac/dacpac** wizard to deploy schema changes from a `.dacpac` file or import schema and data from a `.bacpac` file.

> [!NOTE]
> The **Apply bacpac/dacpac** wizard is in preview.

- **DACPAC**: Deploy schema changes to an existing database, whether empty or populated. The deployment calculates schema differences and applies changes according to the selected publish options.
- **BACPAC**: Import schema and data into an existing, empty database. If the database contains user objects, BACPAC import is unavailable.

For more information about the package formats, see [Data-tier applications (DAC) overview](/sql/tools/sql-database-projects/concepts/data-tier-applications/overview).

## Prerequisites

- [SQL Server Management Studio (SSMS)](install/install.md).
- A target database on SQL Server, Azure SQL Database, or Azure SQL Managed Instance.
- A local `.dacpac` or `.bacpac` file.
- Permissions to deploy schema changes or import the package into the target database. See [SqlPackage publish](/sql/tools/sqlpackage/sqlpackage-publish) and [SqlPackage import](/sql/tools/sqlpackage/sqlpackage-import).
- For a BACPAC, a target database with no user-defined objects.

To create a target database first, see [Create a database from a DACPAC or BACPAC](create-database-from-dacpac-bacpac.md).

## Launch the wizard

In **Object Explorer**, right-click the target database and select **Tasks** > **Apply bacpac/dacpac (Preview)**.

:::image type="content" source="media/database-devops/tasks-context-menu.png" alt-text="Screenshot of the database Tasks menu showing the preview Apply bacpac/dacpac command.":::

## Select the source file

On **Select Source**, confirm the **Target server** and **Database**.

Select **Bacpac** or **Dacpac**, and enter the local file path or select **Browse**. Select **Next**.

If the target database contains user objects, **Bacpac** is disabled. The wizard doesn't merge a BACPAC's data with existing tables or rows.

:::image type="content" source="media/database-devops/apply-select-source.png" alt-text="Screenshot of Select Source with Dacpac selected and Bacpac disabled because the target database contains user objects.":::

## Configure options

### DACPAC

For a DACPAC, the **Options** page displays **SQLCMD Variables** and **Publish Options**.

- Enter values for any SQLCMD variables defined in the package.
- Use the search box to find publish options, and select the options for the deployment.
- Review **Block on possible data loss** before proceeding. Disabling this option can allow changes that remove data.

Select **Next**.

:::image type="content" source="media/database-devops/apply-options-dacpac-sqlcmd.png" alt-text="Screenshot of DACPAC Options showing editable SQLCMD variable values and searchable Publish Options.":::

### BACPAC

For a BACPAC, the **Options** page displays **Command timeout**, **Long-running command timeout**, **Database lock timeout**, and **Import Options**.

Configure the timeout settings. Use the search box to find import options, and select the options for the import. Select **Next**.

:::image type="content" source="media/database-devops/apply-options-bacpac.png" alt-text="Screenshot of BACPAC Options showing command and database lock timeout settings and searchable Import Options.":::

## Review the plan

On **Review Plan**, review the planned operations and any warnings before applying the package.

### DACPAC deployment

For a DACPAC, schema changes can include creating, altering, or dropping objects. Back up the target database before applying changes that could remove data.

If the database already matches the DACPAC, the page reports that no changes are needed. Select **Refresh** to refresh the plan.

Select **Execute** to apply the package.

:::image type="content" source="media/database-devops/apply-review-plan.png" alt-text="Screenshot of Review Plan reporting that no changes are needed because the database matches the selected package.":::

### BACPAC import

For a BACPAC, **Review Plan** lists the tables and data sizes under **Table data to import**. The **Total data** value shows the total amount of data to import.

Select **Refresh** to refresh the plan. Select **Execute** to import the package.

:::image type="content" source="media/database-devops/apply-review-plan-bacpac.png" alt-text="Screenshot of the BACPAC import plan listing tables, data sizes, and total data to import.":::

## Review results

On **Progress**, check the status of each operation. Select **Save Logs** to save the operation output.

If an operation fails, review its error and the saved logs before retrying. After the operation completes, select **Close**.

:::image type="content" source="media/database-devops/apply-progress.png" alt-text="Screenshot of completed DACPAC deployment operations with Save Logs and Close buttons.":::

## Related content

- [Create a DACPAC or BACPAC file](create-dacpac-bacpac.md)
- [Create a database from a DACPAC or BACPAC](create-database-from-dacpac-bacpac.md)
- [Projects in SQL Server Management Studio](build-database-projects-by-using-sql-server-management-studio.md)
- [Schema Compare in SQL Server Management Studio](schema-compare.md)
- [SqlPackage publish](/sql/tools/sqlpackage/sqlpackage-publish)
- [Import a BACPAC file to create a new database](/sql/tools/sql-database-projects/concepts/data-tier-applications/import-bacpac-file-create-new-database)
