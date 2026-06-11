---
title: MCP Servers
titleSuffix: GitHub Copilot in SQL Server Management Studio
description: Learn how to use Model Context Protocol (MCP) servers with GitHub Copilot Agent mode in SQL Server Management Studio (SSMS) to extend Copilot capabilities.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: erinstellato
ms.date: 06/09/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to connect MCP servers to GitHub Copilot Agent mode in SQL Server Management Studio so that I can extend Copilot capabilities.
---

# Use MCP servers with GitHub Copilot in SQL Server Management Studio

Model Context Protocol (MCP) is an open standard that lets GitHub Copilot use tools and services outside of SSMS. With MCP, Agent mode (currently in preview) can interact with external systems such as source control, documentation, your internal ticketing system, and other APIs. You use the same conversational interface for these systems alongside database tasks.

MCP works through a client-server model:

- MCP clients (such as SSMS) connect to MCP servers and request actions on behalf of the AI model.
- MCP servers expose one or more tools through a well-defined interface. Each tool performs a specific action, such as creating a work item, listing open tickets, or querying an external API.
- The protocol defines the message format for tool discovery, invocation, and response handling.

You must be in [Agent mode](agent-mode.md) to use MCP. Ask mode doesn't support MCP.

> [!NOTE]  
> MCP tools are disabled by default after you add a server. You must manually enable each tool in the Tools list in the Copilot Chat window before Copilot can use it.

## Prerequisites

- SSMS 22.7 or a later version with the [AI Assistance workload](installation-state.md#install-github-copilot-in-ssms-using-the-visual-studio-installer).
- A GitHub account with [Copilot access](https://docs.github.com/copilot/get-started/what-is-github-copilot#getting-access-to-copilot). Alternatively, [use GitHub Copilot for free in SQL Server Management Studio](free-plan.md).

## Find MCP servers

The [official MCP server repository](https://github.com/modelcontextprotocol/servers) is a good starting point. It lists reference implementations and community-contributed servers for a wide range of services, including file systems, databases, DevOps platforms, and web APIs.

MCP is a rapidly evolving ecosystem. The official MCP server repository lists current servers you can integrate into your workflows.

## Add an MCP server

### Add an MCP server from chat

Add MCP servers from the Tools picker manually, or through the MCP registry.

To add MCP servers manually:

1. In the Copilot Chat window, select the **Tools** icon to open the Tools panel.
1. Select the green **+** button at the top of the panel, then **Add custom MCP server**.
1. Enter the **Server ID** and select the appropriate connection from the **Type** dropdown list:
   - For HTTP servers, enter the server URL.
   - For `stdio` servers, enter the command and any arguments needed to launch the server process.
1. Save the configuration. SSMS initializes the server and adds its tools to the Tools list.

To add MCP servers from the registry:

1. In the Copilot Chat window, select the **Tools** icon to open the Tools panel.
1. Select the green **+** button at the top of the panel, then **Add from MCP registry**.
1. Within the **MCP Server Manager** window, find the MCP server and select **Install**.
1. Once installed, the MCP server appears in the **Added** servers section of the Tools panel.

By default, tools aren't enabled for an MCP server you install. You must enable them through the Tools panel.

### Add an MCP server to the `.mcp.json` file

The `.mcp.json` file is a manual option to configure MCP servers.

1. Create or open `%USERPROFILE%\.mcp.json`. This global configuration file makes the MCP servers available for your user account.
1. Paste the server configuration into the file using the following format:

   ```json
   {
     "servers": {
       "github": {
         "url": "https://api.githubcopilot.com/mcp/"
       }
     }
   }
   ```

1. Save the file. SSMS detects the change, initializes the configured servers, and makes the MCP available in the Tools window.
1. If a server requires authentication, an **Authentication Required** link appears in the file. Select it to complete the authentication flow.

For more information on MCP server configuration, see Visual Studio's [Use MCP servers](/visualstudio/ide/mcp-servers).

## Available MCP servers

The GitHub policy settings on the GitHub Copilot dashboard for administrators govern Agent mode and MCP usage in SSMS. If the administrator turns off this setting, users under that subscription can't use Agent mode or connect to MCP servers in SSMS.

Additionally, administrators can configure an MCP server allow list to control exactly which MCP servers are permitted within their organization. For more information, see [Configure the MCP server allow list](admin-controls.md#configure-the-mcp-server-allow-list).

For more information, see [Managing policies and features for GitHub Copilot in your enterprise](https://docs.github.com/enterprise-cloud@latest/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-enterprise-policies).

## Related content

- [Use GitHub Copilot Agent mode (preview) in SQL Server Management Studio](agent-mode.md)
- [Admin controls for GitHub Copilot in SQL Server Management Studio](admin-controls.md)
- [Troubleshoot GitHub Copilot in SQL Server Management Studio](troubleshoot.md)
