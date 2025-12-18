---
title: Overview/Introduction
titleSuffix: SQL MCP Server
description: Learn how SQL MCP Server enables AI agents to safely interact with SQL databases. Configure your data source and expose tables, views, and stored procedures through MCP tools.
author: jnixon
ms.author: jerrynixon
ms.reviewer: sidandrews
ms.service: data-api-builder
ms.topic: overview
ms.date: 12/18/2025
---

# What is SQL MCP Server?

[!INCLUDE[Note - Preview](includes/note-preview.md)]

SQL MCP Server enables AI agents to safely interact with SQL databases through the Model Context Protocol (MCP). This open-source engine, included with Data API builder (DAB) starting in version 1.7, lets you configure database access through a JSON file that defines connections, exposed objects, and permissions. Agents can perform controlled SQL operations through MCP tools without direct database access.

## Model Context Protocol (MCP)

Model Context Protocol (MCP) is a standard that defines how AI agents discover and call external tools. A tool is a single operation such as creating a record or reading data. Each tool describes its inputs, outputs, and behavior. MCP provides a predictable way for agents to discover and use capabilities.

## MCP server for SQL

SQL MCP Server is Microsoft's dynamic, open source engine for agentic apps. You configure it with a JSON file that defines:

- How to connect to your database
- Which tables, views, or stored procedures to expose
- The permissions that apply to each object

SQL MCP Server is included as part of Data API builder (DAB) starting in version 1.7. It exposes SQL operations as a small [family of MCP tools](#the-dml-tools) so agents can interact with database entities through a controlled contract. The server is self hosted but, for developers, it can also run locally through the [DAB command-line](../command-line/index.yml).

> [!TIP]
> Data API builder is open source and free to use.

## Use cases

Here are some typical use cases for SQL MCP Server:

- Allow copilots or chatbots to perform safe CRUD operations
- Build internal automations without writing SQL
- Add agent capabilities without exposing the database directly
