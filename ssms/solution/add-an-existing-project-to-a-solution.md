---
title: "Add an Existing Project to a Solution"
description: "Add an Existing Project to a Solution"
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: maghan
ms.date: 02/19/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
f1_keywords:
  - "vs.addexistingproject"
helpviewer_keywords:
  - "adding projects"
  - "solutions [SQL Server Management Studio], project additions"
  - "projects [SQL Server Management Studio], adding"
---

# Add an Existing Project to a Solution

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

You can add one or more projects to an existing solution. A project can be associated with more than one solution.

## To add an existing project to a solution

1. In Solution Explorer, select the solution.

1. On the **File** menu, point to **Add**, and select **Existing Project**.

1. In the **Add Existing Project** dialog box, locate the project you want to add, select the project file, and then select **Open**.

    The project is added to the selected solution.

> [!NOTE]  
> Before adding an existing project from shared directories in a multideveloper environment, you should attempt to ensure that your changes do not adversely affect or overwrite another developer's changes.

## Related content

- [Projects (SQL Server Management Studio)](projects-sql-server-management-studio.md)
- [Solutions (SQL Server Management Studio)](solutions-sql-server-management-studio.md)
