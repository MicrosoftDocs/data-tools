---
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: abhishekum
ms.date: 02/09/2026
ms.service: dms
ms.topic: include
---

The Azure SQL migration extension for Azure Data Studio enables you to assess, get right-sized Azure recommendations and migrate your SQL Server databases to Azure.

> [!IMPORTANT]  
> The Azure SQL migration extension in Azure Data Studio [is retired](/lifecycle/definitions#retirement) as of **February 28, 2026** along with Azure Data Studio. For more information, see [Post-retirement alternatives for Azure SQL migration extension](../extensions/azure-sql-migration-extension.md#post-retirement-alternatives-for-azure-sql-migration-extension).

The Azure SQL Migration extension for Azure Data Studio offers these key benefits:

- A responsive UI for an end-to-end migration experience. The extension starts with a migration readiness assessment and SKU recommendation (preview) (based on performance data).

- An enhanced assessment mechanism that can evaluate SQL Server instances. The extension identifies databases that are ready to migrate to Azure SQL targets.

  You can use the [SQL Server migration experience in the Azure Arc portal](/sql/sql-server/azure-arc/migration-assessment) to assess SQL Server databases.

- An SKU recommendation engine that collects performance data from the on-premises source SQL Server instance and then generates right-sized SKU recommendations based on your Azure SQL target.

- A reliable Azure service powered by Azure Database Migration Service that orchestrates data movement activities to deliver a seamless migration experience.

- You can run your migration online (for migrations that require minimal downtime) or offline (for migrations where downtime persists throughout the migration) depending on your business requirements.

- You can configure a self-hosted integration runtime to use your own compute resources to access the source SQL Server instance backup files in your on-premises environment.

- Provides a secure and improved user experience for migrating TDE databases and SQL/Windows logins to Azure SQL.

For information about specific migration scenarios and Azure SQL targets, see the list of tutorials in the following table:

| Migration scenario | Migration mode |
| --- | --- |
| SQL Server to Azure SQL Managed Instance | [Online](/azure/dms/tutorial-sql-server-managed-instance-online-ads) / [Offline](/azure/dms/tutorial-sql-server-managed-instance-offline-ads) |
| SQL Server to SQL Server on Azure Virtual Machines | [Online](/azure/dms/tutorial-sql-server-to-virtual-machine-online-ads) / [Offline](/azure/dms/tutorial-sql-server-to-virtual-machine-offline-ads) |
| SQL Server to Azure SQL Database | [Offline](/azure/dms/tutorial-sql-server-azure-sql-database-offline-ads) |

> [!IMPORTANT]  
> If your target is Azure SQL Database, make sure you deploy the database schema before you begin the migration. You can use [Azure Database Migration Service either from Azure portal](/data-migration/sql-server/database/database-migration-service) or using [PowerShell / AZ cmdlets](/azure/dms/migration-dms-powershell-cli).
