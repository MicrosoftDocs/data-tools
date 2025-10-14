---
title: "Overview of the Query Hint Recommendation Tool (Preview)"
titleSuffix: SQL Server Management Studio
description: Query Hint Recommendation tool overview.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 10/07/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand how to use the Query Hint Recommendation Tool.
---

# Query Hint Recommendation tool (Preview)

Microsoft SQL Server and Azure SQL offer a suite of query hints that can guide the query optimizer to generate alternative query execution plans that provide better performance. [Query Store hints](/sql/relational-databases/performance/query-store-hints) provide a user-friendly way to influence the shape of query plans without changing the application code. While Query Store hints are convenient, identifying the optimal hint for a specific query can require a manual trial-and-error process, which can be time consuming for users.

The Query Hint Recommendation tool, a component for SQL Server Management Studio (SSMS), automates the identification of optimal query hints to enhance SQL query performance. This tool allows users to explore query hints for a given query while minimizing the need for manual trial and error.

## How it works

The tool takes a maximum tuning budget as input and makes the best use of the given time budget by skipping query hints that aren't expected to yield a better quality plan. The tool also computes the baseline performance without any hint and uses it to reject hints that yield a plan with performance worse than baseline or the best hint found so far.

In summary, the tool makes effective use of the tuning time budget to efficiently identify the optimal query hint.

## Related content

- [Install the Query Hint Recommendation tool (Preview)](hint-tool-install.md)
- [Use the Query Hint Recommendation tool (Preview)](hint-tool-use.md)
