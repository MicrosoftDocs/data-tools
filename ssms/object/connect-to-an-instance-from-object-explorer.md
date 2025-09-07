---
title: "Connect to a SQL Server or Azure SQL Database"
description: "Connect to a SQL Server or Azure SQL Database"
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/07/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---
# Connect to a SQL Server or Azure SQL Database

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

To work with servers and databases, you must first connect to the server. You can connect to multiple servers at the same time.

[SQL Server Management Studio (SSMS)](../sql-server-management-studio-ssms.md) supports several types of connections. This article provides details for connecting to SQL Server and Azure SQL Database (connecting to an Azure SQL single database or elastic pool). For information on the other connection options, see the [Related content](#related-content) at the end of this page.

## Connect to a server

1. On **Object Explorer**, select **Connect > Database Engine...**.

   :::image type="content" source="../media/connect-to-server/connect-db-engine.png" alt-text="Screenshot of Connect to Database Engine dialog.":::

1. Fill out the **Connect to Server** form and select **Connect**.

   :::image type="content" source="../media/connect-to-server/connect.png" alt-text="Screenshot of Connect dialog.":::

1. If you're connecting to an Azure SQL Server, you might get prompted to sign in to create a firewall rule. Select **Sign In...** (if not, skip to step 6).

   :::image type="content" source="../media/connect-to-server/firewall-rule-sign-in.png" alt-text="Screenshot of the New Firewall Rule dialog box with the Sign in option called out.":::

1. After you successfully sign in, the form is prepopulated with your specific IP address. If your IP address changes often, it might be easier to grant access to a range, so select the option that's best for your environment.

   :::image type="content" source="../media/connect-to-server/new-firewall-rule.png" alt-text="Screenshot of the New Firewall Rule dialog box with the Add my client IP address option selected and the OK option called out.":::

1. To create the firewall rule and connect to the server, select **OK**.

1. The server appears in **Object Explorer** after successfully connecting.

   :::image type="content" source="../media/connect-to-server/connected.png" alt-text="Screenshot of the Object Explorer showing that the server is successfully connected.":::

## Related content

- [Create and update database tables (Visual Database Tools)](../visual-db-tools/design-tables-visual-database-tools.md)
- [What is SQL Server Management Studio (SSMS)?](../sql-server-management-studio-ssms.md)
- [Install SQL Server Management Studio](../install/install.md)
- [Analysis Services](/analysis-services/instances/connect-from-client-applications-analysis-services)
- [Integration Services](/sql/integration-services/sql-server-integration-services)
- [Connect to a report server in Management Studio](/sql/reporting-services/tools/connect-to-a-report-server-in-management-studio)
- [Connect to Microsoft Azure Storage](../f1-help/connect-to-microsoft-azure-storage.md)
