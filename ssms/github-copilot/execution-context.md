---
title: Execution Context for GitHub Copilot
titleSuffix: GitHub Copilot in SQL Server Management Studio
description: Learn how to configure the execution context for GitHub Copilot in SQL Server Management Studio (SSMS) using the CONSTITUTION.md for the database.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: erinstellato
ms.date: 06/09/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator, I want to configure the execution context for GitHub Copilot Agent mode in SQL Server Management Studio so that I can specify which SQL Server login or database user is used when executing queries.
---

# Execution context for GitHub Copilot in SQL Server Management Studio

GitHub Copilot in SQL Server Management Studio (SSMS) executes queries and commands under the context of your login. This article explains the default execution model, and how to use a database's `CONSTITUTION.md` to specify a particular database user or SQL login to set execution context for database.

## Default execution context

All queries that GitHub Copilot in SSMS generates and executes, in both Ask mode and Agent mode, run under the user or login you used to connect to the database.

> [!NOTE]  
> GitHub Copilot Agent mode in SQL Server Management Studio (SSMS) is currently in preview.

Copilot has no separate permissions and no elevated access. If your user or login can't read a table, Copilot can't read it either.

> [!IMPORTANT]  
> The approval system in Agent mode isn't a security boundary. It confirms your intent before each action, but it doesn't restrict what Copilot can do beyond the permissions already granted to your login. The actual security boundary is SQL Server's permission enforcement. Apply the principle of least-privilege: grant users only the `SELECT`, `EXECUTE`, and other permissions they need on the specific objects they should access.

## Specify GitHub Copilot execution context with CONSTITUTION.md

The database `CONSTITUTION.md` lets database owners specify a database user or SQL login that applies to all GitHub Copilot interactions for that database for both Ask and Agent mode. It's stored as an extended property at the database level. It has the highest precedence of any instruction for that database: it overrides all `AGENTS.md` object-level instructions. When configured, SSMS uses `EXECUTE AS` to run Copilot-generated queries under that specified account.

The signed-in SSMS user must have `IMPERSONATE` permission on the designated Copilot user. Without this permission, Copilot can't execute queries and the feature doesn't work for that user. This behavior is by design: rather than silently falling back to the user's own permissions (which might be overly broad), the system enforces the principle of least privilege. Administrators should grant `IMPERSONATE` on the Copilot execution account to all users who need Copilot access. They can also use the absence of that grant to block Copilot usage for specific users or roles.

To specify a database user or SQL login for GitHub Copilot to use when executing queries, add the `agentExecuteAsUser` property to the YAML front matter of the `CONSTITUTION.md` for the database. The `agentExecuteAsUser` must be added to the front matter of the `CONSTITUTION.md` for it to be recognized by GitHub Copilot.

### agentExecuteAsUser front matter property

```yaml
---
agentExecuteAsUser: <database user or SQL login>
---
```

The `agentExecuteAsUser` property accepts either a database user name or a SQL Server login name. When you set this property, GitHub Copilot uses the specified identity when executing queries against that database.

- The scope is **per-database**. Each database can have its own `CONSTITUTION.md` with a different `agentExecuteAsUser` value.
- Individual `AGENTS.md` object-level instructions **can't** override `agentExecuteAsUser`. The constitution's execution context takes precedence for the entire database.

### Add agentExecuteAsUser to CONSTITUTION.md

Store the `CONSTITUTION.md` instruction as an extended property on the database by using `sp_addextendedproperty`. The `@name` must be `CONSTITUTION.md` and the `@value` contains the full constitution content, including the YAML front matter.

The following example sets `agentExecuteAsUser` to a low-privilege reporting user (`ReportingUser`) and adds a coding standard:

```sql
USE SalesDB;

EXECUTE sp_addextendedproperty
    @name = N'CONSTITUTION.md',
    @value = N'---
agentExecuteAsUser: ReportingUser

---
Any T-SQL generated for this database must comply with organizational standards.
Queries must not use SELECT *. Always use explicit column lists.
Avoid queries that modify data unless explicitly requested by the user.';
```

GitHub Copilot reads the constitution for a database when a user opens a GitHub Copilot session for that database. In this example, GitHub Copilot uses `ReportingUser` as the execution context for queries against that database.

### Front matter with constitution body

The YAML front matter and the Markdown body coexist in the same `CONSTITUTION.md` value. The front matter is delimited by `---` markers at the start of the content. Everything after the closing `---` is treated as the instruction body and is applied as guidance for all Copilot interactions.

```sql
USE SalesDB;

EXECUTE sp_addextendedproperty
    @name = N'CONSTITUTION.md',
    @value = N'---
agentExecuteAsUser: GHCP_DB_User

---
## Database Constitution: SalesDB

This database stores customer orders, product catalog, and revenue data.

### Coding standards
- Always use explicit column lists. Do not use SELECT *.
- Use schema-qualified object names (e.g., Sales.Orders, not Orders).
- Wrap multi-statement scripts in a transaction with TRY/CATCH error handling.

### Restricted operations
- Do not generate TRUNCATE TABLE statements.
- Do not generate DROP statements without an existence check.
- Revenue calculations must use SUM(NetAmount) from Sales.Transactions, excluding rows where RefundFlag = 1.';
```

## Database user versus SQL login

The `agentExecuteAsUser` property accepts either a database user or a SQL Server login. Use the following guidance to choose what is most appropriate for your environment:

| | Database user | SQL login |
| --- | --- | --- |
| **Scope** | Specific to one database | Server-wide identity |
| **When to use** | When you want to set permissions at the database level | When you want to set permissions for a server-level identity |
| **Recommendation** | Offers more granular control | Use when a server-level identity is required |

For most deployments, specifying a database user provides the most granular control. Create a dedicated low-privilege database user for GitHub Copilot, and grant it only the permissions needed for the expected Copilot interactions in that database.

### Example: create a dedicated database user with limited permissions

```sql
/* Create a database user that is not mapped to a SQL login */
USE SalesDB;

CREATE USER GHCP_DB_User WITHOUT LOGIN;

/* Grant only the permissions Copilot needs */
GRANT SELECT ON SCHEMA::Sales TO GHCP_DB_User;
GRANT SELECT ON SCHEMA::Reporting TO GHCP_DB_User;
GRANT EXECUTE ON SCHEMA::Sales TO GHCP_DB_User;

/* Do not grant DDL permissions unless schema modification is expected */
```

Then set `agentExecuteAsUser: GHCP_DB_User` in the `CONSTITUTION.md` for the `SalesDB` database.

## Best practices

- **Use a dedicated, low-privilege account**: Create a specific database user or login for GitHub Copilot rather than reusing an existing user. This approach minimizes the risk of incorrectly assigning permissions to GitHub Copilot users if the user or login is used for another purpose.

- **Grant only what is needed**: Review the typical Copilot use cases for your database and grant only the permissions required. Start with read-only (`SELECT`) access and add modification permissions deliberately.

- **Avoid highly privileged accounts**: Don't set `agentExecuteAsUser` to `sa`, `dbo`, or any account with high permissions unless the use case explicitly requires it.

- **Audit regularly**: Review the permissions of the `agentExecuteAsUser` account periodically as your database and team requirements change.

- **Remember the execution boundary**: Setting `agentExecuteAsUser` controls what identity Copilot uses, but SQL Server's permission enforcement is the actual security boundary. Ensure the specified account has only the minimum permissions needed.

## Update or remove agentExecuteAsUser

To change the `agentExecuteAsUser` value or update other parts of the constitution, use `sp_updateextendedproperty`:

```sql
USE SalesDB;

EXECUTE sp_updateextendedproperty
    @name = N'CONSTITUTION.md',
    @value = N'---
agentExecuteAsUser: New_GHCP_User

---
Updated constitution content here.';
```

To remove the `CONSTITUTION.md` instruction entirely, use `sp_dropextendedproperty`:

```sql
USE SalesDB;

EXECUTE sp_dropextendedproperty @name = N'CONSTITUTION.md';
```

After removal, GitHub Copilot runs queries under the connected user's login, and no database-level constitution applies.

## Verify the current constitution

To check whether a `CONSTITUTION.md` instruction is set for a database, ask Copilot:

```copilot-prompt
Does this database have a constitution set?
```

Or query the extended properties directly:

```sql
USE SalesDB;

SELECT name,
       CAST (value AS NVARCHAR (MAX)) AS ConstitutionContent
FROM sys.extended_properties
WHERE class = 0
      AND name = N'CONSTITUTION.md';
```

## Related content

- [Use database instructions with GitHub Copilot in SQL Server Management Studio](database-instructions.md)
- [Use GitHub Copilot Agent mode (preview) in SQL Server Management Studio](agent-mode.md)
- [Get started with GitHub Copilot in SQL Server Management Studio](get-started.md)
- [Troubleshoot GitHub Copilot in SQL Server Management Studio](troubleshoot.md)
