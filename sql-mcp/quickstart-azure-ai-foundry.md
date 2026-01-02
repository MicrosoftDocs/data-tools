---
title: Quickstart - Azure AI Foundry
description: Learn how to connect SQL MCP Server to Azure AI Foundry agents using Chat Playground. Test database queries with GPT models - no coding required.
ms.topic: quickstart
ms.date: 12/22/2025
---

# Quickstart: Use SQL MCP Server with Azure AI Foundry

[!INCLUDE[Section - Quickstart selector](includes/section-quickstart-selector.md)]

[!INCLUDE[Note - Preview](includes/note-preview.md)]

This quickstart shows you how to connect a deployed SQL MCP Server to Azure AI Foundry using a Custom MCP Tool. You test everything using the Chat Playground with a chat model such as GPT-5-mini - no coding required.

> [!NOTE]
> The **new Foundry experience** is in preview. You need to select the preview toggle in the header when you access https://ai.azure.com.

:::image type="complex" source="media/quickstart-azure-ai-foundry/diagram.svg" lightbox="media/quickstart-azure-ai-foundry/diagram.svg" alt-text="Diagram that shows a deployed SQL MCP Server connected to Azure AI Foundry.":::
  This architecture diagram illustrates a cloud-based AI agent system deployed in Azure. Within Azure, a Microsoft Foundry environment (blue-bordered rectangle) contains two components: a Custom Agent and a Custom Tool, connected by an arrow showing the flow from agent to tool. Below the Foundry container, an MCP (Model Context Protocol) server (green 3D box) connects to a SQL database (blue cylinder). An arrow flows from the Custom Tool to the MCP server, which has a bidirectional connection to the database. This architecture demonstrates how AI agents in Microsoft Foundry use custom tools to interact with SQL databases through the MCP server as an intermediary layer, enabling AI agents to query and manipulate data without direct database access.
:::image-end:::

## Prerequisites

### 1. Deployed SQL MCP Server

You need a SQL MCP Server deployed to Azure Container Apps with public ingress enabled. If you don't have a deployment yet, complete the [Deploy SQL MCP Server to Azure Container Apps](quickstart-azure-container-apps.md) quickstart first.

You need the MCP endpoint URL from that deployment (for example, `https://your-app.azurecontainerapps.io/mcp`).

### 2. Azure AI Foundry project

You need access to Azure AI Foundry with an existing project and access to a chat model (for example, GPT-5-mini).

## Step 1: Access Azure AI Foundry

1. Navigate to https://ai.azure.com.
2. In the header, select the **new Foundry experience** (preview toggle).
3. Select your Foundry project.
4. In the left navigation, select **Playground**.

> [!NOTE]
> UI text and navigation may vary as Azure AI Foundry evolves. For the latest guidance, see [MCP tools in Azure AI Foundry](/azure/ai-foundry/agents/concepts/tool-catalog).

## Step 2: Create or open an agent

1. Select an existing agent or create a new one.
2. In the agent configuration, locate the **Tools** section on the left panel.

## Step 3: Add a Model Context Protocol tool

1. In the **Tools** section, select **Add** (the button may show a dropdown or **+** icon).
2. Select **Add a new tool** from the dropdown.
3. The **Select a tool** dialog opens with three tabs: **Configured**, **Catalog**, and **Custom**.
4. Select the **Custom** tab at the top.
5. Select **Model Context Protocol (MCP)** from the available options.
6. Select **Create** to proceed.

## Step 4: Configure your MCP connection

The **Add Model Context Protocol tool** dialog appears. Fill in the following information:

### Name (required)

Enter a descriptive name: `products-mcp`.

### Remote MCP Server endpoint (required)

Enter your MCP server URL: `https://<your-container-app-url>/mcp` (from your Azure Container Apps deployment).

### Authentication (required)

Select **Unauthenticated** from the dropdown.

> [!NOTE]
> This configuration works because the Azure Container Apps quickstart configured **anonymous** permissions (for example, `anonymous:read`). At the time of writing, this quickstart uses Unauthenticated mode. If you enable authentication on your MCP server, configure the MCP tool accordingly (authentication configuration is not covered in this quickstart).

Select **Connect** to add the tool.

## Step 5: Configure agent instructions

In the **Instructions** section at the top of the agent configuration, add or replace the text with:

```text
You are a helpful product catalog assistant. When answering questions about products, use the products-mcp tool to query the database. 

The Products entity contains:
- Id: Product identifier
- Name: Product name
- Inventory: Units in stock
- Price: Retail price in USD
- Cost: Store cost in USD

Always use the schema discovery tool first to understand the schema, then use the query tool to retrieve data.
```

## Step 6: Test your agent

Try these prompts in the chat:

### Example 1: Schema discovery

```text
What tables or entities are available in the database?
```

The agent should call a schema discovery tool (such as `describe_entities`) to see the Products entity structure.

### Example 2: Simple query

```text
List all products
```

The agent should call a query tool (such as `read_records`) to retrieve product data.

### Example 3: Price query

```text
Show me products under $20
```

The agent should query products where Price < 20.

### Example 4: Inventory check

```text
Which products are low in stock (less than 30 units)?
```

The agent should filter Inventory < 30.

### Example 5: Complex query

```text
What's the most expensive product, and how many do we have in stock?
```

The agent should:

- Query products sorted by Price descending
- Return the top result with Inventory count

## Step 7: View tool calls

In the Chat Playground, you can see tool calls and their arguments/responses:

- **Tool called**: The schema discovery or query tool used
- **Arguments**: The parameters passed (filters, fields, etc.)
- **Response**: The data returned from your SQL database

## Troubleshooting

### Tool not appearing in Azure AI Foundry

- Verify the MCP URL is correct and accessible.
- Check that the Container App is running with public ingress enabled (see [monitoring guidance](quickstart-azure-container-apps.md#monitoring-and-troubleshooting)).
- Test the `/mcp` endpoint using curl or a REST client to verify reachability.

### Tool calls require approval

- In the MCP tool configuration, ensure **Require approval** is set to `never`.

### Agent not using the tool

- Check your system message includes clear instructions about when to use the tool.
- Try asking more specific questions that relate to the Products data.

For deployment issues, see the [troubleshooting section](quickstart-azure-container-apps.md#monitoring-and-troubleshooting) in the Azure Container Apps deployment guide.

## Related content

- [Overview of SQL MCP Server](overview.md)
- [Data manipulation tools in SQL MCP Server](data-manipulation-language-tools.md)
- [Adding semantic descriptions to SQL MCP Server](how-to-add-descriptions.md)
