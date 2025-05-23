---
title: "Overview"
titleSuffix: Copilot in SQL Server Management Studio
description: Learn about Copilot in SQL Server Management Studio.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 05/23/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - ce-skilling-ai-copilot
# CustomerIntent: As a database administrator or database developer, I want to understand how to use Copilot in SQL Server Management Studio.
---
# Copilot in SQL Server Management Studio (Preview)

Use Copilot in SQL Server Management Studio (SSMS) to ask questions about your database and environment, and get help writing Transact-SQL (T-SQL) with AI.

Copilot in SSMS doesn't retain any of your information (prompts, responses, system metadata, etc.) and doesn't use any of your data to train or retrain models.

Copilot in SSMS can answer questions for databases in SQL Server, Azure SQL Database, Azure SQL Managed Instance, and SQL Database in Fabric. Copilot executes queries based on the permissions for your login. For example, if you don't have permission to select from the table `Sales.Orders` and you ask Copilot to write and execute a select query such as `SELECT TOP 100 * FROM Sales.Orders`, the query execution can't occur.

Copilot in SSMS uses [Azure OpenAI resources](use-azure-openai-with-copilot-in-ssms.md), requiring an endpoint and deployment in your Azure subscription.

## Related tasks

- [Use Azure OpenAI with Copilot in SSMS](use-azure-openai-with-copilot-in-ssms.md)
- [Install Copilot in SQL Server Management Studio](copilot-in-ssms-install.md)
- [Scenarios for Copilot in SQL Server Management Studio](copilot-in-ssms-scenarios.md)
- [Use the chat window for Copilot in SQL Server Management Studio](copilot-in-ssms-chat.md)
- [Code assistance for Copilot in SQL Server Management Studio](copilot-in-ssms-code-assistance.md)
- [Troubleshooting issues with Copilot in SQL Server Management Studio](copilot-in-ssms-troubleshooting.md)

## Related content

- [What is SQL Server Management Studio (SSMS)?](../sql-server-management-studio-ssms.md)
- [Install Copilot in SQL Server Management Studio](copilot-in-ssms-install.md)
