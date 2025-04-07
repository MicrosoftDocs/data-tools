---
title: Table Properties
description: "Table Properties (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 01/19/2017
ms.service: sql-server-management-studio
ms.topic: conceptual
ms.collection:
  - data-tools
f1_keywords:
  - "vdt.tabledesigner"
  - "vdt.designers.properties.Table"
---
# Table Properties (Visual Database Tools)
[!INCLUDE[SQL Server](../includes/applies-to-version/sqlserver.md)]
These properties appear in the Properties window when you right-click in Table Designer and select Properties. Unless otherwise noted, you can edit these properties in the Properties window when the table is selected.  
  
> [!NOTE]  
> If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO). When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table. You cannot drop published objects, therefore the schema change will fail.  
  
## Show Table Properties in Table Designer  
  
> [!NOTE]  
> The properties in this topic are ordered by category rather than alphabet.  
  
**Identity Category**  
Expands to show properties for **Name**, **Description**, and **Schema**.  
  
**Name**  
Displays the name of the table. To edit the name, type in the text box.  
  
> [!CAUTION]  
> If existing queries, views, user-defined functions, stored procedures, or programs refer to the table, the name modification will make these objects invalid.  
  
**Database Name**  
Shows the name of the data source of the selected table.  
  
**Description**  
Shows a description of the selected table. To see the entire description, or to edit it, click the description and then click the ellipses **(...)** to the right of the property.  
  
**Schema**  
Shows the name of the schema to which this table belongs. (Applies only to Microsoft SQL Server.)  
  
**Server Name**  
Shows the name of the server for the data source.  
  
**Table Designer Category**  
Expands to show properties for **Identity Column**, **Is Indexable**, and **Is Replicated**.  
  
**Identity Column**  
Shows the column used as the table's identity column. To change the identity column, choose from the drop-down list. Only columns of a numeric data type will show in the list.  
  
**Is Indexable**  
Shows whether the table can be indexed. If the table is not indexable it may be because you are not the table owner or because the table contains columns with data types of text, ntext, or image.  
  
**Is Replicated**  
Shows whether the table is replicated in another location.  
  
**Regular Data Space Specification Category**  
Expands to show properties for **(Data Space Type)**, **Filegroup or Partition Scheme Name**, and **Partition Column List**.  
  
**(Data Space Type)**  
Shows whether this table is stored using a filegroup or partition scheme.  
  
**Filegroup or Partition Scheme Name**  
Shows the name of the filegroup or partition scheme.  
  
**Partition Column List**  
Provides access to the **Partition Column List** dialog box.  
  
**Row GUID Column**  
Shows the column used by Microsoft SQL Server as the table's ROWGUID column. To change the ROWGUID column, choose from the drop-down list. (Applies only to SQL Server 7.0 or higher.)  
  
**Text/Image Filegroup**  
Provides a drop-down list from which you can choose the filegroup for columns that have text or image data types. If the table is stored using a partition scheme, leave this field blank.  
  
## See Also  
[Design Tables](design-tables-visual-database-tools.md)  
  
