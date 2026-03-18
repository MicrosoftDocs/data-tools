---
title: Custom Instructions
titleSuffix: GitHub Copilot in SQL Server Management Studio
description: Learn how to use custom instructions with GitHub Copilot in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: erinstellato
ms.date: 03/18/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand how to use GitHub Copilot Completions in SQL Server Management Studio.
---

# Use custom instructions with GitHub Copilot in SQL Server Management Studio

Use the custom instructions feature to automatically add customized, contextual details to your prompts. Copilot Chat uses these instructions to tailor responses based on your personal preferences.

## Use the .github/copilot-instructions.md file

To use a `.github/copilot-instructions.md` file:

1. Create or add a custom instructions file named `.github/copilot-instructions.md` in the root of your repository.

1. To enable the feature, select **Enable custom instructions to be loaded from .github/copilot-instructions.md files and added to requests** in **Tools** > **Options** > **GitHub** > **Copilot** > **Copilot Chat**.

Custom instructions aren't visible in the Chat view or inline chat. However, when Copilot uses the `.github/copilot-instructions.md` file, it lists the file in the References list of a response.

## Enable user-level instructions

In addition to custom instructions for a repository, you can define user-level preferences that apply to all your Copilot sessions. User-level preferences are saved to `%USERPROFILE%/copilot-instructions.md`.

Use user-level preferences for personal coding standards, preferred patterns, or workflow conventions that you want Copilot to follow, even when you're not using a repository. Repository-level instructions in `.github/copilot-instructions.md` still apply alongside your user-level preferences, so Copilot respects any shared standards.

If the `copilot-instructions.md` file doesn't exist in your `%USERPROFILE%` folder, you can create it in that location.

## Custom instructions file format

Custom instruction files are markdown files (`.md` file extension) and contain a main heading and subheadings for each section you define.

### Example

```markdown
# Copilot Instructions

## Persona
- I am a veteran SQL Server data professional with 20+ years of experience.
- Use a helpful, collegial tone. Keep explanations brief, but provide enough context to understand the code.
- Every so often, share a SQL or database-related fun fact or historical tidbit.

## Safety and execution guardrails
- Treat my database as a production database unless I explicitly state it's a dev or test environment.
- For any query that could scan large tables, include a cautious version first (TOP, date filter, or indexed predicate), but offer to give me the full version if I want it

## Code style
- Use tabs instead of spaces for indentation
- Always schema-qualify object names (e.g., dbo.Customer)
- Place JOIN conditions on separate lines
- Include header comments with author, date, parameters, change history and description for all stored procedures and functions
- Always qualify column names with table aliases
- Use short, readable aliases based on table name

## Naming conventions:
- Tables: PascalCase singular (Customer, Order, Product)
- Primary keys: <TableName>ID (CustomerID)
- Foreign keys: <ReferencedTable>ID
- Stored procedures: usp_<Action><Entity>
- Views: v_<Description>
- Functions: fn_<Description>
```

## Related content

- [Use database instructions with GitHub Copilot in SQL Server Management Studio](database-instructions.md)
- [Adding repository customer instructions for GitHub Copilot](https://docs.github.com/enterprise-cloud@latest/copilot/how-tos/configure-custom-instructions/add-repository-instructions?tool=visualstudio)
