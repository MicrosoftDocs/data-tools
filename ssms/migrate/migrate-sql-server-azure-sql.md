---
title: Migrate SQL Server to Azure SQL
description: Learn how to assess, plan, and migrate SQL Server databases to Azure using SQL Server Management Studio (SSMS) and Azure migration tools.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: niball
ms.date: 04/14/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
  - sql-migration-content
keywords:
  - SQL Server
  - Azure SQL
  - SSMS
  - SQL Server Management Studio
  - extensions
  - components
---

# Migrate SQL Server to Azure SQL using the migration component in SSMS

The Migrate SQL Server feature in SQL Server Management Studio (SSMS) assesses SQL Server instances and migrates them to Azure SQL.

| Azure&nbsp;Arc enabled | Details |
| --- | --- |
| **Yes** | SSMS uses readiness assessments already collected through Azure Arc. These assessments include compatibility findings, target sizing, and recommended migration paths. |
| **No** | SSMS runs a local, metadata-based readiness assessment and recommends an Azure SQL target (Azure SQL Managed Instance or SQL Server on Azure Virtual Machines). From the assessment results, you can start a migration using<br /><br />- The link feature for Azure SQL Managed Instance (near-zero downtime)<br />- Native backup and restore (lift-and-shift)<br />- Azure Database Migration Service (Azure DMS) |

You can also provision Azure SQL targets and monitor migrations from SSMS or the Azure portal.

## Prerequisites

- SQL Server Management Studio 22 and later versions.
- A SQL Server instance login with **sysadmin** permissions.

## Installation and configuration

1. Install the latest version of [SQL Server Management Studio](../install/install.md) (SSMS). Once the installation is complete, select **Modify** > **Individual Components**. SSMS is installed using Visual Studio Installer.

1. Select the **Migration** component, choose **Install while downloading** from the dropdown list, and select **Modify** to complete the installation.

## Migration process

## [SQL Server migration](#tab/sql-standard)

This workflow is suitable for SQL Server instances not enabled by Azure Arc.

:::image type="content" source="media/migrate-sql-server-azure-sql/not-arc-enabled.png" alt-text="Screenshot of Migration tab showing migration options for standalone SQL Server instances.":::

## [SQL Server migration enabled by Azure Arc](#tab/sql-arc)

This workflow is available for SQL Server instances enabled by Azure Arc. It provides precomputed assessments and streamlined monitoring.

:::image type="content" source="media/migrate-sql-server-azure-sql/arc-enabled.png" alt-text="Screenshot of Migration tab showing migration options for SQL Server instances enabled by Azure Arc.":::

---

### Connect to SQL Server

## [SQL Server migration](#tab/sql-standard)

1. Open SSMS.
1. Connect to your source SQL Server instance.
1. Right-click on your SQL Server instance in Object Explorer, and select **Migrate SQL Server**.

This action opens the **Migration** landing page and opens other SSMS wizards for migrating data .

## [SQL Server migration enabled by Azure Arc](#tab/sql-arc)

1. Open SSMS.
1. Connect to your source SQL Server instance.
1. Right-click on your SQL Server instance in Object Explorer, and select **Migrate SQL Server**.

---

### Assess readiness for migration

## [SQL Server migration](#tab/sql-standard)

The migration landing page opens to the **Database Assessment** phase.

**Azure Migration Readiness** evaluates your database for compatibility with Azure SQL targets. The migration readiness check identifies any migration blockers for Azure SQL Managed Instance, Azure SQL Database, or SQL Server on Azure Virtual Machines (Azure VM) targets.

**To run an assessment**:

1. Select **Run Assessment** from the **Migration** landing page.
1. The tool generates an HTML report with detailed findings.
1. Review the **target recommendations**, which are determined by:
   - Migration path with the least blocking issues
   - Migration activities requiring minimal manual intervention

> [!TIP]  
> For performance-based sizing recommendations with detailed metrics, consider using the [migration readiness assessment](/sql/sql-server/azure-arc/migration-assessment) method described in [SQL Server migration enabled by Azure Arc](?tabs=sql-arc#assess-readiness-for-migration).

The assessment results provide insights into both instance readiness and database readiness. The readiness categories are described in the following table:

| Category | Description |
| --- | --- |
| **Ready** | Databases can be migrated to the target without requiring any changes. |
| **Ready with warnings** | Some non-blocking issues are present. Migration can proceed without breaking changes to the database or application. |
| **Not ready** | Migration-blocking issues exist. These issues require remediation before migrating to the target environment. The report includes a list of identified issues that must be fixed before migration. |

## [SQL Server migration enabled by Azure Arc](#tab/sql-arc)

Select **View Readiness Assessment** to see [precomputed assessment data collected by Azure Arc](/sql/sql-server/azure-arc/migration-assessment). You don't need to run manual assessment scans.

Review the assessment results:

- **Assessment findings**: Compatibility issues and migration readiness.
- **Target sizing recommendations**: Right-sizing based on [actual performance metrics](/sql/sql-server/azure-arc/migration-assessment).
- **Migration path recommendations**: Optimal target selection.

---

### Select target

## [SQL Server migration](#tab/sql-standard)

When the assessment finishes, set up your migration target:

1. Select **Provision Target** to access the **Azure SQL Hub**.

1. From the [Azure SQL Hub](https://aka.ms/azuresqlhub), you can create any SQL target type from a single pane:

   - Azure SQL Database
   - Azure SQL Managed Instance
   - SQL Server on Azure VM

## [SQL Server migration enabled by Azure Arc](#tab/sql-arc)

Choose your [destination platform](/sql/sql-server/azure-arc/migrate-to-azure-sql-managed-instance?tabs=mi-link#select-target):

- **Azure SQL Managed Instance**: For maximum compatibility.
- **SQL Server on Azure VM**: For lift-and-shift scenarios.

Configure the target environment based on the recommendations provided.

---

### Migrate data

From the **Migration** landing page, choose **Migrate data**. You can then choose the appropriate migration method based on your target and requirements.

## [SQL Server migration](#tab/sql-standard)

#### SQL Managed Instance (SQL Managed Instance link)

- Use [SQL Managed Instance link](/azure/azure-sql/managed-instance/managed-instance-link-configure-how-to-ssms) to set up a SQL Managed Instance link.
- Enables near-real-time data replication with minimal downtime.

#### Backup and restore

- Use the SSMS backup and restore functionality for [SQL Server migration](upgrade-sql-server.md#prepare-for-upgrade).
- Suitable for smaller databases or when downtime is acceptable.

#### Azure Database Migration Service (Azure DMS)

- Redirects to [Azure DMS](/azure/dms/) for enterprise-grade migrations.
- Supports all target types (SQL Database, SQL Managed Instance, and Azure VM).
- Provides both **offline** and **online** migration options.
- Recommended for large-scale or complex migrations.

## [SQL Server migration enabled by Azure Arc](#tab/sql-arc)

In the Azure portal, navigate to your SQL Server instance, and open the **Database migration** pane, to choose the migration method that best fits your needs.

#### SQL Managed Instance

After an initial configuration to prepare your environment, the migration process automates the rest based on your selection. For more information, see [Integrated migration methods](/sql/sql-server/azure-arc/migrate-to-azure-sql-managed-instance?tabs=mi-link#integrated-migration-methods) and [Migrate data](/sql/sql-server/azure-arc/migrate-to-azure-sql-managed-instance?tabs=mi-link#migrate-data).

- **SQL Managed Instance link**: Continuous data replication with online migration.
- **Log shipping**: Traditional log shipping method.

#### SQL Server on Azure Virtual Machines

Use backup and restore or Azure DMS to migrate to SQL Server on Azure VM.

---

### Monitor migration

## [SQL Server migration](#tab/sql-standard)

Track your migration progress and perform cutover:

1. **For Azure DMS migrations**: Use the [Azure DMS](/azure/dms/) monitoring dashboard.
1. **For Managed Instance link migrations**: Monitor through the [SQL Managed Instance link](/azure/azure-sql/managed-instance/managed-instance-link-failover-how-to) feature.

## [SQL Server migration enabled by Azure Arc](#tab/sql-arc)

The **Monitor and Cutover** page in Azure DMS and Azure Arc-enabled SQL Server migrations provides a centralized experience to:

- Track migration progress
- Validate replication status
- Identify migration errors
- Perform final production cutover

For more information, see [Monitor and cutover](/sql/sql-server/azure-arc/migrate-to-azure-sql-managed-instance?tabs=mi-link#monitor-and-cutover).

---

## SQL Server upgrade

In addition to Azure migration, SSMS provides [database compatibility upgrade capabilities](upgrade-sql-server.md#upgrade-assessment). The upgrade assessment identifies compatibility issues related to breaking changes, behavior changes, and deprecated features. The report also provides a feature parity check for cross-platform database migration.

### Upgrade assessment

1. Select **Upgrade Assessment** from the **Migrate to higher version of SQL Server** section.
1. The tool evaluates compatibility level upgrade readiness.
1. Review breaking changes and deprecated features in the report.

### Database upgrade

1. Go to **Upgrade SQL Server** from the **Migrate to higher version of SQL Server** section.
1. Follow the **Upgrade Database** steps.
1. Perform compatibility level upgrade with minimal disruption.

## Best practices

- Always run assessments before planning migration to identify potential issues early.
- Use Arc-enabled assessment when available for more accurate performance-based sizing.
- Choose online migration (Managed Instance link or Azure DMS online) for production databases requiring minimal downtime.
- Test thoroughly in nonproduction environments before production migration.
- Monitor performance during and after migration to ensure optimal configuration.
- Plan cutover windows during low-traffic periods to minimize effect on end users.

## Migration options comparison

| Migration method | Target types | Downtime | Best for |
| --- | --- | --- | --- |
| SSMS Managed Instance link | SQL Managed Instance | Minimal (online) | Production databases, continuous sync |
| Backup and restore | All | Moderate to high | Scheduled downtime |
| Log shipping | SQL Managed Instance | Low to moderate | Large databases, traditional approach |
| Azure DMS | All | Minimal to none | Enterprise migrations, multiple databases |

## Known issues

The following common issues might occur during migration. Use the recommended resolutions to address them.

### Assessment fails

- Verify connectivity to source database.
- Check user permissions for system catalog access.
- Ensure SSMS is up to date.

### Migration performance is slow

- Check network bandwidth between source and Azure.
- Review target tier sizing recommendations.
- Consider using Azure ExpressRoute for large data transfers.

### Cutover validation fails

- Verify data integrity checks.
- Review application compatibility with target platform.
- Check for blocking issues in assessment report.

## Related content

- [What is Azure SQL Managed Instance?](/azure/azure-sql/managed-instance/sql-managed-instance-paas-overview)
- [Azure Database Migration Service](/azure/dms/)
- [SQL Server on Azure Virtual Machines](/azure/azure-sql/virtual-machines/)
- [Azure Arc-enabled SQL Server](/sql/sql-server/azure-arc/overview)
