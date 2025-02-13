---
title: "Options (SQL Server Object Explorer - Scripting)"
description: Description of options within the SQL Server Object Explorer - Scripting window.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 09/15/2025
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "VS.ToolsOptionsPages.ObjectExplorerScripting"
  - "VS.ToolsOptionsPages.Sql_Server_Object_Explorer.ObjectExplorerScripting"
---
# Options (SQL Server Object Explorer - Scripting)

[!INCLUDE [SQL Server Azure SQL Database Azure SQL Managed Instance Synapse Analytics PDW Fabric SE Fabric DW Fabric SQL DB](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw-fabricse-fabricdw-fabricsqldb.md)]

Use this page to set scripting options that apply to the following commands on object context menus in **Object Explorer**:

- **Edit** commands for user tables and views.

- **Script \<object\> as** commands for user-created objects.

- **Modify** command for user-created objects.

- This page also sets the scripting option defaults for the **Generate SQL Server Script Wizard**.

## Remarks

The **Edit** and **Modify** commands might produce results that are different from the **Script \<object\> as** command for the same option setting. The **Edit** and **Modify** commands are designed to modify objects in the current database during a Query Editor session. The **Script \<object\> as** command is designed to generate a script so that it can be used later to create objects.

## Options

Specify scripting options by selecting from the available settings in the list to the right of each option.

> [!NOTE]  
> The default settings listed only apply to the **Script entire database and all database objects** option and might vary when using the **Select specific database objects** option.

### General scripting options

#### Delimit individual statements

Separates individual [!INCLUDE [tsql](../includes/tsql-md.md)] statements by using a batch separator. To change the default batch separator for **Query Editor**, select **Tools**/**Options**/**Query Execution**/**SQL Server**/**General**/**Batch separator**. Default is False. For more information, see [GO](/sql/t-sql/language-elements/sql-server-utilities-statements-go).

#### Include descriptive headers

Adds descriptive comments to the script by separating the script into sections for each object. Default is True. For more information, see [Slash Star (Block Comment)](/sql/t-sql/language-elements/slash-star-comment-transact-sql).

#### Include enabling vardecimal compression

Includes the vardecimal storage options. Default is False. For more information, see [sp_db_vardecimal_storage_format](/sql/relational-databases/system-stored-procedures/sp-db-vardecimal-storage-format-transact-sql).

#### Script change tracking

Includes change tracking information in the script.

#### Script full-text catalogs

Includes a script for full-text catalogs. Default is False. For more information, see [CREATE FULLTEXT CATALOG](/sql/t-sql/statements/create-fulltext-catalog-transact-sql).

#### Script `USE` \<database\>

Adds the `USE DATABASE` statement to the script to create database objects in the context of the current **Object Explorer** database. When the script is expected for use in a different database, select False to omit. Default is True. For more information, see [USE](/sql/t-sql/language-elements/use-transact-sql).

### Object scripting options

#### Check for object existence

Check that an object with the given name exists before dropping or altering or that an object with the given name doesn't exist before creating. For more information, see [IF...ELSE](/sql/t-sql/language-elements/if-else-transact-sql) and [EXISTS](/sql/t-sql/language-elements/exists-transact-sql).

#### Generate script for dependent objects

Generates a script for other objects that are required when the script for the selected object is executed. Default is False.

#### Schema qualify object names

Qualifies object names with the object schema. Default is False. For more information, see [Create a database schema](/sql/relational-databases/security/authentication-access/create-a-database-schema).

#### Script data compression options

Includes data compression options in the script. Default is False.

#### Script extended properties

Includes extended properties in the script if the object has extended properties. Default is False. For more information, see [sp_addextendedproperty](/sql/relational-databases/system-stored-procedures/sp-addextendedproperty-transact-sql).

#### Script owner

Includes the owner in the generated script. Default is False.

#### Script permissions

Includes permissions on database objects in the script. Default is True. For more information, see [Permissions (Database Engine)](/sql/relational-databases/security/permissions-database-engine).

### Table/View options

The following options apply only to scripts for tables or views.

#### Convert user-defined data types to base types

Converts user-defined data types to the base types from which they were created. Use True when the source database user-defined data types don't exist in the database where the script is run. Use False to keep the user-defined data types. Default is False. For more information, see [CREATE TYPE](/sql/t-sql/statements/create-type-transact-sql).

#### Generate `SET` ANSI PADDING commands

Adds the `SET ANSI_PADDING` statement before and after each `CREATE TABLE` statement. Default is True. For more information, see [SET ANSI_PADDING](/sql/t-sql/statements/set-ansi-padding-transact-sql).

#### Include collation

Includes collation in column definition. Default is True. For more information, see [Collation and Unicode support](/sql/relational-databases/collations/collation-and-unicode-support).

#### Include `IDENTITY` property

Includes definitions for `IDENTITY` seed and `IDENTITY` increment. Default is True. For more information, see [CREATE TABLE (Transact-SQL) IDENTITY (Property)](/sql/t-sql/statements/create-table-transact-sql-identity-property).

#### Schema qualify foreign key references

Adds the schema name to table references for FOREIGN `KEY` constraints. Default is True.

#### Script bound defaults and rules

Includes the `sp_bindefault` and `sp_bindrule` binding stored procedure calls. Default is True. For more information, see [sp_bindefault](/sql/relational-databases/system-stored-procedures/sp-bindefault-transact-sql) and [sp_bindrule](/sql/relational-databases/system-stored-procedures/sp-bindrule-transact-sql).

#### Script `CHECK` constraints

Adds [Unique constraints and check constraints](/sql/relational-databases/tables/unique-constraints-and-check-constraints) to the script. Default is True.

#### Script defaults

Includes column default values in the script. Default is False. For more information, see [CREATE DEFAULT](/sql/t-sql/statements/create-default-transact-sql).

#### Script file groups

Specifies the filegroup in the `ON` clause for table definitions. Default is False. For more information, see [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql).

#### Script foreign keys

Includes [Primary and foreign key constraints](/sql/relational-databases/tables/primary-and-foreign-key-constraints) in the script. Default is False.

#### Script full-text indexes

Includes full-text indexes in the script. Default is False. For more information, see [CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql).

#### Script indexes

Includes clustered, nonclustered, and XML indexes in the script. Default is True. For more information, see [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql).

#### Script partition schemes

Includes table partitioning schemes in the script. Default is False. For more information, see [CREATE PARTITION SCHEME](/sql/t-sql/statements/create-partition-scheme-transact-sql).

#### Script primary keys

Includes [Primary and foreign key constraints](/sql/relational-databases/tables/primary-and-foreign-key-constraints) in the script. Default is True.

#### Script statistics

Includes user-defined statistics in the script. Default is False. For more information, see [CREATE STATISTICS](/sql/t-sql/statements/create-statistics-transact-sql).

#### Script triggers

Include triggers in the script. Default is False. For more information, see [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql).

#### Script unique keys

Includes [Unique constraints and check constraints](/sql/relational-databases/tables/unique-constraints-and-check-constraints) in the script. Default is False.

#### Script view columns

Declares view columns in view headers. Default is False. For more information, see [CREATE VIEW](/sql/t-sql/statements/create-view-transact-sql).

#### Include DRI system names

Includes system generated constraint names to enforce declarative referential integrity (DRI). Default is False. For more information, see [REFERENTIAL_CONSTRAINTS](/sql/relational-databases/system-information-schema-views/referential-constraints-transact-sql).

### Version options

#### Match script settings to source

If enabled the target version, engine edition and engine type of the scripts generated are set to the values of the server the object being scripted. This configuration disables (and ignores) the other version options.

#### Script for database engine edition

Scripts generated are targeted for the specified [Engine Edition](/dotnet/api/microsoft.sqlserver.management.smo.edition).

#### Script for database engine type

Scripts generated are targeted for the specified [Database Engine Type](/previous-versions/sql/sql-server-2014/ee642509(v=sql.120)).

#### Script for server version

Scripts generated are targeted for the specified version of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)]. Features that are new in [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] can't be scripted for earlier versions. Some scripts created for [!INCLUDE [ssnoversion](../includes/ssnoversion-md.md)] can't be executed on servers that are running on an earlier version of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)], or on a database that has an earlier [database compatibility level setting](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).

## Related content

- [Generate scripts (SQL Server Management Studio)](../scripting/generate-scripts-sql-server-management-studio.md)
