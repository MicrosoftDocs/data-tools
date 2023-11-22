---
title: Database Migration Assessment for Oracle extension
description: Learn how to install the Azure Data Studio Database Migration Assessment for Oracle extension. This extension helps guide you choose the best Azure SQL database and Azure Database for PostgreSQL migration path.
author: nilabjaball
ms.author: niball
ms.reviewer: maghan, randolphwest
ms.date: 11/22/2023
ms.service: azure-data-studio
ms.subservice: migration-extension
ms.topic: conceptual
ms.custom: sql-migration-content
---

# Database Migration Assessment for Oracle extension

The Database Migration Assessment for Oracle extension in Azure Data Studio helps you assess an Oracle workload for migrating to Azure SQL and Azure Database for PostgreSQL. The extension identifies an appropriate Azure SQL or PostgreSQL target with right-sizing recommendations, and how complex the migration can be.

## Prerequisites

- [Azure Data Studio version 1.39 or above](../download-azure-data-studio.md).
- An [Oracle database](https://www.oracle.com/database/technologies/oracle-database-software-downloads.html) running version 11g or higher.
- Oracle users should have CONNECT and SELECT ANY DICTIONARY privileges assigned.

## Install Azure Data Studio extension

Follow these steps to install the Database Migration Assessment for Oracle extension in Azure Data Studio.

1. Open the extensions manager in Azure Data Studio. You can select the extensions icon or select **Extensions** in the View menu.

1. Type *Oracle* in the search bar.

1. Select the **Database Migration Assessment for Oracle** extension and view its details.

1. Select **Install**.

   :::image type="content" source="media/database-migration-assessment-for-oracle-extension/install-database-migration-assessment-for-oracle-extension.png" alt-text="Screenshot of installing the extension." lightbox="media/database-migration-assessment-for-oracle-extension/install-database-migration-assessment-for-oracle-extension.png":::

## Configure extension settings

You can configure several extension settings after installing the extension.

1. Go to extensions and select **Database Migration Assessment for Oracle**, select the **manage settings icon**, and then select extension settings.

   :::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-extension-manage.png" alt-text="Screenshot of extension." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-extension-manage.png":::

1. Under extension settings, edit any extension settings to meet the environment's requirements.

   :::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-extension-settings-edit.png" alt-text="Screenshot of extension properties settings." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-extension-settings-edit.png":::

   > [!NOTE]  
   > To perform Oracle to PostgreSQL code assessment, the Oracle client home path and Ora2Pg installation path are mandatory parameters.

## Run assessment

Once the assessment extension installs, the next step is to connect to Oracle your database, collect metadata information from your Oracle instance and generate an assessment report.

1. Go to the connections icon in the menu bar.

   :::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-connections-menu-bar.png" alt-text="Screenshot of connections menu bar." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-connections-menu-bar.png":::

1. In the **Connection Details**, fill out the fields.
   1. In the **Connection type** field, select **Oracle**.
   1. In the **Data Source** field, type in your Oracle server name and instance.
      1. You can provide the TNS name as well. (Make sure that the `ORACLE_HOME` environment variable is set and the `TNSNAMES.ORA` file is located in the `<ORACLE_HOME>/network/admin folder`.)
      1. For container database, you can either connect the container root database using the CDB service ID, or use the pluggable database service name to connect to pluggable database.
   1. Provide the database username in the **User Id** field.
   1. Provide the database password in the **Password** field.

   :::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-connections-details.png" alt-text="Screenshot of connection details.":::
1. Select **Connect**.

1. Now, a new connection appears in the connection details menu.

1. Right-click on the Oracle connection and select **Manage**.

   :::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-manage-database-connection.png" alt-text="Screenshot showing the Manage database screen." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-manage-database-connection.png":::

1. Select **Migration Assessment**.

   :::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-select-oracle-assessment.png" alt-text="Screenshot showing the Migration Assessment database screen." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-select-oracle-assessment.png":::

1. Select **Run new Assessment**.

   :::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-run-new-oracle-assessment.png" alt-text="Screenshot showing the Run new Assessment screen." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-run-new-oracle-assessment.png":::

1. Provide your assessment details.

   1. In the **Assessment name** field, enter a title, for example, `demo1`.
   1. Enter your **Assessment setting**.
      1. Enter the destination migration database in the **Target Platform** field. Currently, it supports Azure SQL and PostgreSQL as targets.

         > [!NOTE]  
         > PostgreSQL target is in preview. This target option will be discontinued. You should export any prior assessments.

      1. In the **Performance data collection** section, either select **Run performance data collection on Oracle database (connected)** or **Add AWR report**.

         The recommendation is to use the connected option if you're running this tool during a peak or realistic load. Otherwise, provide the AWR reports generated in the past for performance and sizing recommendations.

         > [!NOTE]  
         > The AWR report assessment option isn't enabled for pluggable database.

      1. Enter the multiplier value in the **Scale factor** field.

         - If the recommended SKU needs to consider other peak loads, the scale factor multiplier should be greater than 1. For example, Burst Load, Seasonal usage, and future capacity planning. When a partial Oracle schema workload is migrated, the multiplier should be less than 1.

      1. In the **Percentile utilization** field, enter the percentile value for sizing the Azure target.

         - The percentile value of the performance sample set to be considered for sizing the Azure target.

   :::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-assessment-details.png" alt-text="Screenshot showing the assessment details screen." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-assessment-details.png":::

1. There are two types of assessment:

   - **Workload Assessment.** In this assessment, the Oracle assessment module performs a lightweight discovery of the schema objects and categorizes the schema complexity for migration to various categories with a high-level estimate for conversion hours.  This preassessment helps to find the feasibility of the migration to the target platform.

   - **Code Assessment.** The code assessment performs an in-depth assessment of the Oracle schema objects and then suggests an overall readiness of the code objects with "ready", "need review", and "not ready" object types at a granular level and its associated conversion hours with higher accuracy.

     > [!NOTE]  
     > The extension uses the open-source Ora2Pg schema converter for code assessments.

     If the Oracle client and/or Ora2Pg isn't installed on the same machine as Azure Data Studio, either manually install them, or use the [Ora2Pg installation script](https://github.com/microsoft/OrcasNinjaTeam/tree/master/ora2pg-install) from GitHub.

     If the Oracle client and Ora2Pg are installed, ensure that the Oracle client home path, and Ora2Pg installation path are updated in the extension settings.

     - When you select Code assessment for SQL scenarios, select the schemas that you would like to access for Oracle to SQL conversion and migration. By default, all the eligible schemas are selected for the assessment.

1. Choose **Run validation** to perform the prerequisites and various validation rules related to security permissions,  configuration settings etc. If validation fails, then you need to fix the errors to proceed further.

1. When Validation is successful, you can select **Run assessment**.

1. Now, you see the new assessment in the "Last five assessments" section.

   :::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-demo.png" alt-text="Screenshot showing the option to name the assessment." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-demo.png":::

1. Select the assessment link to view the assessment details page. You can view the latest assessment status.

   :::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-latest-assessment-status.png" alt-text="Screenshot showing the latest assessment status." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-latest-assessment-status.png":::

1. Select **Refresh**, or wait until the assessment completes. By default, the assessment status page refreshes every 15 seconds. The status shows you one of four statuses: *success*, *failed*, *in-progress*, or *canceled*.

## View the assessment

Once the assessment is complete, a consolidated output using *cards* is generated for either each Azure SQL target: **SQL Server on Azure Virtual Machines**, **Azure SQL Database**, and **Azure SQL Managed Instance**, or **Azure Database for PostgreSQL - Flexible server**.

:::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-view-assessment.png" alt-text="Screenshot of the view assessment option." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-view-assessment.png":::

Each card has multiple sections. The card shows the overall feasibility of the migration to the target. You can drill down on various workloads under various migration complexity categories:

- The feature compatibility section provides the feature assessment review result.
- SKU recommendation provides the proper sizing of the target.
- The code assessment provides the code complexity of database objects.

When you select **View report details**, it first shows the assessment summary.

:::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-card-sections.png" alt-text="Screenshot showing assessment summary." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-card-sections.png":::

If the target selected is Database for Azure PostgreSQL, either the Database details tab or Code assessment tab is visible based on the assessment type selection.

The following Database details tab provides the breakdown per schema basis. It shows the list of schemas discovered, the migration feasibility, and the estimated time to convert the schema in hours.

:::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-per-schema-basis.png" alt-text="Screenshot showing the breakdown per schema basis." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-per-schema-basis.png":::

This estimation is based on a statistical model that applies to the object count, lines of code, enabled features, and size of the database. For more accurate estimate on the code conversion, use code assessment.

> [!NOTE]  
> The following system or Oracle built-in schemas are excluded from the workload assessment:
>  
> `APEX`, `APPQOSSYS`, `AUDSYS`, `CSMIG`, `CTXSYS`, `DBMS_PRIVILEGE_CAPTURE`, `DBSFWUSER`, `DBSNMP`, `DIP`, `DMSYS`, `DVF`, `DVSYS`, `EXFSYS`, `FLOW_`, `GSMADMIN_INTERNAL`, `LBACSYS`, `MDDATA`, `MDSYS`, `MGDSYS`, `MGMT_VIEW`, `MTMSYS`, `ODM`, `ODM_MTR`, `OJVMSYS`, `OLAPSYS`, `ORACLE_OCM`, `ORDDATA`, `ORDPLUGINS`, `ORDSYS`, `OSE$HTTP$ADMIN`, `OUTLN`, `OWBSYS`, `OWBSYS_AUDIT`, `PERFSTAT`, `SDE`, `SI_INFORMTN_SCHEMA`, `SPATIAL_CSW_ADMIN_USR`, `SPATIAL_WFS_ADMIN_USR`, `SQLTXPLAIN`, `SYS`, `SYSMAN`, `SYSTEM`, `TRACESRV`, `TSMSYS`, `WEBSYS`, `WKPROXY`, `WKSYS`, `WK_PROXY`, `WK_TEST`, `WMSYS`, `XDB`, `XS$NULL`

The SKU recommendation provides the following items:

- The suitable Azure target.
- The service tier.
- The metric thresholds are used to provide the recommended SKU.

  :::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-skus.png" alt-text="Screenshot showing SKU recommendations." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-skus.png":::

The SKU recommendation evaluates various performance metrics, such as CPU, memory, IOPS, latency, and storage. Based on the usage and the configuration data, the recommender provides the suitable target and the appropriate service tier. The SKU recommendation is based on the container root instance or pluggable database utilization. Schema selection is ignored and not applicable to the SKU sizing.

> [!NOTE]  
> If the automatic workload repository (AWR) feature is enabled on the Oracle instance, the SKU recommender will use the `DBA_HIST_` views to gather the performance metrics metadata. Otherwise, the recommender will use server configuration and other system view information for sizing the Azure SQL target.

The code compatibility (for PostgreSQL targets only) provides a summary of schema objects that can be converted to the Azure target. The report provides the breakup of the objects that can be converted automatically, ready with conditions, and need to be remediated and converted manually.

:::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-code-compatibility-pg.png" alt-text="Screenshot showing the code compatibility report." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-code-compatibility-pg.png":::

The report shows the total number of objects and conversion effort hours required to migrate code to the Azure PostgreSQL database. The graphical image provides the breakup for each schema object type such as tables, views, and clusters. The efforts are categorized as "Ready - automatically converted", "Needs review", and "Not ready - requires manual conversion".

A drill-down for the "Not ready" and "Needs review" sections provides the list of remediation tasks and the effort hours for each task.

:::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-remediation-pg.png" alt-text="Screenshot showing the remediation task." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-remediation-pg.png":::

The feature assessment provides the Oracle to Azure data target mapped features and the effort required for migrating those capabilities to the Azure target.

:::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-mapped-assessment.png" alt-text="Screenshot showing the mapped assessment." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-mapped-assessment.png":::

You can download the report for offline viewing by selecting **Download combined reports** or **Download individual reports**.

:::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-download-report.png" alt-text="Screenshot showing the download assessment report option." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-download-report.png":::

You can also cancel an ongoing assessment, delete an assessment and move assessments to another directory.

## Change assessment path

1. Go to the extension marketplace and search for *Database Migration Assessment for Oracle*.
1. Select the **Manage** icon, and select **Extensions settings**.
1. Provide the new assessment path under Oracle Assessment: Assessment Path.

:::image type="content" source="media/database-migration-assessment-for-oracle-extension/dmafo-extension.png" alt-text="Screenshot showing the Change assessment path option." lightbox="media/database-migration-assessment-for-oracle-extension/dmafo-extension.png":::

## Troubleshoot

### Logs

The extension stores errors, warnings, and other diagnostic logs in the default log directory:

- Windows - `C:\Users\<username>.dmaoracle\logs\`
- Linux - `~/.dmaoracle/logs`
- macOS - `/Users/<username>/.dmaoracle/logs`

> [!NOTE]  
> By default, the extension stores the last seven log files.

To change the log directory, update the `LogDirectory` property in the extension settings file.

| Operating system | Path |
| --- | --- |
| Windows | `C:\Users\<username>\.azuredatastudio\extensions\microsoft.azuredatastudio-dma-oracle-<VersionNumber>\bin\service\Properties\ConfigSettings\extension-settings.json` |
| Linux | `~/.azuredatastudio/extensions/microsoft.azuredatastudio-dma-oracle-<VersionNumber>/<VersionNumber>/bin/service/Properties/ConfigSettings/extension-settings.json` |
| macOS | `/Users/<username>/.azuredatastudio/extensions/microsoft.azuredatastudio-dma-oracle-<VersionNumber>/<VersionNumber>/bin/service/Properties/ConfigSettings/extension-settings.json` |

For more information about troubleshooting issues, visit [Troubleshoot Database Migration Assessment for Oracle extension errors](database-migration-assessment-for-oracle-extension-troubleshoot.md).

### Known issues and limitations

- **Path provided doesn't exist.**

  Reason: Missing files or missing permission on the assessment folder.

  **Possible solution:**

  - The user has read and write permission on the assessment folder.
  - If there's a missing file or folder, delete the assessment and generate a new assessment.

- **Encountered connection timeout exception while interacting with Oracle.**

  Reason: Failed to connect to Oracle instance.

  **Possible solution:**

  - Check if firewall rules block the Oracle listening port.
  - Run `tnsping` and see if the Service ID gets resolved.

## Contact Microsoft for help

If you need further assistance from Microsoft, contact [@dmasupport](mailto:dmasupport@microsoft.com). For faster turnaround, you can attach the logs from the [default log directory](#logs).

## Related content

- [Extension for Oracle (Preview)](extension-for-oracle.md)
- [Azure SQL migration extension for Azure Data Studio](azure-sql-migration-extension.md)
- [Database Schema Conversion Toolkit (DSCT)](dsct/database-schema-conversion-toolkit.md)
- [Extend the functionality of Azure Data Studio](add-extensions.md)
