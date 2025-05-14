---
title: "Connect to a SQL Server or Azure SQL Database"
description: "Connect to a SQL Server or Azure SQL Database"
author: rwestMSFT
ms.author: randolphwest
ms.date: "01/28/2019"
ms.service: sql-server-management-studio
ms.topic: conceptual
ms.collection:
  - data-tools
---
# Connect to a SQL Server or Azure SQL Database

[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]
To work with servers and databases, you must first connect to the server. You can connect to multiple servers at the same time.

[SQL Server Management Studio (SSMS)](../sql-server-management-studio-ssms.md) supports several types of connections. This article provides details for connecting to SQL Server and Azure SQL Database (connecting to an Azure SQL single database or elastic pool). For information on the other connection options, see the [Related content](#related-content) at the end of this page.
  
## Connecting to a Server  

1. On **Object Explorer**, click **Connect > Database Engine...**.

   ![connect](../media/connect-to-server/connect-db-engine.png)

1. Fill out the **Connect to Server** form and click **Connect**:

   ![connect to server](../media/connect-to-server/connect.png)

1. If you're connecting to an Azure SQL Server, you might get prompted to sign in to create a firewall rule. Click **Sign In...** (if not, skip to step 6 below)

   ![Screenshot of the New Firewall Rule dialog box with the Sign in option called out.](../media/connect-to-server/firewall-rule-sign-in.png)

1. After successfully signing in, the form is pre-populated with your specific IP address. If your IP address changes often, it might be easier to grant access to a range, so select the option that's best for your environment. 

   ![Screenshot of the New Firewall Rule dialog box with the Add my client IP address option selected and the OK option called out.](../media/connect-to-server/new-firewall-rule.png)

1. To create the firewall rule and connect to the server, click **OK**.

1. The server appears in **Object Explorer** after successfully connecting:

   ![Screenshot of the Object Explorer showing that the server is successfully connected.](../media/connect-to-server/connected.png)

## Related content

- [Design, Create, and Update Tables](../visual-db-tools/design-tables-visual-database-tools.md)
- [What is SQL Server Management Studio (SSMS)?](../sql-server-management-studio-ssms.md)
- [Install SQL Server Management Studio](../install/install.md)
- [Analysis Services](/analysis-services/instances/connect-from-client-applications-analysis-services)
- [Integration Services](/sql/integration-services/sql-server-integration-services)
- [Reporting Services](/sql/reporting-services/tools/connect-to-a-report-server-in-management-studio)
- [Azure Storage](../f1-help/connect-to-microsoft-azure-storage.md)
