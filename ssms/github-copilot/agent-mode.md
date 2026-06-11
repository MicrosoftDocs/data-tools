---
title: GitHub Copilot Agent Mode (Preview)
titleSuffix: GitHub Copilot in SQL Server Management Studio
description: Learn how to use GitHub Copilot Agent mode in SQL Server Management Studio (SSMS) to autonomously complete complex, multi-step database tasks.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: erinstellato
ms.date: 06/09/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand how to use GitHub Copilot Agent mode in SQL Server Management Studio to complete complex, multi-step database tasks.
---

# Use GitHub Copilot Agent mode (preview) in SQL Server Management Studio

GitHub Copilot Agent mode (preview) in SQL Server Management Studio (SSMS) lets you specify a high-level goal in natural language and have Copilot work through it by executing queries, reading files, and iterating on its own outputs until the task is complete or your input is needed.

> [!NOTE]  
> GitHub Copilot Agent mode in SQL Server Management Studio (SSMS) is currently in preview.

Unlike Ask mode, which stops after a single response, Agent mode continues running steps, invoking tools, and refining its approach until it reaches your goal. All queries and commands are executed under the context of the user's login and permissions, unless a custom database user or SQL login is specified in the front matter of the database's `CONSTITUTION.md`. For more information, see [Execution context for GitHub Copilot in SQL Server Management Studio](execution-context.md).

> [!IMPORTANT]  
> Agent mode can execute queries and make database changes on your behalf. Copilot requests your approval before running each query or command. Review proposed actions carefully before approving them. Enforce access control using SQL Server's least-privilege permissions. The security boundary is SQL Server's permission enforcement, not Copilot's approval system.

## Ask mode versus Agent mode

Use the following table to decide which mode fits your task:

| | Ask mode | Agent mode |
| --- | --- | --- |
| **How it works** | Single response per prompt; you apply code manually | Multi-step execution; iterates until goal is reached |
| **Execution** | Read-only queries only | Queries and commands execute with your approval |
| **Schema changes** | Generates T-SQL for you to run | Can execute schema changes if you approve them and your login has permission |
| **Best for** | Exploring ideas, reviewing generated code before applying | Complex multi-step tasks, investigation, analysis, and iterative development |
| **Interruption** | Single response, you can cancel at any time | You can cancel at any time |

## Prerequisites

- SSMS 22.7 or a later version with the [AI Assistance workload](installation-state.md#install-github-copilot-in-ssms-using-the-visual-studio-installer).
- A GitHub account with [Copilot access](https://docs.github.com/copilot/get-started/what-is-github-copilot#getting-access-to-copilot). Alternatively, [use GitHub Copilot for free in SQL Server Management Studio](free-plan.md).

## Use Agent mode

In Agent mode, Copilot operates autonomously and determines the relevant context for your prompt. Agent mode for GitHub Copilot in SSMS uses a local MCP server, `sql-tools` for its integration, and ships with a predefined set of tools.

1. In SSMS, select **View** > **GitHub Copilot Chat** to open the chat window.
1. At the bottom of the chat window, expand the mode dropdown list and select **Agent**.
1. In the bottom right of the chat window, select the Tools icon to see available tools.
1. Expand `sql-tools` to see the predefined tools. Hover over the tool name to learn more about what it does. If you deselect all tools, Agent mode doesn't function as expected.
1. You can't disable the `SSMS` list of tools.
1. Enter your prompt describing the high-level goal, and include the name of the database or server you're working against. Agent mode doesn't inherit context from the active query editor.

> [!IMPORTANT]  
> For best results, include the database or server in your prompt. This inclusion reduces ambiguity and the number of tool calls. If you don't include connection information, Copilot reads your connection list to identify a connection to use or asks for clarification on which database or server to use.

1. To submit your prompt, select **Send** or press <kbd>Enter</kbd>.

   Example prompts to get started:

   ```copilot-prompt
   - In the WideWorldImporters database on the SalesPRD server, analyze the `Sales.usp_QuarterlySalesSummary` stored procedure and its execution plan and tell me how to improve it
   - The AdventureWorks database on the SalesPRD server had high CPU between 1PM and 2PM today, investigate what caused it
   - Find the SQL Agent jobs on the SalesPRD server that failed in the last 24 hours, analyze the history and explain what happened and how to fix the jobs
   ```

1. Agent mode might invoke multiple tools to complete your request. For example, when reading schema information, generating Transact-SQL, and analyzing results. The active tool appears in the chat as each step runs.
1. When Copilot is ready to execute a query or command, it pauses and asks for your approval. Review the proposed action, and then select **Allow** to proceed, or **Dismiss** to skip that step.

   You can configure the scope of approval by using the **Allow** dropdown list:

   | Option | Effect |
   | --- | --- |
   | **Allow once** | Approves this single invocation |
   | **Allow for this session** | Approves this tool for the rest of the current chat session |
   | **Allow always** | Approves this tool for all subsequent invocations |

   To reset tool approval settings, go to **Tools** > **Options** > **GitHub** > **Copilot** > **Tools**.

1. Copilot monitors the outcome of each step. If a query returns an error or a result that doesn't meet your goal, Copilot revises its approach and tries again automatically.
1. When the task is complete, Copilot summarizes what it did. Review any changes applied to your database or the query editor.

## Understand Agent mode tools

In Agent mode, Copilot can use the following tools to complete your request:

- Built-in tools
- [Model Context Protocol (MCP) tools](mcp-servers.md)
- [Agent skills](agent-skills.md) that provide task-specific instructions

> [!NOTE]  
> Agent mode works only with databases and objects that you can access or connect to, or by using credentials in the database `CONSTITUTION.md` file. It doesn't have elevated permissions beyond those your credentials already have.

To view and manage the tools available in Agent mode, select the **Tools** icon in the chat window. Based on the outcome of a tool, Copilot might invoke other tools to accomplish the overall request. For example, if a T-SQL code edit results in a syntax error, Copilot might explore another approach and suggest a different change.

You can also extend Agent mode with [MCP servers](mcp-servers.md) to connect Copilot to external tools and services. The tools available for an MCP server aren't automatically enabled. Their checkboxes are cleared by default, and you must select them to activate the tools.

## Manage tool approvals

Copilot requests confirmation before running any query or invoking an external tool. This step protects you from unintended changes. By default, each action requires an explicit approval.

When approving a tool, use the **Allow** dropdown list to set persistence:

- **Allow for this session**: no further prompts for that tool in the current chat session
- **Allow always**: persisted across sessions for that tool

To review and reset approvals, go to **Tools** > **Options** > **GitHub** > **Copilot** > **Tools**.

## Accept or discard edits

When Agent mode applies changes to open files, a **Total changes** summary appears in the chat window. Select each file to review changes individually. You can keep or undo edits made to each section of code using the **Keep** and **Undo** buttons. Alternatively, in the **Total changes** list, select **Keep** or **Undo** for all edits made since the last time that you selected **Keep** or **Undo**.

### Multi-file summary view

Starting in SSMS 22.6, when Copilot edits multiple files, you can review all changes in a single summary view instead of switching between files individually.

1. After Copilot finishes editing, select the **Open changes summary view** button in the Copilot Chat working set.
1. A single tab opens that shows all changed files with the differences listed.
1. You can accept or undo changes at different levels of granularity:

- Across all files at once, using the global **Keep files** and **Undo files** buttons.
- For each file using the **Keep All Changes** and **Undo All** buttons.
- For each individual code change, using **Keep** (<kbd>Ctrl</kbd> + <kbd>Y</kbd>) and **Undo** (<kbd>Ctrl</kbd> + <kbd>N</kbd>).

1. Use the controls in the top-left corner of the window to:

- Collapse all file contents to see only file headers for a quick overview
- Navigate between diff chunks using the next and previous buttons to jump through changes quickly
  You can also select any file to open it separately and see its full context.

## Interrupt an Agent mode request

To stop an ongoing Agent mode request at any time, select **Cancel** in the chat window. Canceling stops all running tools and pending queries. Any queries already executed and approved **aren't** automatically rolled back. Verify your database state after canceling a multi-step operation if needed.

## Scenarios

The following examples show how Agent mode handles common SQL Server tasks. These examples are representative prompts. Adapt them to your database and goals.

### Create and test a stored procedure

```copilot-prompt
Within the WideWorldImporters database on the PRD-Sales server, create a stored procedure named Sales.GetTopCustomers that accepts a date range and a row count, and returns the top N customers by total order value in that date range. Include error handling and test it with sample parameters.
```

Agent mode reads the schema of your database to identify the appropriate tables, drafts the stored procedure, executes the `CREATE PROCEDURE` statement, and then runs a test execution with sample parameters to validate the output.

### Optimize query performance

```copilot-prompt
The query in the active editor, connected to AdventureWorks on the TEST-AW server is running slowly. Analyze its execution plan and suggest options to improve performance.
```

Agent mode can generate an estimated execution plan for your query, use Query Store to find the plan, or use an actual plan if you include it as a reference. It identifies anti-patterns in the query and the execution plans, including missing indexes. It proposes specific code and schema changes, including `CREATE INDEX` statements, and can implement the changes if you approve. Always implement changes in a test or development environment before applying them to a production database.

### Investigate logs

```copilot-prompt
Analyze the SQL ERRORLOG for the PRD-HR server for the last month and give me a list of errors and problems and solutions for fixing them.
```

Agent mode reviews the ERRORLOG files for the instance, creates a list of identified issues, and generates suggestions for resolution.

### Audit and fix permission gaps

```copilot-prompt
Review the permissions for the Reporting role in the CustomerSales database on the PRD-Sales server and identify any tables in the Sales schema that it can't access. Add the missing SELECT permissions.
```

Agent mode queries the permission catalog views, identifies gaps, generates `GRANT` statements, and executes them if you approve.

## Execution context and permissions

All queries and commands that Agent mode executes run in the context of your authenticated account, unless you designate a database user or SQL login for GitHub Copilot in the database's `CONSTITUTION.md` as the `agentExecuteAsUser`.

- If your login doesn't have permission to modify a table, Agent mode can't modify it either, even if you approve the proposed query.
- Copilot's approval system isn't a security boundary. Apply the principle of least-privilege in your database: grant users only the permissions they need on specific objects.
- For databases where you want to specify a database user or SQL login, see [Execution context for GitHub Copilot in SQL Server Management Studio](execution-context.md).
- If a database user or SQL login is designated for a database, and the user of GitHub Copilot doesn't have IMPERSONATE permission, they can't use GitHub Copilot for that database.

By default, Agent mode is configured as `READ_ONLY`. If your login, or the `agentExecuteAsUser` account, has permissions to modify data or the database schema, GitHub Copilot doesn't execute those queries by default.

You can change Agent mode to `READ_WRITE` in the mcp.json file. However, if your login or the `agentExecuteAsUser` account doesn't have permission to modify data or the database schema, any such queries fail due to SQL security permissions.

## Frequently asked questions

### Does Agent mode execute queries automatically without asking me?

No. Agent mode requests your approval before executing every query or command. You can choose to allow a tool for the current session or always to reduce approval prompts.

### What happens if a query fails?

Agent mode detects the error, analyzes it, and revises its approach automatically. It attempts to resolve the issue without further input from you. If it can't resolve the error after several attempts, it reports the failure and asks for your guidance.

### How is Agent mode different from Ask mode?

Ask mode returns a single response and stops. You decide whether to apply the generated code. Agent mode runs multiple steps autonomously, executes queries with your approval, monitors outcomes, and iterates. Use Ask mode when you want full control over every step; use Agent mode for complex multi-step tasks where you only provide guidance.

### Can I use Agent mode with MCP servers?

Yes. You must be in Agent mode to use MCP tools. See [Use MCP servers with GitHub Copilot in SQL Server Management Studio](mcp-servers.md).

### As an administrator, how do I control Agent mode for my organization?

Administrators control Agent mode through the GitHub Copilot dashboard. For more information, see [Admin controls for GitHub Copilot in SQL Server Management Studio](admin-controls.md).

## Related content

- [Use the GitHub Copilot Chat experience in SQL Server Management Studio](chat.md)
- [Use Agent skills with GitHub Copilot in SQL Server Management Studio](agent-skills.md)
- [Use MCP servers with GitHub Copilot in SQL Server Management Studio](mcp-servers.md)
- [Execution context for GitHub Copilot in SQL Server Management Studio](execution-context.md)
- [Troubleshoot GitHub Copilot in SQL Server Management Studio](troubleshoot.md)
