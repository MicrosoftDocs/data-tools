---
title: Connect and Query Azure SQL Database
description: Connect to and query an Azure SQL Database using SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: mikeray, randolphwest, maghan
ms.date: 09/12/2025
ms.service: sql-server-management-studio
ms.topic: quickstart
ms.collection:
  - data-tools
ms.custom:
  - intro-quickstart
# CustomerIntent: As a user, I want to connect to and query an Azure SQL Database using SSMS, so that I can perform database operations.
---
# Quickstart: Connect and query an Azure SQL Database using SQL Server Management Studio (SSMS)

[!INCLUDE [asdb](../includes/applies-to-version/asdb.md)]

Get started using SQL Server Management Studio (SSMS) to connect to your Azure SQL Database and run some Transact-SQL (T-SQL) commands.

[!INCLUDE [entra-id](../includes/entra-id-hard-coded.md)]

The article demonstrates the following steps:

> [!div class="checklist"]
>
> - Connect to an Azure SQL Database logical server
> - Create a database
> - Create a table in your new database
> - Insert rows into your new table
> - Query the new table and view the results
> - Use the query window table to verify your connection properties
> - Remove database

## Prerequisites

- [Install SQL Server Management Studio](../install/install.md)
- [Azure SQL Database](/azure/azure-sql/database/free-offer?view=azuresql-db&preserve-view=true) logical server

## Connect to an Azure SQL Database

> [!NOTE]  
> Releases of SSMS prior to 18.6 don't authenticate to Database Engines through Microsoft Entra multifactor authentication (MFA). To continue using MFA, you need [SSMS 18.6](../install/install.md) or a later version.

1. Start SQL Server Management Studio (SSMS). The first time you run SSMS, the **Connect to Server** window opens. If it doesn't open, you can open it manually by selecting **Object Explorer** > **Connect** > **Database Engine**.

   :::image type="content" source="media/ssms-connect-query-azure-sql-database/connect-object-explorer.png" alt-text="Screenshot of the Connect link in Object Explorer.":::

1. The **Connect to Server** dialog box appears. Enter the following information:

   | Setting | Suggested value | Details |
   | --- | --- | --- |
   | **Server type** | Database Engine | Select **Database Engine** (usually the default option). |
   | **Server name** | The fully qualified server name | Enter the name of your *Azure SQL Database* [logical server name](/azure/azure-sql/database/logical-servers?view=azuresql-db&preserve-view=true). |
   | **Authentication** | | |
   | | [Microsoft Entra ID](/azure/azure-sql/database/authentication-microsoft-entra-connect-to-azure-sql?view=azuresql-db&preserve-view=true) <sup>1</sup> | |
   | | - Password<br />- Integrated<br />- MFA | We recommend Microsoft Entra authentication with multifactor authentication (MFA). See [Using Microsoft Entra multifactor authentication](/azure/azure-sql/database/authentication-mfa-ssms-overview). |
   | | - Service Principal | See [Microsoft Entra service principals with Azure SQL](/azure/azure-sql/database/authentication-aad-service-principal). |
   | | - Managed Identity | See [Managed identities in Microsoft Entra for Azure SQL](/azure/azure-sql/database/authentication-azure-ad-user-assigned-managed-identity).<br /><br />Connecting with SSMS using a managed identity requires an Azure VM. See [Use a Windows VM system-assigned managed identity to access Azure SQL](/azure/active-directory/managed-identities-azure-resources/tutorial-windows-vm-access-sql) |
   | | - Default | The default option can be used when connecting using any Microsoft Entra authentication mode that's passwordless and noninteractive. |
   | | SQL Server Authentication | Use **SQL Server Authentication** for Azure SQL to connect. |
   | **Login** | Server account user ID | The user ID from the server account used to create the server. |
   | **Password** | Server account password | The password from the server account used to create the server. |
   | **Database Name** | Provide the database name of your Azure SQL Database. |
   | **Encryption** <sup>2</sup> | Encryption method | Select the encryption level for the connection. The default value is *Mandatory*. |
   | **Trust server certificate** | Trust Server Certificate | Check this option to bypass server certificate validation. The default value is *False* (unchecked), which promotes better security using trusted certificates. |
   | **Host Name in Certificate** | Host name of the server | The value provided in this option is used to specify a different, but expected, CN or SAN in the server certificate. |

   <sup>1</sup> The Windows Authentication method isn't supported for Azure SQL. For more information, see [Azure SQL authentication](/azure/sql-database/sql-database-security-overview#access-management). We recommend Microsoft Entra authentication with multifactor authentication (MFA).

   <sup>2</sup> [!INCLUDE [ssms-encryption](../includes/ssms-encryption.md)]

   You can also modify additional connection options by selecting **Options**. Examples of connection options are the database you're connecting to, the connection timeout value, and the network protocol. This article uses the default values for all the options.

   :::image type="content" source="media/ssms-connect-query-azure-sql-database/connect-to-azure-sql-object-explorer-ssms20.png" alt-text="Screenshot of connection dialog for Azure SQL." lightbox="media/ssms-connect-query-azure-sql-database/connect-to-azure-sql-object-explorer-ssms20.png":::

1. After you complete all the fields, select **Connect**.

   If your firewall isn't set up, a prompt appears to configure the firewall. Once you sign in, fill in your Azure account sign in information and continue to set the firewall rule. Then select **OK**. This prompt is a one time action. Once you configure the firewall, the firewall prompt shouldn't appear.

   :::image type="content" source="media/ssms-connect-query-azure-sql-database/azure-sql-firewall-sign-in.png" alt-text="Screenshot of the Create new firewall rule dialog in SSMS.":::

1. To verify that your Azure SQL Database connection succeeded, expand and explore the objects within **Object Explorer** where the server name, the SQL Server version, and the username are displayed. These objects are different depending on the server type.

   :::image type="content" source="media/ssms-connect-query-azure-sql-database/connect-azure-sql.png" alt-text="Screenshot of a connection to Azure SQL Database in the Object Explorer.":::

## Troubleshoot connectivity issues

- If your browser fails to connect to SQL Database when using **Microsoft Entra with MFA**, you can navigate to **Tools** > **Options** > **Azure Services** > **Azure Cloud**, and change the value for either **Use system default web browser** or **Use Web Account Manager**. For more information, see [Options (Azure Services)](../menu-help/options-azure-services.md).

- You can experience connection problems with Azure SQL Database. For more information on troubleshooting connection problems, visit [Troubleshoot connectivity issues and other errors](/azure/azure-sql/database/troubleshoot-common-errors-issues).

- You can prevent, troubleshoot, diagnose, and mitigate connection and transient errors that you encounter when interacting with Azure SQL Database. For more information, visit [Troubleshoot transient connection errors](/azure/azure-sql/database/troubleshoot-common-connectivity-issues).

## Create a database

Now let's create a database named `TutorialDB` by following these steps:

1. Right-click your server instance in **Object Explorer**, and then select **New Query**:

   :::image type="content" source="media/ssms-connect-query-azure-sql-database/new-query.png" alt-text="Screenshot showing the New Query link.":::

1. Paste the following T-SQL code snippet into the query window create a new database with default settings:

   ```sql
   IF NOT EXISTS (SELECT name
                  FROM sys.databases
                  WHERE name = N'TutorialDB')
       CREATE DATABASE [TutorialDB];
   GO
   ```

1. Execute the query by selecting **Execute** or selecting F5 on your keyboard.

   After the query is complete, the new `TutorialDB` database appears in the list of databases in **Object Explorer**. If it isn't displayed, right-click the **Databases** node, and then select **Refresh**.

## Create a table in the new database

In this section, you create a table in the newly created `TutorialDB` database. Because the query editor is still in the context of the `master` database, switch the connection context to the `TutorialDB` database by doing the following steps:

1. In the database dropdown list, select the database that you want, as shown here:

   :::image type="content" source="media/ssms-connect-query-azure-sql-database/change-db.png" alt-text="Screenshot showing how to Change the database context.":::

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

:::image type="content" source="media/ssms-connect-query-azure-sql-database/new-table.png" alt-text="Screenshot showing New table.":::

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

:::image type="content" source="media/ssms-connect-query-azure-sql-database/query-results.png" alt-text="Screenshot showing the Results list.":::

You can also modify the way results are presented by selecting one of the following options:

:::image type="content" source="media/ssms-connect-query-azure-sql-database/results.png" alt-text="Screenshot of three options for displaying query results.":::

- The first button displays the results in **Text View**, as shown in the image in the next section.
- The middle button displays the results in **Grid View**, which is the default option.
- The third button lets you save the results to a file whose extension is `.rpt` by default.

## Verify your connection properties by using the query window table

You can find information about the connection properties under the results of your query. After you run the previously mentioned query in the preceding step, review the connection properties at the bottom of the query window.

- You can determine which server and database you're connected to, and your username.
- You can also view the query duration and the number of rows returned by the previously executed query.

  :::image type="content" source="media/ssms-connect-query-azure-sql-database/connection-properties.png" alt-text="Screenshot of the connection properties." lightbox="media/ssms-connect-query-azure-sql-database/connection-properties.png":::

## Clean up resources

The `TutorialDB` database you created in this quickstart **isn't** a free offer database. Let's remove it. Paste the following T-SQL code and **Execute**:

```sql
IF EXISTS (SELECT name
           FROM sys.databases
           WHERE name = N'TutorialDB')
    DROP DATABASE [TutorialDB];
GO
```

## Related content

- [Query Editor (SQL Server Management Studio)](../f1-help/database-engine-query-editor-sql-server-management-studio.md)
- [Script objects in SQL Server Management Studio](../tutorials/scripting-ssms.md)
- [Use templates in SQL Server Management Studio](../template/templates-ssms.md)
- [SQL Server Management Studio components and configuration](../tutorials/ssms-configuration.md)
- [Tips and tricks for using SQL Server Management Studio (SSMS)](../tutorials/ssms-tricks.md)
