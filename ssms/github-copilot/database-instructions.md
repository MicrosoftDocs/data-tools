---
title: Database Instructions
titleSuffix: GitHub Copilot in SQL Server Management Studio (Preview)
description: Learn how to use database instructions with GitHub Copilot in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: erinstellato
ms.date: 02/11/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand how to use database instructions with GitHub Copilot in SQL Server Management Studio.
---

# Use database instructions with GitHub Copilot in SQL Server Management Studio (Preview)

Database instructions provide GitHub Copilot in SQL Server Management Studio (SSMS) with database-specific context and guidance that lives directly in the database. Database owners and teams can use them to describe business rules, data conventions, and usage patterns. With database instructions, Copilot can generate more accurate, meaningful, and consistent responses when users ask questions or write queries. Database instructions act as living documentation that travels with the database and is automatically applied during Copilot interactions.

In this article, you learn how to use database instructions, which further empower users and Copilot to find the correct objects and information faster. This feature helps reduce the time spent providing database, business, and internal knowledge to Copilot.

For related information about GitHub Copilot Chat, see [Use the GitHub Copilot Chat experience in SQL Server Management Studio (Preview)](chat.md).

## How database instructions work

Database instructions are stored as metadata in the database, which allows Copilot to automatically discover and apply them at runtime. When a user interacts with GitHub Copilot for a database, such as asking a question in natural language or generating T-SQL, Copilot incorporates these instructions as extra context. This context ensures responses reflect business definitions, canonical tables, and domain-specific rules, rather than relying only on schema names or guesswork. Instructions persist across sessions and are available to any user who accesses the same database.

## Prerequisites

Database instructions for GitHub Copilot in SSMS rely on information in extended properties.

1. Install SSMS 22.3 or a later version with the [AI Assistance workload](installation-state.md#install-github-copilot-in-ssms-using-the-visual-studio-installer).

1. Sign in to your GitHub account with Copilot access.

[Use GitHub Copilot for free](free-plan.md). Sign up and use AI to code faster and more efficiently.

## Use GitHub Copilot to add or view database instructions

These steps show how to create and use database instructions using GitHub Copilot.

### Ask Copilot a question to reveal missing context

Start by asking Copilot a question about your data in natural language. For example, `What was revenue for the last quarter of the year?` If the business has different start dates for fiscal year and calendar year, or if revenue requires a calculation that involves multiple tables, the relevant tables or columns are good candidates for a database instruction.

### Define the business rule as a database instruction

In Copilot chat, describe the rule or clarification you want Copilot to remember. For example, `Add an instruction for the Finance.CompanyRevenue table to state that revenue is defined as SUM(NetAmount) excluding refunds recorded in Finance.Refunds.`

### Save the instruction to the database

Once Copilot generates the T-SQL syntax to add the instruction as an extended property, you must persist this information as a database instruction. In Ask mode, GitHub Copilot can't run modification queries against the database.

```sql
-- Created by GitHub Copilot in SSMS - review carefully before executing
EXECUTE sp_addextendedproperty
    @name = N'AGENTS.md',
    @value = N'Revenue is defined as SUM(NetAmount) excluding refunds recorded in Finance.Refunds. When calculating actual revenue, refunds must be subtracted from the Revenue column values.',
    @level0type = N'SCHEMA',
    @level0name = N'Finance',
    @level1type = N'TABLE',
    @level1name = N'CompanyRevenue';
```

After you add the instruction to the database, Copilot automatically applies the information to future interactions.

### Use Copilot with the instruction applied

Ask Copilot the same or a related question again, `What was revenue for the last quarter of the year?` Copilot now uses the saved instruction to generate results that align with your business definition of revenue, without requiring you to restate the rule. You can also ask Copilot `Show me the query used to get this information.` to confirm Copilot's understanding of the instruction.

### More examples

There are infinite scenarios where business rules need to be applied for a database object including tables, columns, and stored procedures.

- `The dbo.Apts table stores information about patient appointments`
- `The Status column in dbo.Apts encodes status as: 1 = Scheduled, 2 = Completed, 5 = Confirmed, 99 = Cancelled`
- `The DtCrtd column in dbo.Apts lists the date and time the appointment was created`

When using database instructions with Copilot, you can also ask about instructions that currently exist.

- `Show me the database instructions for this database`
- `Does this database have a constitution set?`

## Use GitHub Copilot to create a database constitution

GitHub Copilot in SSMS also supports a singular constitution for your database, which sets the highest precedence instruction for the database. The constitution can include recommendations, coding guidelines, retention policies, and more.

> [!NOTE]  
> Implementing a database constitution applies to GitHub Copilot conversations for every user that uses GitHub Copilot in SSMS. The recommendations and guidelines apply only to GitHub Copilot conversations.

```sql
EXECUTE sp_addextendedproperty
    @name = N'CONSTITUTION.md',
    @value = N'Any T-SQL in this database must comply with the organizational standards and guidelines outlined in this constitution document.
 Queries that use SELECT * should not be used.';
```

## Requirements

Database instructions are currently only supported as extended properties. They follow the [AGENTS.md](https://agents.md/) format to provide the context used by GitHub Copilot. The name of the object's extended property must be `AGENTS.md`. Only one property named `AGENTS.md` can exist for an object. If an instruction is incorrect, you can update it using `sp_updateextendedproperty`, or delete it using `sp_dropextendedproperty`. There's no other configuration required for database instructions to work.

## Related content

- [Get started with GitHub Copilot in SQL Server Management Studio (Preview)](get-started.md)
- [Troubleshoot GitHub Copilot in SQL Server Management Studio (Preview)](troubleshoot.md)
