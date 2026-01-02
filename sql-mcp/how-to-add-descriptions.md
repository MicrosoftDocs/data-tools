---
title: Add Descriptions to Entities
description: Learn how to add semantic descriptions to SQL MCP Server entities, fields, and parameters to improve AI agent accuracy. Includes CLI examples and best practices.
ms.topic: how-to
ms.date: 12/22/2025
---

# Add descriptions to SQL MCP Server entities

[!INCLUDE[Note - Preview](includes/note-preview.md)]

Descriptions are semantic metadata that help AI agents understand your SQL MCP Server database schema. When you add descriptions to entities, fields, and parameters, language models make better decisions about which data to query and how to use it. This article shows you how to add descriptions at every level using the Data API builder CLI, improving AI agent accuracy and tool discovery.

## Why add descriptions?

AI agents rely on context to understand your data. Without descriptions, an agent only sees technical names like `ProductID` or `dbo.Orders`. With descriptions, the agent understands that `ProductID` is "Unique identifier for each product in the catalog" and `dbo.Orders` contains "Customer purchase orders with line items and shipping details."

### Descriptions improve:

- **Tool discovery** - Agents find the right entities faster
- **Query accuracy** - Agents build better queries with proper context
- **Parameter usage** - Agents supply correct values to stored procedures
- **Field selection** - Agents return only relevant fields

> [!TIP]
> Descriptions are exposed through the `describe_entities` MCP tool and help language models make informed decisions without guessing.

## Entity descriptions

Entity descriptions explain what a table, view, or stored procedure represents. Add them when you create or update an entity.

### Add descriptions with `dab add`

When adding a new entity, use the `--description` flag:

```bash
dab add Products \
  --source dbo.Products \
  --permissions "anonymous:*" \
  --description "Product catalog with pricing, inventory, and supplier information"
```

### Add descriptions with `dab update`

You can add or change descriptions on existing entities:

```bash
dab update Products \
  --description "Product catalog with pricing, inventory, and supplier information"
```

### Examples

#### Table description:

```bash
dab add Orders \
  --source dbo.Orders \
  --permissions "authenticated:read" \
  --description "Customer purchase orders with line items, shipping details, and payment status"
```

#### View description:

```bash
dab add ActiveProducts \
  --source dbo.vw_ActiveProducts \
  --source.type view \
  --source.key-fields "ProductID" \
  --permissions "anonymous:read" \
  --description "Currently available products with positive inventory and active status"
```

#### Stored procedure description:

```bash
dab add GetOrderHistory \
  --source dbo.usp_GetOrderHistory \
  --source.type stored-procedure \
  --permissions "authenticated:execute" \
  --description "Retrieves complete order history for a customer including items, totals, and shipping tracking"
```

## Field descriptions

Field descriptions explain what each column represents. They help agents understand the purpose and meaning of individual data points.

### Add field descriptions with `dab update`

Use the `--fields.name` and `--fields.description` flags together:

```bash
dab update Products \
  --fields.name ProductID \
  --fields.description "Unique identifier for each product" \
  --fields.primary-key true
```

### Add multiple field descriptions

You can add descriptions to multiple fields by calling `dab update` multiple times:

```bash
dab update Products \
  --fields.name ProductID \
  --fields.description "Unique identifier for each product" \
  --fields.primary-key true

dab update Products \
  --fields.name ProductName \
  --fields.description "Display name of the product"

dab update Products \
  --fields.name UnitPrice \
  --fields.description "Retail price per unit in USD"

dab update Products \
  --fields.name UnitsInStock \
  --fields.description "Current inventory count available for purchase"

dab update Products \
  --fields.name Discontinued \
  --fields.description "True if product is no longer available for sale"
```

### Field description best practices

Use clear, concise descriptions that include:

- **Purpose** - What the field represents
- **Units** - Currency, measurements, time zones
- **Format** - Date formats, string patterns
- **Business rules** - Valid ranges, constraints

#### Good examples:

```bash
# Include units
dab update Products \
  --fields.name Weight \
  --fields.description "Product weight in kilograms"

# Include format details
dab update Orders \
  --fields.name OrderDate \
  --fields.description "Order placement date in UTC (ISO 8601 format)"

# Include business context
dab update Employees \
  --fields.name HireDate \
  --fields.description "Date employee was hired, used for calculating benefits eligibility"

# Include constraints
dab update Products \
  --fields.name ReorderLevel \
  --fields.description "Minimum stock level that triggers automatic reorder (must be positive integer)"
```

## Parameter descriptions

Parameter descriptions help agents understand what values to supply when executing stored procedures. This approach is especially important for MCP tools that call stored procedures.

### Add parameter descriptions with `dab add`

When adding a stored procedure, use comma-separated lists for parameter metadata:

```bash
dab add GetOrdersByDateRange \
  --source dbo.usp_GetOrdersByDateRange \
  --source.type stored-procedure \
  --permissions "authenticated:execute" \
  --description "Retrieves all orders placed within a specified date range" \
  --parameters.name "StartDate,EndDate,CustomerID" \
  --parameters.description "Beginning of date range (inclusive),End of date range (inclusive),Optional customer ID filter (null returns all customers)" \
  --parameters.required "true,true,false" \
  --parameters.default ",,null"
```

### Add parameter descriptions with `dab update`

You can update parameter descriptions on existing stored procedures:

```bash
dab update GetOrdersByDateRange \
  --parameters.name "StartDate,EndDate,CustomerID" \
  --parameters.description "Beginning of date range (inclusive),End of date range (inclusive),Optional customer ID filter (null returns all customers)" \
  --parameters.required "true,true,false"
```

### Parameter description format

Parameters use comma-separated lists where:

- `--parameters.name` - Parameter names in order
- `--parameters.description` - Corresponding descriptions
- `--parameters.required` - Whether each parameter is required (`true`/`false`)
- `--parameters.default` - Default values (empty string for required parameters)

#### Example with detailed parameter descriptions:

```bash
dab add SearchProducts \
  --source dbo.usp_SearchProducts \
  --source.type stored-procedure \
  --permissions "anonymous:execute" \
  --description "Searches products by keyword, category, and price range" \
  --parameters.name "SearchTerm,CategoryID,MinPrice,MaxPrice,PageSize,PageNumber" \
  --parameters.description "Keyword to search in product names and descriptions,Product category ID (null searches all categories),Minimum price filter in USD (null removes lower bound),Maximum price filter in USD (null removes upper bound),Number of results per page (default 20, max 100),Page number for pagination (1-based)" \
  --parameters.required "true,false,false,false,false,false" \
  --parameters.default ",null,null,null,20,1"
```

## Complete example workflow

Here's a complete example showing how to add descriptions at every level:

### 1. Create the entity with a description

```bash
dab add Customers \
  --source dbo.Customers \
  --permissions "authenticated:read,update" \
  --description "Customer master records including contact information, billing preferences, and account status"
```

### 2. Add field descriptions

```bash
dab update Customers \
  --fields.name CustomerID \
  --fields.description "Unique customer identifier (auto-generated)" \
  --fields.primary-key true

dab update Customers \
  --fields.name CompanyName \
  --fields.description "Customer company or organization name"

dab update Customers \
  --fields.name ContactEmail \
  --fields.description "Primary contact email address for order notifications"

dab update Customers \
  --fields.name Phone \
  --fields.description "Primary phone number in E.164 format (+1234567890)"

dab update Customers \
  --fields.name AccountBalance \
  --fields.description "Current account balance in USD (negative indicates credit)"

dab update Customers \
  --fields.name PreferredCurrency \
  --fields.description "Customer's preferred billing currency (ISO 4217 code)"

dab update Customers \
  --fields.name IsActive \
  --fields.description "Account status flag (false indicates suspended or closed account)"

dab update Customers \
  --fields.name CreatedDate \
  --fields.description "Account creation timestamp in UTC"

dab update Customers \
  --fields.name LastOrderDate \
  --fields.description "Date of most recent order (null for customers with no orders)"
```

### 3. Add a related stored procedure with parameter descriptions

```bash
dab add UpdateCustomerPreferences \
  --source dbo.usp_UpdateCustomerPreferences \
  --source.type stored-procedure \
  --permissions "authenticated:execute" \
  --description "Updates customer communication and billing preferences" \
  --parameters.name "CustomerID,EmailNotifications,SMSNotifications,PreferredCurrency,MarketingOptIn" \
  --parameters.description "Customer ID to update,Enable email notifications for orders and promotions,Enable SMS notifications for shipping updates,Preferred billing currency (ISO 4217 code),Opt in to marketing communications" \
  --parameters.required "true,false,false,false,false" \
  --parameters.default ",true,false,USD,false"
```

## Viewing descriptions in configuration

Descriptions are stored in your `dab-config.json` file. Here's how they appear:

```json
{
  "entities": {
    "Products": {
      "description": "Product catalog with pricing, inventory, and supplier information",
      "source": {
        "object": "dbo.Products",
        "type": "table"
      },
      "fields": {
        "ProductID": {
          "description": "Unique identifier for each product",
          "isPrimaryKey": true
        },
        "ProductName": {
          "description": "Display name of the product"
        },
        "UnitPrice": {
          "description": "Retail price per unit in USD"
        }
      },
      "permissions": [
        {
          "role": "anonymous",
          "actions": ["*"]
        }
      ]
    },
    "GetOrdersByDateRange": {
      "description": "Retrieves all orders placed within a specified date range",
      "source": {
        "object": "dbo.usp_GetOrdersByDateRange",
        "type": "stored-procedure",
        "parameters": {
          "StartDate": {
            "description": "Beginning of date range (inclusive)",
            "required": true
          },
          "EndDate": {
            "description": "End of date range (inclusive)",
            "required": true
          },
          "CustomerID": {
            "description": "Optional customer ID filter (null returns all customers)",
            "required": false,
            "default": null
          }
        }
      },
      "permissions": [
        {
          "role": "authenticated",
          "actions": ["execute"]
        }
      ]
    }
  }
}
```

## How agents use descriptions

When an AI agent calls the `describe_entities` MCP tool, it receives your descriptions along with schema information:

```json
{
  "entities": [
    {
      "name": "Products",
      "description": "Product catalog with pricing, inventory, and supplier information",
      "fields": [
        {
          "name": "ProductID",
          "type": "int",
          "description": "Unique identifier for each product",
          "isKey": true
        },
        {
          "name": "UnitPrice",
          "type": "decimal",
          "description": "Retail price per unit in USD"
        }
      ],
      "operations": ["read_records", "create_record", "update_record"]
    }
  ]
}
```

The agent uses this information to:

1. **Select the right entity** - Matches user intent to entity descriptions
2. **Choose relevant fields** - Returns only the fields needed based on descriptions
3. **Build accurate queries** - Understands relationships and constraints
4. **Supply correct parameters** - Provides appropriate values to stored procedures

## Best practices

### Do

- **Be specific** - "Customer shipping address" is better than "Address"
- **Include units** - "Price in USD", "Weight in kilograms"
- **Mention formats** - "ISO 8601 date format", "E.164 phone format"
- **Explain business rules** - "Negative values indicate credit balance"
- **Note optional fields** - "Optional; null returns all results"
- **Keep descriptions current** - Update descriptions when schema changes

### Don't

- **Don't use technical jargon only** - Add business context alongside technical details
- **Don't duplicate field names** - "ProductID is the product ID" adds no value
- **Don't write novels** - Keep descriptions concise (one to two sentences)
- **Don't forget parameter order** - Ensure comma-separated lists align properly
- **Don't ignore nullable fields** - Mention when null values have special meaning

## Scripting description updates

For large schemas, you can script description updates using a loop:

```bash
#!/bin/bash

# Array of field descriptions for Products table
declare -a fields=(
  "ProductID:Unique identifier for each product:true"
  "ProductName:Display name of the product:false"
  "SupplierID:ID of the supplier providing this product:false"
  "CategoryID:Product category classification:false"
  "QuantityPerUnit:Standard packaging quantity (e.g., '12 bottles per case'):false"
  "UnitPrice:Retail price per unit in USD:false"
  "UnitsInStock:Current inventory count available for purchase:false"
  "UnitsOnOrder:Quantity ordered from supplier but not yet received:false"
  "ReorderLevel:Minimum stock level that triggers automatic reorder:false"
  "Discontinued:True if product is no longer available for sale:false"
)

# Loop through and add descriptions
for field in "${fields[@]}"; do
  IFS=':' read -r name desc is_pk <<< "$field"
  if [ "$is_pk" = "true" ]; then
    dab update Products --fields.name "$name" --fields.description "$desc" --fields.primary-key true
  else
    dab update Products --fields.name "$name" --fields.description "$desc"
  fi
done
```

## Related content

- [Overview of SQL MCP Server](overview.md)
- [Data manipulation tools in SQL MCP Server](data-manipulation-language-tools.md)
- [Data API builder (DAB) configuration reference - `entities`](/azure/data-api-builder/)configuration/index)
- [Data API builder (DAB) command-line interface (CLI) reference - `add`](/azure/data-api-builder/command-line/dab-add)
- [Data API builder (DAB) command-line interface (CLI) reference - `update`](/azure/data-api-builder/command-line/dab-update)
