---
title: Understand Database Diagram Ownership
description: "Understand database diagram ownership (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
f1_keywords:
  - "vdt.diagnostic.CannotOpenWithInvalidOwner"
helpviewer_keywords:
  - "diagrams [SQL Server], ownership"
  - "database diagrams [SQL Server], ownership"
  - "owners [SQL Server], database diagrams"
---

# Understand database diagram ownership (Visual Database Tools)

[!INCLUDE [SQL Server Azure SQL Database PDW](../includes/applies-to-version/sql-asdb-asdbmi-pdw.md)]

To use Database Diagram Designer it must first be set up by a member of the [db_owner](/sql/relational-databases/security/authentication-access/database-level-roles#fixed-database-roles) role (a role of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] databases) to control access to diagrams. Each diagram has one and only one owner, the user who created it. For more information on setting up diagramming see [Set up Database Diagram Designer (Visual Database Tools)](set-up-database-diagram-designer-visual-database-tools.md).

## Diagram ownership considerations

Some points to keep in mind about diagram ownership:

- Although any user with access to a database can create a diagram, once the diagram has been created, the only users who can see it are the diagram creator and any member of the **db_owner** role. If the diagram creator is part of a user group and not a member of the **db_owner** role then they require their own login to view the diagram.

- Ownership of diagrams can only be transferred to members of the **db_owner** role. This is only possible if the previous owner of the diagram has been removed from the database.

- If the owner of a diagram has been removed from the database, the diagram remains in the database until a member of the **db_owner** role attempts to open it. At that point the **db_owner** member can choose to take over ownership of the diagram.

## Related content

- [Work with database diagrams (Visual Database Tools)](work-with-database-diagrams-visual-database-tools.md)
- [Set up Database Diagram Designer (Visual Database Tools)](set-up-database-diagram-designer-visual-database-tools.md)
