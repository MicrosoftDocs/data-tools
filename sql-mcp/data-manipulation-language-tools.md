---
title: Data Manipulation Language Tools (DMT)
description: Reference guide for the six DML tools that SQL MCP Server exposes to AI agents.
ms.topic: concept-article
ms.date: 12/22/2025
---

# Data manipulation language (DML) tools in SQL MCP Server

[!INCLUDE[Note - Preview](includes/note-preview.md)]

SQL MCP Server exposes six Data Manipulation Language (DML) tools to AI agents. These tools provide a typed CRUD surface for database operations—creating, reading, updating, and deleting records plus executing stored procedures. All tools respect role-based access control (RBAC), entity permissions, and policies defined in your configuration.

## What are DML tools?

DML (Data Manipulation Language) tools handle data operations: creating, reading, updating, and deleting records, plus executing stored procedures. Unlike DDL (Data Definition Language) which modifies schema, DML works exclusively on the data plane in existing tables and views.

The six DML tools are:

- `describe_entities` - Discovers available entities and operations
- `create_record` - Inserts new rows
- `read_records` - Queries tables and views
- `update_record` - Modifies existing rows
- `delete_record` - Removes rows
- `execute_entity` - Runs stored procedures

When DML tools are enabled globally and for an entity, SQL MCP Server exposes them through the MCP protocol. Agents never interact directly with your database schema - they work through the Data API builder abstraction layer.

## The tools

### list_tools response

When an agent calls `list_tools`, SQL MCP Server returns:

```json
{
  "tools": [
    { "name": "describe_entities" },
    { "name": "create_record" },
    { "name": "read_records" },
    { "name": "update_record" },
    { "name": "delete_record" },
    { "name": "execute_entity" }
  ]
}
```

### describe_entities

Returns the entities available to the current role. Each entry includes field names, data types, primary keys, and allowed operations. This tool doesn't query the database. Instead, it reads from the in-memory configuration built from your config file.

```json
{
  "entities": [
    {
      "name": "Products",
      "description": "Product catalog with pricing and inventory",
      "fields": [
        {
          "name": "ProductId",
          "type": "int",
          "isKey": true,
          "description": "Unique product identifier"
        },
        {
          "name": "ProductName",
          "type": "string",
          "description": "Display name of the product"
        },
        {
          "name": "Price",
          "type": "decimal",
          "description": "Retail price in USD"
        }
      ],
      "operations": [
        "read_records",
        "update_record"
      ]
    }
  ]
}
```

> [!NOTE]
> The entity options used by any of the CRUD and execute DML tools come directly from `describe_entities`. The internal semantic description attached to each tool enforces this two-step flow.

### create_record

Creates a new row in a table. Requires create permission on the entity for the current role. The tool validates input against the entity schema, enforces field-level permissions, applies create policies, and returns the created record with any generated values.

### read_records

Queries a table or view. Supports filtering, sorting, pagination, and field selection. The tool builds deterministic SQL from structured parameters, applies read permissions and field projections, and enforces row-level security policies.

Results from `read_records` are automatically cached using Data API builder's caching system. You can configure cache time-to-live (TTL) globally or per-entity to reduce database load.

### update_record

Modifies an existing row. Requires the primary key and fields to update. The tool validates the primary key exists, enforces update permissions and policies, and only updates fields the current role can modify.

### delete_record

Removes an existing row. Requires the primary key. The tool validates the primary key exists, enforces delete permissions and policies, and performs safe deletion with transaction support.

> [!WARNING]
> Some production scenarios will disable this tool globally to broadly constrain models.

### execute_entity

Runs a stored procedure. Supports input parameters and output results. The tool validates input parameters against the procedure signature, enforces execute permissions, and passes parameters safely.

## Runtime configuration

Configure DML tools globally in the runtime section of your `dab-config.json`:

```json
{
  "runtime": {
    "mcp": {
      "enabled": true,
      "path": "/mcp",
      "dml-tools": {
        "describe-entities": true,
        "create-record": true,
        "read-records": true,
        "update-record": true,
        "delete-record": true,
        "execute-entity": true
      }
    }
  }
}
```

### Using the CLI

Set properties individually using the Data API builder CLI:

```bash
dab configure --runtime.mcp.enabled true
dab configure --runtime.mcp.path "/mcp"
dab configure --runtime.mcp.dml-tools.describe-entities true
dab configure --runtime.mcp.dml-tools.create-record true
dab configure --runtime.mcp.dml-tools.read-records true
dab configure --runtime.mcp.dml-tools.update-record true
dab configure --runtime.mcp.dml-tools.delete-record true
dab configure --runtime.mcp.dml-tools.execute-entity true
```

### Disabling tools

When you disable a tool at the runtime level, it never appears to agents, regardless of entity permissions or role configuration. This setting is useful when you need strict operational boundaries.

#### Common scenarios

- Disable `delete-record` to prevent data loss in production
- Disable `create-record` for read-only reporting endpoints
- Disable `execute-entity` when stored procedures aren't used

When a tool is disabled globally, the tool is hidden from the `list_tools` response and can't be invoked.

## Entity settings

Entities participate in MCP automatically unless you explicitly restrict them. The `dml-tools` property exists so you can exclude an entity from MCP or narrow its capabilities, but you don't need to set anything for normal use.

```json
{
  "entities": {
    "Products": {
      "mcp": {
        "dml-tools": true
      }
    },
    "SensitiveData": {
      "mcp": {
        "dml-tools": false
      }
    }
  }
}
```

If you don't specify `mcp.dml-tools` on an entity, it defaults to `true` when MCP is enabled globally.

### Fine-grained control

You can disable specific tools for individual entities:

```json
{
  "entities": {
    "AuditLogs": {
      "mcp": {
        "dml-tools": {
          "create-record": true,
          "read-records": true,
          "update-record": false,
          "delete-record": false
        }
      }
    }
  }
}
```

This configuration allows agents to create and read audit logs but prevents modification or deletion.

## RBAC integration

Every DML tool operation enforces your role-based access control rules. An agent's role determines which entities are visible, which operations are allowed, which fields are included, and whether row-level policies apply.

If the `anonymous` role only allows read permission on `Products`:

- `describe_entities` only shows `read_records` in operations
- `create_record`, `update_record`, and `delete_record` aren't available
- Only fields allowed for `anonymous` appear in the schema

### Configure roles in your `dab-config.json`:

```json
{
  "entities": {
    "Products": {
      "permissions": [
        {
          "role": "anonymous",
          "actions": [
            {
              "action": "read",
              "fields": {
                "include": ["ProductId", "ProductName", "Price"],
                "exclude": ["Cost"]
              }
            }
          ]
        },
        {
          "role": "admin",
          "actions": ["*"]
        }
      ]
    }
  }
}
```

## Related content

- [Overview of SQL MCP Server](overview.md)
- [Adding semantic descriptions to SQL MCP Server](how-to-add-descriptions.md)
- [Data API builder (DAB) configuration reference](/azure/data-api-builder/configuration)
- [Deploy SQL MCP Server to Azure Container Apps](quickstart-azure-container-apps.md)
