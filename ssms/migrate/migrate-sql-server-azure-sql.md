---
title: Migrate SQL Server to Azure SQL
description: Learn how to assess, compare, size, plan, and migrate SQL Server databases to Azure using SQL Server Management Studio (SSMS) and Azure migration tools.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: niball
ms.date: 09/18/2026
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
  - migration assessment
  - target sizing
  - pricing recommendation
  - extensions
  - components
---

# Migrate SQL Server to Azure SQL using the migration component in SSMS

The **Migrate SQL Server** feature in SQL Server Management Studio (SSMS) helps you assess SQL Server instances, compare Azure SQL migration targets, review migration readiness, get target sizing and pricing recommendations, and start a migration to Azure.

| Azure&nbsp;Arc enabled | Details |
| --- | --- |
| **Yes** | SSMS uses readiness assessments collected from Azure Arc. These assessments include compatibility findings, target sizing, pricing estimates when available, and recommended migration paths. |
| **No** | SSMS runs an assessment and compares supported Azure SQL targets. The report can include migration readiness, compatibility findings, sizing recommendations, pricing estimates, and recommended migration paths. From the results, you can start a migration by using SQL Managed Instance link, native backup and restore, or Azure Database Migration Service (Azure DMS). |

You can also provision Azure SQL targets and monitor migrations from SSMS or the Azure portal.

## Prerequisites

- SQL Server Management Studio 22 or a later version.
- A SQL Server instance login with **sysadmin** permissions to perform a migration.

For assessment-only permissions, see [Permissions](#permissions).

## Installation and configuration

1. Install the latest version of [SQL Server Management Studio](../install/install.md) (SSMS) by using Visual Studio Installer.
1. In Visual Studio Installer, select **Modify** for your SSMS installation.
1. Select the **Hybrid and Migration** workload.
1. Select **Install while downloading**, and then select **Modify** to complete the installation.

## Migration process

The workflow depends on whether your SQL Server instance is enabled by Azure Arc.

## [SQL Server migration](#tab/sql-standard)

This workflow is suitable for SQL Server instances not enabled by Azure Arc.

:::image type="content" source="media/migrate-sql-server-azure-sql/not-arc-enabled.png" alt-text="Screenshot of Migration tab showing migration options for standalone SQL Server instances.":::

## [SQL Server migration enabled by Azure Arc](#tab/sql-arc)

This workflow is available for SQL Server instances enabled by Azure Arc. It provides precomputed assessments and streamlined monitoring.

:::image type="content" source="media/migrate-sql-server-azure-sql/arc-enabled.png" alt-text="Screenshot of Migration tab showing migration options for SQL Server instances enabled by Azure Arc.":::

---

### Connect to SQL Server

Start the migration workflow from SSMS.

## [SQL Server migration](#tab/sql-standard)

1. Open SSMS.
1. Connect to your source SQL Server instance.
1. Right-click your SQL Server instance in Object Explorer, and select **Migrate SQL Server**.

This action opens the **Migration** landing page, where you can assess the source environment, compare targets, and open the appropriate migration experience.

## [SQL Server migration enabled by Azure Arc](#tab/sql-arc)

1. Open SSMS.
1. Connect to your source SQL Server instance.
1. Right-click your SQL Server instance in Object Explorer, and select **Migrate SQL Server**.

This action opens the **Migration** landing page, where you can assess the source environment, compare targets, and open the appropriate migration experience.

---

### Assess readiness for migration

Assess migration compatibility and generate target recommendations.

## [SQL Server migration](#tab/sql-standard)

The migration landing page opens to the **Database Assessment** phase.

**Azure Migration Readiness** assesses your SQL Server environment and helps you select an appropriate Azure SQL target. The assessment evaluates migration compatibility and can provide target, sizing, and pricing recommendations.

To run an assessment:

1. Select **Run Assessment** from the **Migration** landing page.

1. When the assessment completes, open the generated HTML report.

1. Review the available migration targets and recommendations for:

   - Migration readiness
   - Compatibility findings
   - Recommended Azure SQL target
   - Minimum target configuration
   - Compute and storage sizing
   - Estimated monthly cost
   - Available pricing options

The report can compare these targets:

- Azure SQL Database
- Azure SQL Managed Instance
- SQL Server on Azure Virtual Machines

#### Migration readiness categories

The assessment uses the following user-facing migration readiness categories:

| Category | Description |
| --- | --- |
| **Ready** | The database can be migrated to the target with no conditions to review. |
| **Ready with conditions** | The database has conditions to review before migration, including issues, warnings, affected objects, and recommended remediation. |

A target shown as **Ready with conditions** can include findings that require remediation. Open the target details to review the affected databases and objects before planning the migration.

#### Target sizing recommendations

When sizing information is available, the report can include:

- Recommended service tier
- Recommended compute configuration in vCores
- Recommended storage
- Database-level sizing (for Azure SQL Database targets)
- Target-specific storage configuration
- Reasons for the recommendation, based on the assessment's compute, memory, storage, and I/O inputs

Sizing represents a recommended minimum target configuration based on the assessment data available at report-generation time. Validate the recommendation against expected production workload, growth, resiliency, and operational requirements before provisioning the target.

> [!TIP]  
> Review the recommendation details to understand the sizing factors that influenced the recommended configuration. Depending on the assessment data available, these factors can include compute, memory, storage, IOPS, and I/O throughput.

#### Pricing recommendations

When pricing information is available, the report provides an estimated monthly cost for each evaluated target. The estimate can include:

- Compute cost
- Storage cost
- Total estimated monthly cost
- Pricing region
- Currency
- Pricing basis
- Available reservation or savings plan pricing

Commitment pricing can affect compute charges, while storage can continue to be priced separately. If pricing isn't available for a target or pricing option, the report displays the value as unavailable rather than calculating an assumed discount.

> [!IMPORTANT]  
> Prices in the assessment report are estimates. Actual Azure charges can vary based on usage, configuration, region, offer, licensing selection, discounts, taxes, and changes to Azure pricing. Use the Azure pricing tools and your organization's commercial agreement to validate costs before provisioning.

## [SQL Server migration enabled by Azure Arc](#tab/sql-arc)

Select **View Readiness Assessment** to see [precomputed assessment data collected by Azure Arc](/sql/sql-server/azure-arc/migration-assessment). You don't need to run a separate manual assessment scan.

Review the following results:

- **Assessment findings**: Compatibility issues, warnings, affected objects, and migration readiness.
- **Target sizing recommendations**: Right-sizing based on the assessment data available from Azure Arc.
- **Pricing recommendations**: Estimated target costs when pricing information is available.
- **Migration path recommendations**: Recommended target and migration approach.

---

### Select target

Compare targets from the assessment before you provision.

## [SQL Server migration](#tab/sql-standard)

When the assessment finishes, compare the available migration targets before provisioning your destination.

For each target, review:

- Migration readiness
- Compatibility findings
- Estimated monthly cost
- Minimum recommended target configuration
- Recommended service tier
- Compute and storage recommendations
- Recommendation details

The report highlights a recommended migration target. Select **View details** to review database readiness, assessment findings, target configuration, sizing information, and pricing information before you decide.

After selecting a target:

1. Select **Provision Target** to access the [Azure SQL hub](https://aka.ms/azuresqlhub).

1. Create the Azure SQL target that fits your migration requirements:

   - Azure SQL Database
   - Azure SQL Managed Instance
   - SQL Server on Azure VM

1. Validate the provisioned configuration against the recommendation and your production requirements.

## [SQL Server migration enabled by Azure Arc](#tab/sql-arc)

Choose an Azure SQL target as your [destination platform](/sql/sql-server/azure-arc/migrate-to-azure-sql-managed-instance?tabs=mi-link#select-target):

- **Azure SQL Managed Instance**: For high SQL Server compatibility with a managed platform.
- **SQL Server on Azure VM**: For lift-and-shift scenarios and operating-system-level control.

Configure the target environment based on the sizing, compatibility, and pricing recommendations provided by the assessment.

---

### Migrate data

Select the migration method that fits your target, downtime requirements, and operational needs.

## [SQL Server migration](#tab/sql-standard)

From the **Migration** landing page, select **Migrate data**.

#### SQL Managed Instance link

Use a [SQL Managed Instance link](/azure/azure-sql/managed-instance/managed-instance-link-configure-how-to-ssms) to continuously replicate data between SQL Server and Azure SQL Managed Instance.

Consider this method for online migrations that require minimal downtime.

#### Backup and restore

Use SSMS backup and restore functionality for [SQL Server migration](upgrade-sql-server.md#prepare-for-upgrade).

Consider this method when downtime is acceptable and the source and target support the required backup and restore path.

#### Azure Database Migration Service

Use [Azure Database Migration Service](/azure/dms/) for supported migration scenarios.

Use offline or online migration options when supported by the selected source and target.

Consider Azure DMS for large-scale or complex migrations.

## [SQL Server migration enabled by Azure Arc](#tab/sql-arc)

In the Azure portal, go to the SQL Server instance, and open the **Database migration** pane to choose a migration method.

#### SQL Managed Instance

After the initial environment configuration, continue with the selected integrated migration method. For more information, see [Integrated migration methods](/sql/sql-server/azure-arc/migrate-to-azure-sql-managed-instance?tabs=mi-link#integrated-migration-methods) and [Migrate data](/sql/sql-server/azure-arc/migrate-to-azure-sql-managed-instance?tabs=mi-link#migrate-data).

- **SQL Managed Instance link**: Continuous data replication with online migration.
- **Log shipping**: Log-based migration method.

#### SQL Server on Azure Virtual Machines

Use backup and restore or Azure DMS for supported migrations to SQL Server on Azure VM.

---

### Monitor migration

Track migration progress through the appropriate monitoring experience.

## [SQL Server migration](#tab/sql-standard)

Track migration progress and cut over:

1. For Azure DMS migrations, use the [Azure DMS](/azure/dms/) monitoring experience.
1. For Managed Instance link migrations, monitor the [SQL Managed Instance link](/azure/azure-sql/managed-instance/managed-instance-link-failover-how-to).

## [SQL Server migration enabled by Azure Arc](#tab/sql-arc)

Use the monitoring experience for the selected migration method to:

- Track migration progress
- Validate replication status
- Identify migration errors
- Perform the final production cutover

For more information, see [Monitor and cut over](/sql/sql-server/azure-arc/migrate-to-azure-sql-managed-instance?tabs=mi-link#monitor-and-cutover).

---

## SQL Server upgrade

In addition to Azure migration, SSMS provides [database compatibility upgrade capabilities](upgrade-sql-server.md#upgrade-assessment). The upgrade assessment identifies compatibility issues related to breaking changes, behavior changes, and deprecated features. The report also provides a feature-parity check for cross-platform database migration.

### Upgrade assessment

1. Select **Upgrade Assessment** from the **Migrate to higher version of SQL Server** section.
1. Allow the tool to evaluate compatibility-level upgrade readiness.
1. Review breaking changes and deprecated features in the report.

### Database upgrade

1. Select **Upgrade SQL Server** from the **Migrate to higher version of SQL Server** section.
1. Follow the **Upgrade Database** steps.
1. Test and complete the compatibility-level upgrade.

## Best practices

- Run an assessment before planning the migration.

- Review both target-level and database-level readiness.

- Treat **Ready with conditions** as an instruction to review and address the associated findings, not as an automatic approval to migrate.

- Validate target sizing against representative workload data, expected growth, resiliency, and performance requirements.

- Validate pricing estimates against the intended region, licensing model, commercial agreement, and current Azure pricing.

- Choose an online migration method when the production workload requires minimal downtime and the method supports your scenario.

- Test the migration and application behavior in a nonproduction environment.

- Monitor performance during and after migration.

- Plan the cutover during an approved change window.

## Migration options comparison

| Migration method | Primary target | Downtime profile | Consider when |
| --- | --- | --- | --- |
| SQL Managed Instance link | Azure SQL Managed Instance | Minimal | Requires continuous replication and an online cutover. |
| Backup and restore | Supported SQL Server and Azure SQL targets | Moderate to high | A planned outage is acceptable. |
| Log shipping | Azure SQL Managed Instance in supported integrated scenarios | Low to moderate | A log-based migration approach meets the scenario requirements. |
| Azure DMS | Supported Azure SQL targets | Depends on the selected migration mode | Requires centralized migration orchestration. |

## Known issues

### Assessment fails

- Verify connectivity to the source database.
- Check that the login has the permissions required for assessment.
- Ensure SSMS and the migration components are up to date.
- Review assessment errors in the generated report.

### Sizing or pricing recommendation is unavailable

- Confirm that the assessment completed successfully.
- Review the report for missing assessment or pricing data.
- Verify that the selected target, region, currency, and pricing option are supported by the recommendation data.
- Don't interpret an unavailable price as a zero-cost recommendation.

### Migration performance is slow

- Check network bandwidth and latency between the source and Azure.
- Review the target sizing recommendation.
- Validate compute, storage, IOPS, and throughput requirements.
- Consider Azure ExpressRoute when it fits the network architecture and migration requirements.

### Cutover validation fails

- Verify data integrity checks.
- Review application compatibility with the target platform.
- Review unresolved conditions and migration errors.
- Confirm that replication or synchronization is healthy before cutover.

## Permissions

To perform a migration, your [!INCLUDE [ssnoversion-md](../includes/ssnoversion-md.md)] instance login requires **sysadmin** permissions.

To run an assessment without running or monitoring a migration, you need the following minimum permissions.

| Object type | Database or object name | Privilege |
| --- | --- | --- |
| Server | | `CONNECT ANY DATABASE` |
| Server | | `CONNECT SQL` |
| Server | | `VIEW ANY DATABASE` |
| Server | | `VIEW ANY DEFINITION` |
| Server | | `VIEW SERVER STATE` |
| Database | All databases | `SELECT sys.sql_expression_dependencies` |
| Database | `msdb` | `EXECUTE dbo.agent_datetime` |
| Database | `msdb` | `SELECT dbo.syscategories` |
| Database | `msdb` | `SELECT dbo.sysjobhistory` |
| Database | `msdb` | `SELECT dbo.sysjobs` |
| Database | `msdb` | `SELECT dbo.sysjobsteps` |
| Database | `msdb` | `SELECT dbo.sysmail_account` |
| Database | `msdb` | `SELECT dbo.sysmail_profile` |
| Database | `msdb` | `SELECT dbo.sysmail_profileaccount` |
| Database | `msdb` | `SELECT dbo.syssubsystems` |
| Database | `msdb` | `DB DATA READER` |
| Database | `msdb` | `EXECUTE` |

## Related content

- [What is Azure SQL Managed Instance?](/azure/azure-sql/managed-instance/sql-managed-instance-paas-overview)
- [Azure Database Migration Service](/azure/dms/)
- [SQL Server on Azure Virtual Machines](/azure/azure-sql/virtual-machines/)
- [Azure Arc-enabled SQL Server](/sql/sql-server/azure-arc/overview)
