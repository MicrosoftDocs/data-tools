---
title: Connect and Query SQL Server on Azure VM Using SSMS
description: Connect to a SQL Server instance on an Azure VM using SSMS. Create and query SQL Server on an Azure VM by running basic T-SQL queries in SSMS.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: mikeray, randolphwest
ms.date: 02/29/2024
ms.service: sql-server-management-studio
ms.topic: quickstart
ms.collection:
  - data-tools
ms.custom:
  - intro-quickstart
---
# Quickstart: Connect and query a SQL Server instance on an Azure Virtual Machine using SQL Server Management Studio (SSMS)

[!INCLUDE [sqlserver](../includes/applies-to-version/sqlserver.md)]

Get started using SQL Server Management Studio (SSMS) to connect to your SQL Server instance on an Azure Virtual Machine and run some Transact-SQL (T-SQL) commands.

[!INCLUDE [entra-id](../includes/entra-id-hard-coded.md)]

> [!div class="checklist"]
> - Connect to a SQL Server instance
> - Create a database
> - Create a table in your new database
> - Insert rows into your new table
> - Query the new table and view the results
> - Use the query window table to verify your connection properties

## Prerequisites

To complete this article, you need SQL Server Management Studio and access to a data source.

- [Install SQL Server Management Studio](../install/install.md)
- [SQL Server on an Azure VM](https://azure.microsoft.com/services/virtual-machines/sql-server/)

## Connect to SQL Virtual Machines

The following steps show how to create an optional DNS label for your Azure VM and then connect with SQL Server Management Studio.

### Configure a DNS Label for the public IP address

To connect to the SQL Server Database Engine from the Internet, consider creating a DNS Label for your public IP address. You can join by IP address, but the DNS Label creates an A record that is easier to identify and abstracts the underlying public IP address.

> [!NOTE]  
> DNS Labels aren't required if you plan to only connect to the SQL Server instance within the same Virtual Network or only locally.

1. Create a DNS Label by selecting **Virtual machines** in the portal. Select your SQL Server VM to bring up its properties.

1. In the virtual machine overview, select your **Public IP address**.

   :::image type="content" source="media/ssms-connect-query-sql-server-azure-vm/azure-sql-vm-ip-address-.png" alt-text="Screenshot of the public IP address." lightbox="media/ssms-connect-query-sql-server-azure-vm/azure-sql-vm-ip-address-.png":::

1. In the properties for your Public IP address, expand **Configuration**.

1. Enter a DNS Label name. This name is an A record that can be used to directly connect to your SQL Server VM by name instead of by IP address.

1. Select the **Save** button.

   :::image type="content" source="media/ssms-connect-query-sql-server-azure-vm/azure-sql-vm-dns-label.png" alt-text="Screenshot of the DNS label.":::

### Connect

1. Start SQL Server Management Studio. The first time you run SSMS, the **Connect to Server** window opens. If it doesn't open, you can open it manually by selecting **Object Explorer** > **Connect** > **Database Engine**.

   :::image type="content" source="media/ssms-connect-query-sql-server-azure-vm/connect-object-explorer.png" alt-text="Screenshot of the connect link in Object Explorer.":::

1. The **Connect to Server** dialog box appears. Enter the following information:

   | Setting | Suggested values | Description |
   | --- | --- | --- |
   | **Server type** | Database engine | For **Server type**, select **Database Engine** (usually the default option). |
   | **Server name** | The fully qualified server name | For **Server name**, enter the name of your SQL Server VM. You can also use the SQL Server VM IP address to connect. |
   | **Authentication** | Microsoft Entra - Managed Identity | Use **managed identity authentication** to connect to SQL Server VM. Using managed identity authentication eliminates the need for developer-managed credentials. Use SQL Server Authentication only when necessary.<br /><br />**Windows Authentication** isn't supported for SQL Server VM. For more information, see [Azure SQL authentication](/azure/sql-database/sql-database-security-overview#access-management). |
   | **Login** | Server account user ID | The user ID from the server account used to create the server. A sign in is required when using **SQL Server Authentication**. |
   | **Password** | Server account password | The password from the server account used to create the server. A password is required when using **SQL Server Authentication**. |
   | **Encryption** <sup>1</sup> | Encryption method | Select the encryption level for the connection. The default value is *Mandatory*. |
   | **Trust server certificate** | Trust Server Certificate | Check this option to bypass server certificate validation. The default value is *False* (unchecked), which promotes better security using trusted certificates. |
   | **Host Name in Certificate** | Host name of the server | The value provided in this option is used to specify a different, but expected, CN or SAN in the server certificate. |

   <sup>1</sup> [!INCLUDE [ssms-encryption](../includes/ssms-encryption.md)]

   :::image type="content" source="media/ssms-connect-query-sql-server-azure-vm/connect-to-azure-sql-vm-object-explorer-ssms20.png" alt-text="Screenshot of connection dialog for SQL virtual machines.":::

1. After you complete all the fields, select **Connect**.

   You can also modify additional connection options by selecting **Options**. Examples of connection options are the database you're connecting to, the connection timeout value, and the network protocol. This article uses the default values for all the options.

1. To verify that your SQL Server on Azure VM succeeded, expand and explore the objects within **Object Explorer** where the server name, the SQL Server version, and the username are displayed. These objects are different depending on the server type.

   :::image type="content" source="media/ssms-connect-query-sql-server-azure-vm/connect-azure-sql-vm.png" alt-text="Screenshot of the Azure SQL VM connection.":::

## Troubleshoot connectivity issues

Although the portal provides options to configure connectivity automatically, knowing how to manually configure connectivity is useful. Understanding the requirements can also aid troubleshooting.

The following table lists the requirements to connect to SQL Server on Azure VM.

| Requirement | Description |
| --- | --- |
| [Enable SQL Server authentication mode](/sql/database-engine/configure-windows/change-server-authentication-mode#use-ssms) | SQL Server authentication is needed to connect to the VM remotely unless you configured Active Directory on a virtual network. |
| [Create a Login](/sql/relational-databases/security/authentication-access/create-a-login) | If you're using SQL authentication, you need a SQL login with a user name and password that also has permissions to your target database. |
| Enable TCP/IP protocol | SQL Server must allow connections over TCP. |
| [Configure a Windows Firewall for Database Engine Access](/sql/database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access) | The firewall on the VM must allow inbound traffic on the SQL Server port (default 1433). |
| [Create a network security group rule for TCP 1433](/azure/virtual-network/manage-network-security-group#create-a-security-rule) | Allow the VM to receive traffic on the SQL Server port (default 1433) if you want to connect over the internet. This isn't required for local and virtual-network-only connections. This step is only required in the Azure portal. |

> [!TIP]  
> The steps in the preceding table are done for you when you configure connectivity in the portal. Use these steps only to confirm your configuration or to set up connectivity manually for SQL Server.

## Create a database

Create a database named `TutorialDB` by following the below steps:

1. Right-click your server instance in Object Explorer, and then select **New Query**:

   :::image type="content" source="media/ssms-connect-query-sql-server-azure-vm/new-query.png" alt-text="Screenshot of the new query link.":::

1. Paste the following T-SQL code snippet into the query window:

   ```sql
   IF NOT EXISTS (
       SELECT name
       FROM sys.databases
       WHERE name = N'TutorialDB'
   )
   CREATE DATABASE [TutorialDB];
   GO

   ALTER DATABASE [TutorialDB] SET QUERY_STORE = ON;
   GO
   ```

1. Execute the query by selecting **Execute** or selecting F5 on your keyboard.

   :::image type="content" source="media/ssms-connect-query-sql-server-azure-vm/execute.png" alt-text="Screenshot of the Execute command.":::
  
   After the query is complete, the new `TutorialDB`  database appears in the list of databases in Object Explorer. If it isn't displayed, right-click the **Databases** node, and then select **Refresh**.

## Create a table in the new database

In this section, you create a table in the newly created `TutorialDB` database. Because the query editor is still in the context of the `master` database, switch the connection context to the `TutorialDB` database by doing the following steps:

1. In the database dropdown list, select the database that you want, as shown here:

   :::image type="content" source="media/ssms-connect-query-sql-server-azure-vm/change-db.png" alt-text="Screenshot of change database.":::

1. Paste the following T-SQL code snippet into the query window:

   ```sql
   USE [TutorialDB]
   GO

   -- Create a new table called 'Customers' in schema 'dbo'
   -- Drop the table if it already exists
   IF OBJECT_ID('dbo.Customers', 'U') IS NOT NULL
       DROP TABLE dbo.Customers
   GO

   -- Create the table in the specified schema
   CREATE TABLE dbo.Customers (
       CustomerId INT NOT NULL PRIMARY KEY, -- primary key column
       Name NVARCHAR(50) NOT NULL,
       Location NVARCHAR(50) NOT NULL,
       Email NVARCHAR(50) NOT NULL
   );
   GO
   ```

1. Execute the query by selecting **Execute** or selecting F5 on your keyboard.

After the query is complete, the new Customers table is displayed in the list of tables in Object Explorer. If the table isn't displayed, right-click the **TutorialDB** > **Tables** node in Object Explorer, then select **Refresh**.

:::image type="content" source="media/ssms-connect-query-sql-server-azure-vm/new-table.png" alt-text="Screenshot of new table.":::

## Insert rows into the new table

Now let's insert some rows into the Customers table that you created. Paste the following T-SQL code snippet into the query window, and then select **Execute**:

```sql
-- Insert rows into table 'Customers'
INSERT INTO dbo.Customers (
    CustomerId,
    Name,
    Location,
    Email
)
VALUES
    (1, N'Orlando', N'Australia', N''),
    (2, N'Keith', N'India', N'keith0@adventure-works.com'),
    (3, N'Donna', N'Germany', N'donna0@adventure-works.com'),
    (4, N'Janet', N'United States', N'janet1@adventure-works.com')
GO
```

## Query the table and view the results

The results of a query are visible beneath the query text window. To query the `Customers` table and view the rows that were inserted, paste the following T-SQL code snippet into the query window, and then select **Execute**:

```sql
-- Select rows from table 'Customers'
SELECT * FROM dbo.Customers;
```

The query results are displayed under the area where the text was entered.

:::image type="content" source="media/ssms-connect-query-sql-server-azure-vm/query-results.png" alt-text="Screenshot of the results list.":::

You can also modify the way results are presented by selecting one of the following options:

:::image type="content" source="media/ssms-connect-query-sql-server-azure-vm/results.png" alt-text="Screenshot of three options for displaying query results.":::

- The first button displays the results in **Text View**, as shown in the image in the next section.
- The middle button displays the results in **Grid View**, which is the default option.
- The third button lets you save the results to a file whose extension is `.rpt` by default.

## Verify your connection properties by using the query window table

You can find information about the connection properties under the results of your query. After you run the previously mentioned query in the preceding step, review the connection properties at the bottom of the query window.

- You can determine which server and database you're connected to, and your username.
- You can also view the query duration and the number of rows the previously executed query returns.

  :::image type="content" source="media/ssms-connect-query-sql-server-azure-vm/connection-properties.png" alt-text="Screenshot of connection properties." lightbox="media/ssms-connect-query-sql-server-azure-vm/connection-properties.png":::

## Additional tools

You can also use [Azure Data Studio](/azure-data-studio/download-azure-data-studio) to connect and query [SQL Server](/azure-data-studio/quickstart-sql-server), an [Azure SQL Database](/azure-data-studio/quickstart-sql-database), and [Azure Synapse Analytics](/azure-data-studio/quickstart-sql-dw).

## Related content

- [SQL Server Management Studio (SSMS) Query Editor](../f1-help/database-engine-query-editor-sql-server-management-studio.md)
- [Script objects in SQL Server Management Studio](../tutorials/scripting-ssms.md)
- [Use templates in SQL Server Management Studio](../template/templates-ssms.md)
- [SQL Server Management Studio components and configuration](../tutorials/ssms-configuration.md)
- [Tips and tricks for using SQL Server Management Studio (SSMS)](../tutorials/ssms-tricks.md)
