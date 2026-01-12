---
title: Verify Queries
description: "Verify queries (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
f1_keywords:
  - "100644"
helpviewer_keywords:
  - "verifying queries"
  - "queries [SQL Server], verifying"
  - "checking queries"
---
# Verify queries (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

To avoid problems, you can check the query you have built to ensure its syntax is correct. This option is especially useful when you enter statements in the [SQL Pane (Visual Database Tools)](sql-pane-visual-database-tools.md).

When you verify queries, keep in mind:

- A statement can be valid, and therefore be verified successfully, even if it can't be represented in the **Diagram Pane** and **Criteria Pane**.

- SQL Verification can detect some, but not all SQL errors. If a query contains an error not detected during SQL verification, the database detects the error when you run the query.

- Queries that contain parameters can't be verified.

## Verify a SQL statement

Right-click in the **SQL Pane**, and select **Verify SQL Syntax** from the shortcut menu.

## Related content

- [Run queries (Visual Database Tools)](run-queries-visual-database-tools.md)
- [Perform Basic Operations with Queries (Visual Database Tools)](perform-basic-operations-with-queries-visual-database-tools.md)
