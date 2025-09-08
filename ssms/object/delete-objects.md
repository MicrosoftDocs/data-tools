---
title: "Delete Objects"
description: Delete Objects is used to delete a database or database object.
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/07/2025
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.deleteobjects.f1"
helpviewer_keywords:
  - "Delete Objects dialog box"
---
# Delete objects

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

Use this dialog box to delete a database or database object.

## UI element list

#### Object to be deleted

Displays the names, types, owners, and status of the objects that are about to be deleted, and any messages about errors during execution.

Running **Delete** on a database is equivalent to issuing `DROP DATABASE` in [!INCLUDE [tsql](../includes/tsql-md.md)].

#### Show Dependencies

Select to display both the objects that are dependent on the currently selected object and objects that the current object is dependent on (upward and downward dependency). The information displayed in the **Show Dependencies** dialog box is read-only.

The **Show Dependencies** button doesn't appear for all types of database objects. To view dependencies when the **Show Dependencies** button isn't available, right-click the object in Object Explorer, and then select **View Dependencies**.

#### Delete backup and restore history information for databases

Only appears when a database is deleted, this check box causes the backup and restore history for the subject database to be deleted from the `msdb` database.

#### Close existing connections

Only appears when a database is deleted, this check box terminates connections to the subject database.
