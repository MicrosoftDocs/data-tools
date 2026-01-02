---
title: Quickstart - Visual Studio Code local
description: Learn how to start a SQL MCP Server locally using Data API builder without Aspire. Connect Visual Studio Code to your database and execute queries in minutes.
ms.topic: quickstart
ms.date: 12/22/2025
---

# Quickstart: Use SQL MCP Server with Visual Studio Code locally

[!INCLUDE[Section - Quickstart selector](includes/section-quickstart-selector.md)]

[!INCLUDE[Note - Preview](includes/note-preview.md)]

This quickstart uses the Data API builder CLI to run a SQL MCP Server locally without Aspire. You create a database, configure a config file, start SQL MCP Server, and connect to it from Visual Studio Code (VS Code) using a custom tool. This path is the easiest way to explore SQL MCP Server without containers or hosting frameworks.

:::image type="complex" source="media/quickstart-visual-studio-code/diagram.svg" lightbox="media/quickstart-visual-studio-code/diagram.svg" alt-text="Diagram that shows a local SQL MCP Server connected to Visual Studio Code.":::
  This architecture diagram illustrates a local development environment where GitHub Copilot connects to a Local Machine container. Inside the container, three components are arranged horizontally: VS Code (orange box), an MCP (Model Context Protocol) server (green 3D box), and a SQL database (blue cylinder). VS Code connects to the MCP server with a rightward arrow, and the MCP server has a bidirectional connection to the SQL database. This setup allows developers to leverage AI assistance through VS Code and GitHub Copilot for database operations during local development, with the MCP server acting as an intermediary that translates requests into database queries.
:::image-end:::

## Prerequisites

Install these tools before you start.

### 1. .NET 9+

You may already have this tool installed. Run `dotnet --version` and confirm it reports version 9.0 or later. If .NET is already present, reinstalling is safe and only refreshes your runtime.

### 2. SQL Server 2016+

You need access to a SQL Server database. Any of the following work:

* SQL Server (Developer or Express)
* LocalDB (file-based SQL Server)
* SQL Server in Docker

### 3. Install the Data API builder CLI

```bash
dotnet new tool-manifest
dotnet tool install microsoft.dataapibuilder --prerelease
dotnet tool restore
```

> [!NOTE]
> SQL MCP Server is currently in prerelease. Using the `--prerelease` flag ensures you get the latest version of Data API builder with all the features used in this quickstart.

## Step 1: Create your sample database

In this step, you create a database named `ProductsDb` and seed it with a single table named `Products`.

Connect to your SQL instance using SQLCMD, SQL Server Management Studio, or any preferred tool, then run:

```sql
CREATE DATABASE ProductsDb;
GO

USE ProductsDb;
GO

CREATE TABLE dbo.Products (
    Id INT PRIMARY KEY,
    Name NVARCHAR(100) NOT NULL,
    Inventory INT NOT NULL,
    Price DECIMAL(10,2) NOT NULL,
    Cost DECIMAL(10,2) NOT NULL
);

INSERT INTO dbo.Products (Id, Name, Inventory, Price, Cost)
VALUES
    (1, 'Action Figure', 40, 14.99, 5.00),
    (2, 'Building Blocks', 25, 29.99, 10.00),
    (3, 'Puzzle 500 pcs', 30, 12.49, 4.00),
    (4, 'Toy Car', 50, 7.99, 2.50),
    (5, 'Board Game', 20, 34.99, 12.50),
    (6, 'Doll House', 10, 79.99, 30.00),
    (7, 'Stuffed Bear', 45, 15.99, 6.00),
    (8, 'Water Blaster', 35, 19.99, 7.00),
    (9, 'Art Kit', 28, 24.99, 8.00),
    (10,'RC Helicopter', 12, 59.99, 22.00);
```

Your sample database is ready.

## Step 2: Configure SQL MCP Server

Run all commands in the folder where you want to create your `dab-config.json` file.

### Create your environment file

Create a file named `.env` in your working directory and add the following line (customize with your SQL Server information):

```text
MSSQL_CONNECTION_STRING=Server=localhost;Database=ProductsDb;Trusted_Connection=True;TrustServerCertificate=True
```

> [!NOTE]
> Integrated authentication (`Trusted_Connection=True`) works on Windows. For SQL authentication (common with Docker or cross-platform), use `Server=localhost,1433;Database=ProductsDb;User Id=sa;Password=<YourPassword>;TrustServerCertificate=True` instead (assuming your container maps port 1433 to localhost).

Data API builder can read variables from a local `.env` file when present in the working directory. If your environment doesn't support `.env` files, set `MSSQL_CONNECTION_STRING` as an environment variable in your terminal session before running the following commands.

### Initialize and configure the server

Run the following commands:

```bash
dab init --database-type mssql --connection-string "@env('MSSQL_CONNECTION_STRING')" --host-mode Development --config dab-config.json

dab add Products --source dbo.Products --permissions "anonymous:read" --description "Toy store products with inventory, price, and cost."
```

### Optionally add field descriptions

```bash
dab update Products --fields.name Id --fields.primary-key true --fields.description "Product Id"
dab update Products --fields.name Name --fields.description "Product name"
dab update Products --fields.name Inventory --fields.description "Units in stock"
dab update Products --fields.name Price --fields.description "Retail price"
dab update Products --fields.name Cost --fields.description "Store cost"
```

Your SQL MCP Server is fully configured.

## Step 3: Start SQL MCP Server

Before connecting from VS Code, start the SQL MCP Server in a separate terminal.

### Open a terminal and run

```bash
dab start --config dab-config.json
```

This command starts the SQL MCP Server. After startup, the terminal output shows the listening URLs. This quickstart assumes the MCP endpoint is `http://localhost:5000/mcp`. Keep this terminal running - Visual Studio Code connects to this HTTP endpoint.

> [!NOTE]
> You can customize the port by configuring the runtime settings in your `dab-config.json` or by setting environment variables such as `ASPNETCORE_URLS`.

## Step 4: Connect from VS Code

> [!IMPORTANT]
> A workspace is the root folder that VS Code treats as your project. Settings and MCP server definitions only apply inside that folder. If you open a single file, you aren't in a workspace. You must open a folder.

### Open your project folder

1. Select **File** > **Open Folder**.
2. Open the folder that contains your `dab-config.json` file.

### Create your MCP server definition

Create a file named `.vscode/mcp.json` and add the following content:

```json
{
  "servers": {
    "sql-mcp-server": {
      "type": "http",
      "url": "http://localhost:5000/mcp"
    }
  }
}
```

Save the file. VS Code should detect the MCP server configuration and connect to the running SQL MCP Server at the specified HTTP endpoint. You may need to reload the window (**Developer: Reload Window** from the Command Palette).

The `Products` entity appears as MCP tools such as `describe_entities` and `read_records`. Tool names may vary based on your configuration.

> [!NOTE]
> VS Code MCP support is evolving. The configuration schema may change in future releases. For the latest guidance, see the VS Code documentation for MCP integration.

### Try a tool call

Open the VS Code chat and try this prompt:

```text
@sql-mcp-server Which products have an inventory under 30?
```

You should see the toy store data you inserted earlier.

## Related content

- [Overview of SQL MCP Server](overview.md)
- [Data manipulation tools in SQL MCP Server](data-manipulation-language-tools.md)
- [Adding semantic descriptions to SQL MCP Server](how-to-add-descriptions.md)
