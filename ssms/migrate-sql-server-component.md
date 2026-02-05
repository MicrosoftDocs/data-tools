---
title: SQL Server Migration Component
description: Learn about the SQL Server migration component in SQL Server Management Studio (SSMS).
author: nilabjaball
ms.author: niball
ms.reviewer: randolphwest
ms.date: 11/26/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
  - sql-migration-content
f1_keywords:
  - "sql13.swb.migrationassistant.migration.f1"
  - "sql13.swb.migrationassistant.assessment.f1"
helpviewer_keywords:
  - "migrate [SQL Server], SQL Server Management Studio"
  - "migration [SQL Server Management Studio], extensions"
  - "migration [SQL Server Management Studio], components"
  - "migration extension [SQL Server], SQL Server Management Studio"
  - "migration component [SQL Server], SQL Server Management Studio"
  - "SQL Server Management Studio extensions"
  - "SQL Server Management Studio components"
  - "SQL Server Management Studio [SQL Server], extensions"
  - "SQL Server Management Studio [SQL Server], components"
  - "extensions [SQL Server], SQL Server Management Studio"
  - "components [SQL Server], SQL Server Management Studio"
keywords:
  - SQL Server
  - SSMS
  - SQL Server Management Studio
  - extensions
  - components
---

# Use the SQL Server migration component in SQL Server Management Studio

The migration component in SQL Server Management Studio (SSMS) checks upgrade and compatibility issues from lower versions of SQL Server to higher versions of SQL Server, running on-premises and on other virtual machine (VM) environments. The migration component finds compatibility issues related to breaking changes, behavior changes, deprecated features, and other information. The report also provides a feature parity check if you want to migrate from one cross-platform database to another. The upgrade adviser assessment report provides the effect of objects, the possible cause, and remediation steps.

You can also physically migrate your database using the migration component. It follows the backup-copy-restore technology to move data from the source to the target by providing a backup folder and, optionally, a copy folder. Along with the data, the migration wizard transfers logins to simplify side by side migration.

> [!NOTE]  
> Because migration requires network shares to access backup files, this component can't migrate databases to Azure SQL Managed Instance or Azure SQL Database.

## Prerequisites

- SQL Server Management Studio 21 and later versions.
- A SQL Server instance login with **sysadmin** permissions.

## Installation and configuration

1. Install the latest version of [SQL Server Management Studio](install/install.md) (SSMS). Once the installation is complete, select **Modify** > **Individual Components**.

1. Select the **Migration** component, choose **Install while downloading** from the dropdown list, and select **Modify** to complete the installation.

## Assess your environment

1. Connect to the SQL Server instance that needs to be assessed for upgrade from an earlier version of SQL Server to the later version.

1. Right-click on the source instance, and navigate to **Migrate SQL Server** > **New Assessment...**.

1. Select the assessment type using the following information:

   - **Name**: The unique assessment name

   - **Target Name**: The target version that you would like to upgrade

   - **Assessment Type**: One of the following options:

     - **Compatibility Type**: Identify breaking changes, behavior changes, and deprecated features

     - **Feature Parity**: Discover partially supported features that might require re-engineering

       > [!NOTE]  
       > This option is enabled for when target is SQL Server on Linux.

1. Select the databases you would like to assess. If you want to analyze ad hoc queries using Extended Event or Profiler trace files, you can provide the directory containing all the trace or Extended Event files.

1. Verify the selection and select **Finish**. The duration of the assessment rules depends on the number of databases and the complexity of their schemas. Once the assessment is completed, it automatically opens the report.

1. Review the assessment report. This report provides a list of issues under each category. Each issue displays an issue type, any affected objects, and recommendations to fix the issues.

You can change the compatibility to identify issue for a particular database compatibility level, as shown in the following screenshot.

:::image type="content" source="media/migrate-sql-server-component/assessment-report.png" alt-text="Screenshot of the SQL migration report, featuring a filter on the database compatibility level." lightbox="media/migrate-sql-server-component/assessment-report.png":::

If you already saved an assessment report, you can open the assessment by navigating to **View Assessment Report** > **Open Assessment**, and choosing the `assessment_<name>.json` file.

## Prepare for migration

- Make sure that the assessment report is reviewed and all issues are resolved.

- Validate that source databases are in a known good state before beginning migration. The databases are migrated as-is, with no change to the data or internal structures. We recommend using [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) to ensure logical and physical integrity of the source databases.

- If any of the databases are protected by [Transparent data encryption (TDE)](/sql/relational-databases/security/encryption/transparent-data-encryption), ensure the corresponding certificate or asymmetric key is transferred to the target SQL Server instance before initiating migration.

- There are two options for the shared folders used to back up databases from the source and restore them on the target:

  1. Use a single shared folder that both the source and target SQL Server instances have [permissions](/sql/t-sql/statements/backup-transact-sql#permissions) to perform backup and restore respectively.

  1. If you prefer separate shared folders, ensure that the Windows user performing the migration has permissions to copy the backup files from the source shared folder to the target shared folder.

## Migrate your database

1. Connect to the SQL Server that needs to be assessed for upgrade from lower version of SQL Server to higher version.

1. Right-click on the SQL Server instance, and navigate to **Migrate SQL Server** > **New Migration...**.

1. Provide the target server details:

   - **Migration Name**: A unique migration name
   - Target SQL Server instance name
   - **Authentication Type** – Windows authentication or SQL authentication
   - Provide the user credentials
   - Select other connection settings as per your environment

1. Databases:

   - Select the databases that you want to migrate
   - You can edit the target database name
   - Provide the backup folder path, which can be a local drive or file share path
   - If the target instance can't access the source file share, you can select a directory to copy the backup files

1. Backup details:

   If you want to edit the backup and copy path of a particular database, you can select the database name and change the backup and copy path. You can also edit the target data and log file path.

1. Logins:

   Choose logins that are eligible for migration.

1. Once you review selection, select **Finish**.

The migration wizard shows the migration of each database. Once complete, you can connect to the target SQL Server and verify that databases and logins are migrated successfully.

## Related content

- [Upgrade SQL Server to the latest version](/sql/sql-server/migrate/guides/sql-server-to-sql-server-upgrade-guide)
- [Migrate from SQL Server: Pre-migration](/data-migration/sql-server/pre-migration)
