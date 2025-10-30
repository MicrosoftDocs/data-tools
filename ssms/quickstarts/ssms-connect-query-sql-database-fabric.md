---
title: Connect and Query SQL Database in Microsoft Fabric
description: Connect to and query a SQL database in Microsoft Fabric using SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: wiassaf, randolphwest
ms.date: 09/15/2025
ms.service: sql-server-management-studio
ms.topic: quickstart
ms.collection:
  - data-tools
ms.custom:
  - intro-quickstart
# CustomerIntent: As a user, I want to connect to and query a SQL database in Microsoft Fabric using SSMS, so that I can perform database operations.
---
# Quickstart: Connect and query a SQL database in Fabric using SQL Server Management Studio (SSMS)

[!INCLUDE [asdb](../includes/applies-to-version/fabricsqldb.md)]

Get started using SQL Server Management Studio (SSMS) to connect to your SQL database in Microsoft Fabric and run some Transact-SQL (T-SQL) commands.

[!INCLUDE [entra-id](../includes/entra-id-hard-coded.md)]

The article demonstrates the following steps:

> [!div class="checklist"]
>
> - Connect to a SQL database in Fabric
> - Create a table in your new database
> - Insert rows into your new table
> - Query the new table and view the results
> - Use the query window table to verify your connection properties
> - Remove database

## Prerequisites

- [Install SQL Server Management Studio](../install/install.md)
- You need an existing Fabric capacity. If you don't, [start a Fabric trial](/fabric/fundamentals/fabric-trial).
- You can use an existing workspace or [create a new Fabric workspace](/fabric/fundamentals/workspaces).
- You must be a member of the [Admin or Member roles for the workspace](/fabric/fundamentals/give-access-workspaces) to create a SQL database.
- Create a [SQL database in Fabric](/fabric/database/sql/create). Start with an new, empty database.

## Connect to a SQL database in Fabric

> [!NOTE]  
> Releases of SSMS prior to 18.6 don't authenticate to Database Engines through Microsoft Entra multifactor authentication (MFA). To continue using MFA, you need [SSMS 18.6](../install/install.md) or a later version.

1. Start SQL Server Management Studio (SSMS). The first time you run SSMS, the **Connect to Server** window opens. If it doesn't open, you can open it manually by selecting **Object Explorer** > **Connect** > **Database Engine**.

   :::image type="content" source="media/ssms-connect-query-sql-database-fabric/connect-object-explorer.png" alt-text="Screenshot of the Connect link in Object Explorer.":::

1. Locate the **server name** and **database name** for your SQL database in the Fabric portal.

   The connection string of the SQL database is similar to the connection string of Azure SQL Database. The server name looks like `<server-unique-identifer>.database.windows.net` and the database name looks like `<database name>-<unique identifier>`.

   To find the SQL connection string for your **SQL database in Fabric**:

   - Go to the settings of your SQL database item. Select **Connection strings**. The **server name** is the `Data source` and the database name is the `Initial Catalog`.
   - Or, in the item list of the workspace, select the `...` menu. Select **Settings** then **Connection strings**.
   - Or, select the **Open in** button and **SQL Server Management Studio**. The server connection information is displayed.

     :::image type="content" source="media/ssms-connect-query-sql-database-fabric/fabric-portal-open-in-sql-server-management-studio.png" alt-text="Screenshot from the Fabric portal of the Open in button." lightbox="media/ssms-connect-query-sql-database-fabric/fabric-portal-open-in-sql-server-management-studio.png":::

     :::image type="content" source="media/ssms-connect-query-sql-database-fabric/fabric-portal-open-in-sql-server-management-studio-server-name-database-name.png" alt-text="Screenshot from the Fabric portal of the SQL Server Management Studio connection dialogue, showing the server name and database name." lightbox="media/ssms-connect-query-sql-database-fabric/fabric-portal-open-in-sql-server-management-studio-server-name-database-name.png":::

1. The **Connect to Server** dialog box appears. Enter the following information, all other settings can be left default:

   | Setting | Suggested value | Details |
   | --- | --- | --- |
   | **Server type** | Database Engine | Select **Database Engine** (usually the default option). |
   | **Server name** | The fully qualified server name | Enter the **Server Name**, including `.database.fabric.microsoft.com,1433`. |
   | **Authentication** | Choose **Microsoft Entra MFA**. | For more information, see [Authentication in SQL database in Microsoft Fabric](/fabric/database/sql/authentication#connect-to-a-sql-database-using-microsoft-entra-authentication). |
   | **Database Name** | Provide the database name of your SQL database. |

   You can also modify additional connection options by selecting **Options**. Examples of connection options are the database you're connecting to, the connection timeout value, and the network protocol. This article uses the default values for all the options.

1. Select **Connect**.

1. To verify that your SQL database in Fabric connection succeeded, expand and explore the objects within **Object Explorer** where the server name, the SQL Server version, and the username are displayed. These objects are different depending on the server type.

## Troubleshoot connectivity issues

- If your browser fails to connect to SQL Database when using **Microsoft Entra with MFA**, you can navigate to **Tools** > **Options** > **Azure Services** > **Azure Cloud**, and change the value for either **Use system default web browser** or **Use Web Account Manager**. For more information, see [Options (Azure Services)](../menu-help/options-azure-services.md).

- If you experience connection problems with SQL database in Fabric, see [Understand network security in Microsoft Fabric](/fabric/security/security-overview#understand-network-security).

### Clear Microsoft Entra ID token cache

[!INCLUDE [refresh-entra-id-cache](../includes/refresh-entra-id-cache.md)]

## Create a table in the new database

In this section, you create a table in your database.

1. In the **Object Explorer**, in the **Databases** list, right-click on your database, and select **New Query**:

   :::image type="content" source="media/ssms-connect-query-sql-database-fabric/object-explorer-new-query.png" alt-text="Screenshot showing how to create a New Query.":::

1. Paste the following T-SQL code snippet into the query window:

   ```sql
   -- Create a new table called 'Customers' in schema 'dbo'
   -- Drop the table if it already exists
   IF OBJECT_ID('dbo.Customers', 'U') IS NOT NULL
       DROP TABLE dbo.Customers;
   GO

   -- Create the table in the specified schema
   CREATE TABLE dbo.Customers
   (
       CustomerId INT NOT NULL PRIMARY KEY, -- primary key column
       Name NVARCHAR (50) NOT NULL,
       Location NVARCHAR (50) NOT NULL,
       Email NVARCHAR (50) NOT NULL
   );
   GO
   ```

1. Execute the query by selecting **Execute** or selecting F5 on your keyboard.

After the query is complete, the new `Customers` table is displayed in the list of tables in **Object Explorer**. If the table isn't displayed, right-click the **TutorialDB** > **Tables** node in **Object Explorer**, and then select **Refresh**.

:::image type="content" source="media/ssms-connect-query-sql-database-fabric/new-table.png" alt-text="Screenshot showing New table.":::

## Insert rows into the new table

Now let's insert some rows into the `Customers` table that you created. Paste the following T-SQL code snippet into the query window, and then select **Execute**:

```sql
-- Insert rows into table 'Customers'
INSERT INTO dbo.Customers (
    [CustomerId],
    [Name],
    [Location],
    [Email]
)
VALUES
    (1, N'Orlando', N'Australia', N''),
    (2, N'Keith', N'India', N'keith0@adventure-works.com'),
    (3, N'Donna', N'Germany', N'donna0@adventure-works.com'),
    (4, N'Janet', N'United States', N'janet1@adventure-works.com');
GO
```

## Query the table and view the results

The results of a query are visible beneath the query text window. To query the `Customers` table and view the rows that were inserted, paste the following T-SQL code snippet into the query window, and then select **Execute**:

```sql
-- Select rows from table 'Customers'
SELECT * FROM dbo.Customers;
```

The query results are displayed under the area where the text was entered.

:::image type="content" source="media/ssms-connect-query-sql-database-fabric/query-results.png" alt-text="Screenshot showing the Results list.":::

You can also modify the way results are presented by selecting one of the following options:

:::image type="content" source="media/ssms-connect-query-sql-database-fabric/results.png" alt-text="Screenshot of three options for displaying query results.":::

- The first button displays the results in **Text View**, as shown in the image in the next section.
- The middle button displays the results in **Grid View**, which is the default option.
- The third button lets you save the results to a file whose extension is `.rpt` by default.

## Verify your connection properties by using the query window table

You can find information about the connection properties under the results of your query. After you run the previously mentioned query in the preceding step, review the connection properties at the bottom of the query window.

- You can determine which server and database you're connected to, and your username.
- You can also view the query duration and the number of rows returned by the previously executed query.

  :::image type="content" source="media/ssms-connect-query-sql-database-fabric/connection-properties.png" alt-text="Screenshot of the connection properties." lightbox="media/ssms-connect-query-sql-database-fabric/connection-properties.png":::

## Clean up resources

Remove the sample table we create in this quickstart. Paste the following T-SQL code and **Execute**:

```sql
DROP TABLE dbo.Customers;
```

## Related content

- [Query Editor (SQL Server Management Studio)](../f1-help/database-engine-query-editor-sql-server-management-studio.md)
- [Script objects in SQL Server Management Studio](../tutorials/scripting-ssms.md)
- [Use templates in SQL Server Management Studio](../template/templates-ssms.md)
- [SQL Server Management Studio components and configuration](../tutorials/ssms-configuration.md)
- [Tips and tricks for using SQL Server Management Studio (SSMS)](../tutorials/ssms-tricks.md)
