---
title: "Object Dependencies"
description: "Object Dependencies"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/15/2025
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.common.objectdependencies.f1"
---
# Object Dependencies

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

Some database objects have dependencies upon other database objects. For example, views and stored procedures depend upon the existence of tables that contain the data returned by the view or procedure. The **Object Dependencies (General page)** for the current object lists both the database objects that must be present for the object to function properly and the objects that depend upon the selected object. An object that references another object in its definition, and that definition is stored in the system catalog, is known as a *referencing entity*. An object that is referred to by another object is known as a *referenced entity*.

The **Object Dependencies (Advanced page)** for the current object lists the [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] database objects and [!INCLUDE [ssISnoversion](../includes/ssisnoversion-md.md)] objects that depend on the object. The objects might be stored on different servers.

Use this dialog box to understand the dependencies before changing or deleting the selected object.

## UI element list

#### Objects that depend on *\<selected object>*

Selecting this button displays a list of those objects that are dependency-tracked and that depend on the selected object.

#### Objects on which *\<selected object>* depends

Selecting this button displays a list of those objects that are dependency-tracked, on which the selected object depends.

#### Dependencies

If **Objects that depend on** *\<selected object\>* is selected, this displays a hierarchical view of objects that depend on the selected object. If **Objects on which** *\<selected object\>* **depends** is selected, this displays a hierarchical view of objects on which the selected object depends.

#### Name

Displays the name of the object selected in the previous **Dependencies** tree view.

#### Type

Displays the type of the object selected in the previous **Dependencies** tree view.

#### Last Sync Time

Specifies the time and date when the dependency information was last updated.

This option is available only on the **Advanced** page.

#### Dependency type

Displays the type of dependency between two objects. Can be one:

This option is available only on the **General** page.

- Schema-bound dependency

  A relationship between two objects that prevents the referenced object from being dropped or modified as long as the referencing object exists. A schema-bound dependency is created when a view or user-defined function is created by using the `WITH SCHEMABINDING` clause, or when a table references another object through a `CHECK` or `DEFAULT` constraint or in the definition of a computed column.

- Non-schema-bound dependency

  A relationship between two objects that doesn't prevent the referenced object from being dropped or modified.

- Not available or Unresolved Entity

  Indicates the dependency type can't be determined. This occurs only when the selected object is on an instance of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] that is earlier than [!INCLUDE [sql2008-md](../includes/sql2008-md.md)].
