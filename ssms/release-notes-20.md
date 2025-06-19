---
title: "Release Notes For SQL Server Management Studio (SSMS) 20"
description: Release notes for SQL Server Management Studio (SSMS) 20.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: maghan, randolphwest, mbarickman
ms.date: 04/18/2025
ms.service: sql-server-management-studio
ms.topic: release-notes
ms.collection:
  - data-tools
---

# Release notes for SQL Server Management Studio (SSMS) 20

[!INCLUDE [sql-asdb-asdbmi-asa](includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

This article details updates, improvements, and bug fixes for SQL Server Management Studio (SSMS) 20.

[!INCLUDE [ssms-connect-aazure-ad](includes/ssms-connect-azure-ad.md)]

## Current SSMS release

For information about the latest version of SQL Server Management Studio (SSMS), see [Install SQL Server Management Studio](install/install.md).

## Release notes

This section contains release notes for SSMS 19 and earlier versions. For release notes for different versions of SSMS, see:

- [Release notes for SQL Server Management Studio 21](release-notes-21.md)
- [Release notes for SQL Server Management Studio 20](release-notes-20.md)

### 20.2.1

:::image type="icon" source="includes/media/download.svg" border="false"::: **[Download SSMS 20.2.1](https://go.microsoft.com/fwlink/?linkid=2313753)**

- Release number: 20.2.1
- Build number: 20.2.37.0
- Release date: April 8, 2025

Available languages:

- [Chinese (Simplified)](https://go.microsoft.com/fwlink/?linkid=2313753&clcid=0x804)
- [Chinese (Traditional)](https://go.microsoft.com/fwlink/?linkid=2313753&clcid=0x404)
- [English (United States)](https://go.microsoft.com/fwlink/?linkid=2313753&clcid=0x409)
- [French](https://go.microsoft.com/fwlink/?linkid=2313753&clcid=0x40c)
- [German](https://go.microsoft.com/fwlink/?linkid=2313753&clcid=0x407)
- [Italian](https://go.microsoft.com/fwlink/?linkid=2313753&clcid=0x410)
- [Japanese](https://go.microsoft.com/fwlink/?linkid=2313753&clcid=0x411)
- [Korean](https://go.microsoft.com/fwlink/?linkid=2313753&clcid=0x412)
- [Portuguese (Brazil)](https://go.microsoft.com/fwlink/?linkid=2313753&clcid=0x416)
- [Russian](https://go.microsoft.com/fwlink/?linkid=2313753&clcid=0x419)
- [Spanish](https://go.microsoft.com/fwlink/?linkid=2313753&clcid=0x40a)

#### Security advisories 20.2.1

| Feature | Details |
| --- | --- |
| Security | Addressed vulnerability [CVE-2025-29803](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-29803) for Visual Studio Tools for Applications 2019. If you have already installed SSMS 20.2 or an earlier version installed on your machine, you are not exposed to this vulnerability. Installing SSMS 20.2.1 does not update existing VSTA files if you have SSMS 20.2 or earlier versions installed. If security or vulnerability tracking applications state that your system is still at risk after updating to SSMS 20.2.1 from an earlier 20.x release, you can install the latest [Microsoft Visual Studio Tools for Applications 2019](https://www.microsoft.com/download/details.aspx?id=58317) to update VSTA. |

#### Known issues 20.2.1

| Feature | Details | Workaround |
| --- | --- | --- |
| Analysis Services | When you connect to Analysis Services with Microsoft Entra MFA, if you add a new role or open properties for a role, the message "the identity of the user being added to the role is not fetched properly" appears. | This error is benign and can be ignored. The error is addressed within the Azure infrastructure, and no updates to SSMS are required. |
| Analysis Services | After adding a new role, or when opening properties for an existing role, you can't use **Search by name or email address** to add a user. | A user can be added with the **Manual Entry** option. |
| Database Designer | Selecting the Design option for a view referencing a table using spatial data causes SSMS to crash. | Use T-SQL to make changes to the view. |
| Database Mirroring | If you launch the Database Mirroring Monitor from the mirrored node, the primary node isn't listed. | Register the mirrored node from Database Mirroring Monitoring, or use SSMS 18.12.1 to monitor from the mirrored node. |
| General SSMS | Import settings from SSMS 17 option not available. | Settings can be imported from SSMS 18. |
| Linked servers | Creating a linked server to Azure SQL Database with [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)] selected as Server type connects to the `master` database. | To create a linked server to Azure SQL Database, select **Other data source** for the **Server type**, and select **Microsoft OLE DB Provider for SQL Server** or **Microsoft OLE DB Driver for SQL Server** as the **Provider**. Enter the logical server name in the Data source field and the database name in the Catalog field. |
| Maintenance Plan | Selecting "Contents" after adding a backup file within the Destination pane of the Backup Database Task, causes the dialog to disappear. | Use SSMS 20.1 or SSMS 19.3 to access the Contents dialog. |
| PolyBase | PolyBase node isn't visible in Object Explorer when you connect to [!INCLUDE [sssql22-md](includes/sssql22-md.md)]. | Use SSMS 18.12.1. |
| Profiler | The Profiler menu isn't localized. | No current alternative. |
| Replication | If Azure SQL Managed Instance is the publisher and SSMS is running on a machine that isn't in the same virtual network as the publisher, you aren't able to insert a tracer token via Replication Monitor. | To insert tracer tokens, use Replication Monitor in SSMS on a machine that is in the same virtual network as the Azure SQL Managed Instance publisher. |
| Stretch Database | Removed Stretch Database Wizard. | Use T-SQL to configure Stretch Database or use SSMS 18.9.1 or earlier to use the Stretch Database Wizard. |

See [Known issues using Strict Encryption in 20.0](#known-issues-using-strict-encryption-in-200) for known issues using SSMS 20.x and Strict Encryption.

You can reference the [SSMS Developer Community](https://aka.ms/ssms-feedback) site for other known issues and to provide feedback to the product team.

## Previous SSMS releases

Download previous SSMS versions by selecting the download link in the related section.

| SSMS version | Build number | Release date |
| --- | --- | --- |
| [20.2](#202) | 20.2.30.0 | July 9, 2024 |
| [20.1](#201) | 20.1.10.0 | April 9, 2024 |
| [20.0](#200) | 20.0.70.0 | March 19, 2024 |

### 20.2

:::image type="icon" source="includes/media/download.svg" border="false"::: **[Download SSMS 20.2](https://go.microsoft.com/fwlink/?linkid=2278035&clcid=0x409)**

- Release number: 20.2
- Build number: 20.2.30.0
- Release date: July 9, 2024

Available languages:

- [Chinese (Simplified)](https://go.microsoft.com/fwlink/?linkid=2278035&clcid=0x804)
- [Chinese (Traditional)](https://go.microsoft.com/fwlink/?linkid=2278035&clcid=0x404)
- [English (United States)](https://go.microsoft.com/fwlink/?linkid=2278035&clcid=0x409)
- [French](https://go.microsoft.com/fwlink/?linkid=2278035&clcid=0x40c)
- [German](https://go.microsoft.com/fwlink/?linkid=2278035&clcid=0x407)
- [Italian](https://go.microsoft.com/fwlink/?linkid=2278035&clcid=0x410)
- [Japanese](https://go.microsoft.com/fwlink/?linkid=2278035&clcid=0x411)
- [Korean](https://go.microsoft.com/fwlink/?linkid=2278035&clcid=0x412)
- [Portuguese (Brazil)](https://go.microsoft.com/fwlink/?linkid=2278035&clcid=0x416)
- [Russian](https://go.microsoft.com/fwlink/?linkid=2278035&clcid=0x419)
- [Spanish](https://go.microsoft.com/fwlink/?linkid=2278035&clcid=0x40a)

#### What's new in 20.2

| Feature | Details |
| --- | --- |
| Always Encrypted | Introduced support for temporal tables. |
| Always Encrypted | Introduced logging for the Always Encrypted wizard to facilitate troubleshooting. |
| Drivers | Updated SSMS to use the latest driver version for MSOLEDBSQL (18.7.4). The inclusion of this new version could require users who also have older versions of the driver to reboot after installing SSMS 20.2. For more information, review the release notes for the [Microsoft OLE DB driver](/sql/connect/oledb/release-notes-for-oledb-driver-for-sql-server). |
| Integration Services | Removed HADOOP files from SQL Server Integration Services (SSIS) installation files, this addresses [CVE-2022-25168](https://nvd.nist.gov/vuln/detail/CVE-2022-25168). |
| Libraries | Updated DacFx to version 162.3.566. |
| Libraries | Updated Server Management Objects (SMO) to version 171.36.0. |
| Libraries | Removed the Microsoft Visual C++ 2013 Redistributable (x86) from the SSMS installation. Upgrading from a previous version of 20.x does not remove the files. |
| Link feature for Azure SQL Managed Instance | Introduced support for a simplified link failover experience. |

#### Bug fixes in 20.2

| Feature | Details |
| --- | --- |
| Accessibility | Added accessibility support for Expand/Collapse in Database Properties. |
| Accessibility | Improved accessibility of radio buttons in the Restore Database dialog using arrow or tab keys. |
| Accessibility | Fixed labels for radio button controls in the Files page of Database Properties. |
| Accessibility | Fixed an issue with focus control in the Data Classification page. |
| Accessibility | Addressed issues with incomplete or unnecessary screen reader announcements in the Data Classification page. |
| Always Encrypted | Fixed error "Object reference not set to an instance of an object", which occurred when trying to create a Column Master Key after signing out of Azure. |
| Connection | Addressed an issue with truncated authentication methods in the Connection dialog when using Russian locale. |
| Connection | Fixed incorrect length of dropdown lists after changing the engine type. |
| Integration Services | Resolved error "The certificate chain was issued by an authority that is not trusted" when creating or modifying an Integration Services job step in SQL Agent. See [SSMS 20 - certificate error when viewing or editing Agent jobs that run SSIS packages](https://feedback.azure.com/d365community/idea/235c6a29-0bf8-ee11-a1fe-6045bdfe7c85). |
| Link feature for Azure SQL Managed Instance | Resolved a problem where SQL Server endpoint certificates were not loaded for the Managed Instance. |
| Object Explorer | Updated the script generated for external file formats to include the FIRST ROW property. |
| Object Explorer | Added Table-Valued Functions node within the Programmability > Functions node for Synapse. |
| Query Editor | Updated lock icons in the query editor toolbar to be color-aware. |
| Query Editor | Addressed error "Unable to query transaction count. The SQL text editor window will close without committing any open transactions" when closing an unsaved editor with either SHOWPLAN_ALL or SHOWPLAN_XML enabled, and the option **Check for open transactions before closing T-SQL query windows** enabled. |
| Query Plans | Reduced the number of characters in the Description of an execution plan to 1000. The full query is available using the ellipses. |
| Query Store | Addressed an issue where the **Queries With Forced Plans** report generated the error "Couldn't connect to database", see [Query Store report 'Queries with Forced Plans' fails trying to sort by last execution time](https://feedback.azure.com/d365community/idea/6e0360ee-f5f7-ee11-a73c-6045bd77de95). |
| Query Store | Fixed Tracked Queries report to correctly display the metric selected in the Configure dialog. |
| Query Store | Removed unnecessary border around options within the Configure dialog. |
| Query Store | Fixed an issue where no metric was selected in the Configure dialog for the Tracked Queries report. |
| Query Store | Addressed behavior where drop down menus in the report for Metric and Statistic were not updated after they were changed in the Configure dialog. |
| Replication | Fixed an issue where Replication Conflict Viewer was inaccessible when using Mandatory or Optional encryption, see [SSMS 20.0 (Replication - View Conflicts) bug](https://feedback.azure.com/d365community/idea/55c6a655-3aec-ee11-a73d-000d3adc65a4). |

#### Known issues 20.2

| Feature | Details | Workaround |
| --- | --- | --- |
| Analysis Services | When you connect to Analysis Services with Microsoft Entra MFA, if you add a new role or open properties for a role, the message "the identity of the user being added to the role is not fetched properly" appears. | This error is benign and can be ignored. The error is addressed within the Azure infrastructure, and no updates to SSMS are required. |
| Analysis Services | After adding a new role, or when opening properties for an existing role, you can't use **Search by name or email address** to add a user. | A user can be added with the **Manual Entry** option. |
| Database Designer | Selecting the Design option for a view referencing a table using spatial data causes SSMS to crash. | Use T-SQL to make changes to the view. |
| Database Mirroring | If you launch the Database Mirroring Monitor from the mirrored node, the primary node isn't listed. | Register the mirrored node from Database Mirroring Monitoring, or use SSMS 18.12.1 to monitor from the mirrored node. |
| General SSMS | Import settings from SSMS 17 option not available. | Settings can be imported from SSMS 18. |
| Linked servers | Creating a linked server to Azure SQL Database with [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)] selected as Server type connects to the `master` database. | To create a linked server to Azure SQL Database, select **Other data source** for the **Server type**, and select **Microsoft OLE DB Provider for SQL Server** or **Microsoft OLE DB Driver for SQL Server** as the **Provider**. Enter the logical server name in the Data source field and the database name in the Catalog field. |
| Maintenance Plan | Selecting "Contents" after adding a backup file within the Destination pane of the Backup Database Task, causes the dialog to disappear. | Use SSMS 20.1 or SSMS 19.3 to access the Contents dialog. |
| PolyBase | PolyBase node isn't visible in Object Explorer when you connect to [!INCLUDE [sssql22-md](includes/sssql22-md.md)]. | Use SSMS 18.12.1. |
| Profiler | The Profiler menu isn't localized. | No current alternative. |
| Replication | If Azure SQL Managed Instance is the publisher and SSMS is running on a machine that isn't in the same virtual network as the publisher, you aren't able to insert a tracer token via Replication Monitor. | To insert tracer tokens, use Replication Monitor in SSMS on a machine that is in the same virtual network as the Azure SQL Managed Instance publisher. |
| Stretch Database | Removed Stretch Database Wizard. | Use T-SQL to configure Stretch Database or use SSMS 18.9.1 or earlier to use the Stretch Database Wizard. |

See [Known issues using Strict Encryption in 20.0](#known-issues-using-strict-encryption-in-200) for known issues using SSMS 20.x and Strict Encryption.

You can reference the [SSMS Developer Community](https://aka.ms/ssms-feedback) site for other known issues and to provide feedback to the product team.

### 20.1

:::image type="icon" source="includes/media/download.svg" border="false"::: **[Download SSMS 20.1](https://go.microsoft.com/fwlink/?linkid=2267019&clcid=0x409)**

- Release number: 20.1
- Build number: 20.1.10.0
- Release date: April 9, 2024

Available languages:

- [Chinese (Simplified)](https://go.microsoft.com/fwlink/?linkid=2267019&clcid=0x804)
- [Chinese (Traditional)](https://go.microsoft.com/fwlink/?linkid=2267019&clcid=0x404)
- [English (United States)](https://go.microsoft.com/fwlink/?linkid=2267019&clcid=0x409)
- [French](https://go.microsoft.com/fwlink/?linkid=2267019&clcid=0x40c)
- [German](https://go.microsoft.com/fwlink/?linkid=2267019&clcid=0x407)
- [Italian](https://go.microsoft.com/fwlink/?linkid=2267019&clcid=0x410)
- [Japanese](https://go.microsoft.com/fwlink/?linkid=2267019&clcid=0x411)
- [Korean](https://go.microsoft.com/fwlink/?linkid=2267019&clcid=0x412)
- [Portuguese (Brazil)](https://go.microsoft.com/fwlink/?linkid=2267019&clcid=0x416)
- [Russian](https://go.microsoft.com/fwlink/?linkid=2267019&clcid=0x419)
- [Spanish](https://go.microsoft.com/fwlink/?linkid=2267019&clcid=0x40a)

#### What's new in 20.1

| Feature | Details |
| --- | --- |
| Drivers | Updated SSMS to use the latest driver versions for MSODBCSQL.MSI (17.10.6.1) and MSOLEDBSQL.MSI (18.7.2). The inclusion of these new versions could require users who also have older versions of the drivers to reboot after installing SSMS 20.1. For more information, review the release notes for the [Microsoft ODBC driver](/sql/connect/odbc/windows/release-notes-odbc-sql-server-windows) and the [Microsoft OLE DB driver](/sql/connect/oledb/release-notes-for-oledb-driver-for-sql-server). |
| Drivers | Updated Microsoft.Data.SqlClient version from 5.1.4 to 5.1.5. |
| Libraries | Updated Server Management Objects (SMO) version to 171.31.0. |
| Libraries | Updated Microsoft Visual C++ Redistributable version to 14.38.33135.0. The inclusion of these new versions could require users who also have older versions of the drivers to reboot after installing SSMS 20.1. |
| Object Explorer | Updated Object Explorer to display table names prefixed with schema in Graph edge constraint connections. |

#### Bug fixes in 20.1

| Feature | Details |
| --- | --- |
| Maintenance Plans | Resolved issue where Backup Database Task dialog closed after selecting the **Files and Filegroups** radio button in the dialog. |
| SqlParser | Added support for DEFAULT_DATABASE option to CREATE LOGIN T-SQL syntax when using EXTERNAL PROVIDER. |
| SqlParser | Added support for NATIVE_COMPILATION and SCHEMABINDING options to CREATE TRIGGER T-SQL syntax. |

#### Known issues 20.1

| Feature | Details | Workaround |
| --- | --- | --- |
| Analysis Services | When you connect to Analysis Services with Microsoft Entra MFA, if you add a new role or open properties for a role, the message "the identity of the user being added to the role is not fetched properly" appears. | This error is benign and can be ignored. The error is addressed within the Azure infrastructure, and no updates to SSMS are required. |
| Analysis Services | After adding a new role, or when opening properties for an existing role, you can't use **Search by name or email address** to add a user. | A user can be added with the **Manual Entry** option. |
| Database Designer | Selecting the Design option for a view referencing a table using spatial data causes SSMS to crash. | Use T-SQL to make changes to the view. |
| Database Mirroring | If you launch the Database Mirroring Monitor from the mirrored node, the primary node isn't listed. | Register the mirrored node from Database Mirroring Monitoring, or use SSMS 18.12.1 to monitor from the mirrored node. |
| General SSMS | Import settings from SSMS 17 option not available. | Settings can be imported from SSMS 18. |
| Link feature for Azure SQL Managed Instance | After you remove an existing mirroring endpoint certificate on [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)], link creation through the wizard might fail due to unestablished trust between [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)] and Azure SQL Managed Instance, even though all checks are successful. | Use PowerShell command `Get-AzSqlInstanceServerTrustCertificate` to check whether [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)] mirroring endpoint certificate named `<SQL_Server_Instance_Name>` exists in the Azure SQL Managed Instance. If so, use PowerShell command `Remove-AzSqlInstanceServerTrustCertificate` to remove it before a new link creation attempt. |
| Linked servers | Creating a linked server to Azure SQL Database with [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)] selected as Server type connects to the `master` database. | To create a linked server to Azure SQL Database, select **Other data source** for the **Server type**, and select **Microsoft OLE DB Provider for SQL Server** or **Microsoft OLE DB Driver for SQL Server** as the **Provider**. Enter the logical server name in the Data source field and the database name in the Catalog field. |
| PolyBase | PolyBase node isn't visible in Object Explorer when you connect to [!INCLUDE [sssql22-md](includes/sssql22-md.md)]. | Use SSMS 18.12.1. |
| Profiler | The Profiler menu isn't localized. | No current alternative. |
| Query Store Reports | Track Queries report does not update when alternate Metric and Execution options are selected within Configure. | Use SSMS 19.x. |
| Replication | If Azure SQL Managed Instance is the publisher and SSMS is running on a machine that isn't in the same virtual network as the publisher, you aren't able to insert a tracer token via Replication Monitor. | To insert tracer tokens, use Replication Monitor in SSMS on a machine that is in the same virtual network as the Azure SQL Managed Instance publisher. |
| SSIS | When creating or modifying an SSIS job step in a SQL Agent job, you receive the error "A connection was successfully established with the server, but then an error occurred during the login process. (provider: SSL Provider, error: 0 - The certificate chain was issued by an authority that is not trusted.) (Framework Microsoft SqlClient Data Provider)" regardless of whether Optional or Mandatory is selected for the Encryption property. | Use SSMS 19.3 to create or modify SSIS job steps. |
| Stretch Database | Removed Stretch Database Wizard. | Use T-SQL to configure Stretch Database or use SSMS 18.9.1 or earlier to use the Stretch Database Wizard. |

### 20.0

:::image type="icon" source="includes/media/download.svg" border="false"::: **[Download SSMS 20.0](https://go.microsoft.com/fwlink/?linkid=2264204&clcid=0x409)**

- Release number: 20.0
- Build number: 20.0.70.0
- Release date: March 19, 2024

Available languages:

- [Chinese (Simplified)](https://go.microsoft.com/fwlink/?linkid=2264204&clcid=0x804)
- [Chinese (Traditional)](https://go.microsoft.com/fwlink/?linkid=2264204&clcid=0x404)
- [English (United States)](https://go.microsoft.com/fwlink/?linkid=2264204&clcid=0x409)
- [French](https://go.microsoft.com/fwlink/?linkid=2264204&clcid=0x40c)
- [German](https://go.microsoft.com/fwlink/?linkid=2264204&clcid=0x407)
- [Italian](https://go.microsoft.com/fwlink/?linkid=2264204&clcid=0x410)
- [Japanese](https://go.microsoft.com/fwlink/?linkid=2264204&clcid=0x411)
- [Korean](https://go.microsoft.com/fwlink/?linkid=2264204&clcid=0x412)
- [Portuguese (Brazil)](https://go.microsoft.com/fwlink/?linkid=2264204&clcid=0x416)
- [Russian](https://go.microsoft.com/fwlink/?linkid=2264204&clcid=0x419)
- [Spanish](https://go.microsoft.com/fwlink/?linkid=2264204&clcid=0x40a)

#### What's new in 20.0

| Feature | Details |
| --- | --- |
| Connection | The connection security properties **Encryption** and **Trust server certificate** now exist on the main sign in page in the Connection dialog for easier access. For more information, see [Connect with SQL Server Management Studio](quickstarts/ssms-connect.md). |
| Connection | A new property, **Host Name in Certificate**, used with the *Strict (SQL Server 2022 and Azure SQL)* and *Mandatory* **Encryption** options, now exists on the Login page of the Connection dialog. |
| Connection | Added icons to the Query Editor status bar to indicate the encryption method used for the connection. |
| Connection | Added Microsoft Entra ID authentication to **New Login** wizard. |
| Drivers | Updated Microsoft.Data.SqlClient version to 5.1.4, which includes support for Strict encryption and Transport Layer Security (TLS) 1.3. |
| Libraries | Updated Server Management Objects (SMO) version to 171.30.0 |
| Libraries | Updated DacFx version to 162.1.x. |
| Options | Introduced a new option, **Trust server certificate for imported connections**, in **Tools > Options > SQL Server Object Explorer > Commands** under **Connection security**. For more information, see [Options (SQL Server Object Explorer - Commands)](menu-help/options-sql-server-object-explorer-commands.md). |

#### Bug fixes in 20.0

| Feature | Details |
| --- | --- |
| Always Encrypted | The **New Column Master Key** dialog supports Azure Key Vault using role permissions for authorization. |
| Connection | Resolved an issue with SSMS crashing when trying to connect to Azure Storage because the user didn't have access to any containers within the storage account. |
| Connection | Fixed an issue where users couldn't change their password with **Trust server certificate** enabled. |
| Link feature for Azure SQL Managed Instance | Improved handling for importing and deleting certificates. |
| Link feature for Azure SQL Managed Instance | Addressed issues related to text and images in the Link wizards. |
| Security | Addressed vulnerability [CVE-2023-2975](https://nvd.nist.gov/vuln/detail/CVE-2023-2975) for the OpenSSL library. |

#### Known issues 20.0

| Feature | Details | Workaround |
| --- | --- | --- |
| Analysis Services | When you connect to Analysis Services with Microsoft Entra MFA, if you add a new role or open properties for a role, the message "the identity of the user being added to the role is not fetched properly" appears. | This error is benign and can be ignored. The error is addressed within the Azure infrastructure, and no updates to SSMS are required. |
| Analysis Services | After adding a new role, or when opening properties for an existing role, you can't use **Search by name or email address** to add a user. | A user can be added with the **Manual Entry** option. |
| Database Designer | Selecting the Design option for a view referencing a table using spatial data causes SSMS to crash. | Use T-SQL to make changes to the view. |
| Database Mirroring | If you launch the Database Mirroring Monitor from the mirrored node, the primary node isn't listed. | Register the mirrored node from Database Mirroring Monitoring, or use SSMS 18.12.1 to monitor from the mirrored node. |
| General SSMS | Import settings from SSMS 17 option not available. | Settings can be imported from SSMS 18. |
| Link feature for Azure SQL Managed Instance | After you remove an existing mirroring endpoint certificate on [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)], link creation through the wizard might fail due to unestablished trust between [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)] and Azure SQL Managed Instance, even though all checks are successful. | Use PowerShell command `Get-AzSqlInstanceServerTrustCertificate` to check whether [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)] mirroring endpoint certificate named `<SQL_Server_Instance_Name>` exists in the Azure SQL Managed Instance. If so, use PowerShell command `Remove-AzSqlInstanceServerTrustCertificate` to remove it before a new link creation attempt. |
| Linked servers | Creating a linked server to Azure SQL Database with [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)] selected as Server type connects to the `master` database. | To create a linked server to Azure SQL Database, select **Other data source** for the **Server type**, and select **Microsoft OLE DB Provider for SQL Server** or **Microsoft OLE DB Driver for SQL Server** as the **Provider**. Enter the logical server name in the Data source field and the database name in the Catalog field. |
| Maintenance Plans | Selecting the **Files and Filegroups** radio button in the Backup Database Task causes the dialog to close unexpectedly. | No current alternative. |
| PolyBase | PolyBase node isn't visible in Object Explorer when you connect to [!INCLUDE [sssql22-md](includes/sssql22-md.md)]. | Use SSMS 18.12.1. |
| Profiler | The Profiler menu isn't localized. | No current alternative. |
| Query Store Reports | Track Queries report does not update when alternate Metric and Execution options are selected within Configure. | Use SSMS 19.x. |
| Replication | If Azure SQL Managed Instance is the publisher and SSMS is running on a machine that isn't in the same virtual network as the publisher, you aren't able to insert a tracer token via Replication Monitor. | To insert tracer tokens, use Replication Monitor in SSMS on a machine that is in the same virtual network as the Azure SQL Managed Instance publisher. |
| SSIS | When creating or modifying an SSIS job step in a SQL Agent job, you receive the error "A connection was successfully established with the server, but then an error occurred during the login process. (provider: SSL Provider, error: 0 - The certificate chain was issued by an authority that is not trusted.) (Framework Microsoft SqlClient Data Provider)" regardless of whether Optional or Mandatory is selected for the Encryption property. | Use SSMS 19.3 to create or modify SSIS job steps. |
| Stretch Database | Removed Stretch Database Wizard. | Use T-SQL to configure Stretch Database or use SSMS 18.9.1 or earlier to use the Stretch Database Wizard. |

#### Known issues using Strict Encryption in 20.0

| Feature | Details | Workaround |
| --- | --- | --- |
| Connection | When SQL Server is configured with **Force Strict Encryption**, selecting **Azure Data Studio > New Query** from the server or database menu generates the error, "A connection was successfully established with the server, but then an error occurred during the pre-login handshake. (provider: TCP provider, error: 0 - An existing connection was forcibly closed by the remote host.)" | Update the connection to use *Strict* instead of *Mandatory* for the **Encrypt** property in Azure Data Studio, and then connect. |
| Connection | Connecting to SQL Server with *Strict (SQL 2022 and Azure SQL)* selected for **Encryption** and a non-TCP/IP network protocol generates the error, "Cannot connect to SERVERNAME. A connection was successfully established with the server, but then an error occurred during the pre-login handshake. (provider: Shared Memory Provider, error: 15 - Function not supported) (Microsoft SQL Server, Error: 50)  The request is not supported" | Change the **Network protocol** connection property to use *TCP/IP*, or enable the TCP/IP protocol for the SQL Server. |
| Database Tuning Advisor | When SQL Server is configured with **Force Strict Encryption**, connection to the server from the Database Tuning Advisor isn't supported. | No alternative. |
| Maintenance Plans | When you connect to a server with *Strict (SQL Server 2022 and Azure SQL)* encryption, modifying an existing maintenance plan generates the error "Failed to connect to SERVERNAME. (Microsoft.SqlServer.ConnectionInfo) A connection was successfully established with the server, but then an error occurred during the login process. (provider: SSL Provider, error: 0 - The target principal name is incorrect.)" | The problem doesn't occur when you connect with *Mandatory* or *Optional* encryption. |
| Profiler | When SQL Server is configured with **Force Strict Encryption**, connection to the server from Profiler isn't supported, and the error "Cannot connect to SERVERNAME. Class not registered (pfutil)" is generated. | Install MSOLEDBSQL version 19, available from [Download Microsoft OLE DB Driver for SQL Server](/sql/connect/oledb/download-oledb-driver-for-sql-server). |
| Profiler | When you connect to a server with *Strict (SQL Server 2022 and Azure SQL)* encryption and MSOLEDBSQL version 19 installed, traces can't be saved to, or loaded from, a database table. | No alternative. |
| PowerShell | When you connect to a server with *Strict (SQL Server 2022 and Azure SQL)* encryption, selecting **Start Powershell** from a node in Object Explorer generates the error "SQL Server PowerShell provider error: Could not connect to SERVERNAME. [Failed to connect to server SERVERNAME. --> A connection was successfully established with the server, but then an error occurred during the pre-login handshake. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.) --> An existing connection was forcibly closed by the remote host]". | No current alternative. |
| SQL Server Logs | When SQL Server is configured with **Force Strict Encryption**, you can't view the SQL Server ERRORLOG files via Object Explorer, or executing `master.dbo.sp_enumerrorlogs` or `sys.xp_enumerrorlogs` via the Query Editor. | View the ERRORLOG files in the Log folder using File Explorer. |

### 19.3

:::image type="icon" source="includes/media/download.svg" border="false"::: **[Download SSMS 19.3](https://go.microsoft.com/fwlink/?linkid=2257624&clcid=0x409)**

- Release number: 19.3
- Build number: 19.3.4.0
- Release date: January 10, 2024

Available languages:

- [Chinese (Simplified)](https://go.microsoft.com/fwlink/?linkid=2257624&clcid=0x804)
- [Chinese (Traditional)](https://go.microsoft.com/fwlink/?linkid=2257624&clcid=0x404)
- [English (United States)](https://go.microsoft.com/fwlink/?linkid=2257624&clcid=0x409)
- [French](https://go.microsoft.com/fwlink/?linkid=2257624&clcid=0x40c)
- [German](https://go.microsoft.com/fwlink/?linkid=2257624&clcid=0x407)
- [Italian](https://go.microsoft.com/fwlink/?linkid=2257624&clcid=0x410)
- [Japanese](https://go.microsoft.com/fwlink/?linkid=2257624&clcid=0x411)
- [Korean](https://go.microsoft.com/fwlink/?linkid=2257624&clcid=0x412)
- [Portuguese (Brazil)](https://go.microsoft.com/fwlink/?linkid=2257624&clcid=0x416)
- [Russian](https://go.microsoft.com/fwlink/?linkid=2257624&clcid=0x419)
- [Spanish](https://go.microsoft.com/fwlink/?linkid=2257624&clcid=0x40a) |

## More downloads

For a list of all SQL Server Management Studio downloads, search the [Microsoft Download Center](https://www.microsoft.com/download/search.aspx?q=sql%20server%20management%20studio&p=0&r=10&t=&s=Relevancy~Descending).

For the latest release of SQL Server Management Studio, see [Install SQL Server Management Studio](install/install.md).

## Related content

- [Install SQL Server Management Studio](install/install.md)
- [Download Azure Data Studio](/azure-data-studio/download-azure-data-studio)
- [Azure Data Studio release notes](/azure-data-studio/release-notes-azure-data-studio)
