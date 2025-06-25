---
title: "Use Code Assistance"
titleSuffix: Copilot in SQL Server Management Studio
description: Learn how to use code assistance for Copilot in SQL Server Management Studio.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 05/19/2025
ms.update-cycle: 180-days
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - ce-skilling-ai-copilot
# CustomerIntent: As a database administrator or database developer, I want to understand how to use code assistance in Copilot in SQL Server Management Studio.
---

# Code assistance for Copilot in SQL Server Management Studio

Copilot in SQL Server Management Studio (SSMS) offers code assistance which can accelerate productivity by helping you understand and fix queries faster. Highlight any query in the editor and right-click to view the available options.

## Document assistant

The Document assistant returns an updated script in the chat window with a short summary of what the query does. It also adds comments to individual lines of code as appropriate. Documenting T-SQL can help the next person who looks at your code understand what you did.

## Explain assistant

The Explain assistant provides in-depth details about each clause in the query (SELECT, FROM, etc.) in the chat window. The output appears in Markdown format for organization and easy review.

## Fix assistant

The Fix assistant addresses any errors in the script and returns a corrected version of the script in the chat for you to review. The response includes an explanation of the issue and what was changed.

## Refactor assistant

The Refactor assistant identifies anti-patterns in the query, and makes changes consistent with T-SQL best practices. The query is returned in the chat window with a description of improvements made in Markdown format.

## Related content

- [Use the chat window for Copilot in SQL Server Management Studio](copilot-in-ssms-chat.md)
- [Scenarios for Copilot in SQL Server Management Studio](copilot-in-ssms-scenarios.md)
