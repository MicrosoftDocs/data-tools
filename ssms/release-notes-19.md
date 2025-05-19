---
title: "Release Notes For SQL Server Management Studio (SSMS) 19 and earlier versions"
description: Release notes for SQL Server Management Studio (SSMS) 19 and earlier versions.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: maghan, randolphwest, mbarickman
ms.date: 04/18/2025
ms.service: sql-server-management-studio
ms.topic: conceptual
ms.collection:
  - data-tools
---

# Release notes for SQL Server Management Studio (SSMS) 19 and earlier versions

[!INCLUDE [sql-asdb-asdbmi-asa](includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

This article details updates, improvements, and bug fixes for SQL Server Management Studio (SSMS) 19 and earlier versions.

[!INCLUDE [ssms-connect-aazure-ad](includes/ssms-connect-azure-ad.md)]

## Current SSMS release

For information about the latest version of SQL Server Management Studio (SSMS), see [Install SQL Server Management Studio](install/install.md).

## Release notes

This section contains release notes for SSMS 19 and earlier versions. For release notes for different versions of SSMS, see:

- [Release notes for SQL Server Management Studio 21](release-notes-21.md)
- [Release notes for SQL Server Management Studio 20](release-notes-20.md)

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

#### What's new in 19.3

| Feature | Details |
| --- | --- |
| Azure Data Studio installation integration | The installation of SSMS installs Azure Data Studio 1.47.1. |

#### Bug fixes in 19.3

| Feature | Details |
| --- | --- |
| Accessibility | Addressed issue with screen reader announcing incomplete or incorrect information in the database properties dialog. |
| Always Encrypted | Fixed inability to change the **Enable Secure Enclaves** option when creating a new Azure SQL Database using a non-English installation of SSMS. |
| Availability Groups | Changed text color for primary server name in the Availability Group Dashboard, which caused the entry to appear empty. |
| Extended Events | Changed text color for data column after selecting **View Target Data** for the ring_buffer target. |
| Installer | Fixed issue where users might be prompted to update SQL Server Management Studio even if the current release is installed, see [Bug in 19.2.56.2 update version detection](https://feedback.azure.com/d365community/idea/bb5e60b9-5d85-ee11-a81c-002248544521). |
| Object Explorer | Resolved crash occurring when trying to close Object Explorer while the tree is still expanding. |
| Reports | Updated Server Dashboard report to correctly show the number of schedulers when more than 255 are available, see [SSMS 19.2 - Reports - Server dashboard - Processors used by instance - wrong number](https://feedback.azure.com/d365community/idea/cdf3d393-a689-ee11-a81c-6045bdb7ea56). |
| Security | Update to [Microsoft.Data.SqlClient 3.1.5](https://github.com/dotnet/SqlClient/blob/main/release-notes/3.1/3.1.5.md) to address [CVE-2024-0056](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2024-0056). |

#### Known issues 19.3

| Feature | Details | Workaround |
| --- | --- | --- |
| Analysis Services | When you connect to Analysis Services with Microsoft Entra MFA, if you add a new role or open properties for a role, the message "the identity of the user being added to the role is not fetched properly" appears. | This error is benign and can be ignored. It will be addressed within the Azure infrastructure soon, and no updates to SSMS are required. |
| Analysis Services | After adding a new role, or when opening properties for an existing role, you can't use **Search by name or email address** to add a user. | A user can be added with the **Manual Entry** option. |
| Database Designer | Selecting the Design option for a view that references a table using spatial data causes SSMS to crash. | Use T-SQL to make changes to the view. |
| Database Mirroring | When you launch the Database Mirroring Monitor from the mirrored node, the primary node isn't listed. | Use SSMS 18.12.1 if you need to monitor mirroring from the mirrored node. |
| General SSMS | Import settings from SSMS 17 option not available. | Settings can be imported from SSMS 18. |
| Link feature for Azure SQL Managed Instance | After you remove an existing mirroring endpoint certificate on SQL Server, link creation through the wizard might fail due to unestablished trust between SQL Server and Azure SQL Managed Instance, even though all checks are successful. | Use PowerShell command `Get-AzSqlInstanceServerTrustCertificate` to check whether SQL Server mirroring endpoint certificate named "<SQL_Server_Instance_Name>" exists in the Azure SQL Managed Instance. If so, use PowerShell command `Remove-AzSqlInstanceServerTrustCertificate` to remove it before a new link creation attempt. |
| Linked servers | Creating a linked server to Azure SQL Database with SQL Server selected as Server type connects to the `master` database. | To create a linked server to Azure SQL Database, select **Other data source** for the **Server type**, and select **Microsoft OLE DB Provider for SQL Server** or **Microsoft OLE DB Driver for SQL Server** as the **Provider**. Enter logical server name in the Data source field, and enter database name in the Catalog field. |
| PolyBase | PolyBase node isn't visible in Object Explorer when connecting to SQL 2022. | Use SSMS 18.12.1. |
| Profiler | The Profiler menu isn't localized. | No current alternative. |
| Replication | If Azure SQL Managed Instance is the publisher and SSMS is running on a machine, which isn't in the same virtual network as the publisher, you aren't able to insert a tracer token via Replication Monitor. | To insert tracer tokens, use Replication Monitor in SSMS on a machine that is in the same virtual network as the Azure SQL Managed Instance publisher. |
| Stretch DB | Removed Stretch DB Wizard. | Use T-SQL to configure Stretch DB or use SSMS 18.9.1 or earlier to use the Stretch DB Wizard. |

### 18.12.1

:::image type="icon" source="includes/media/download.svg" border="false"::: **[Download SSMS 18.12.1](https://go.microsoft.com/fwlink/?linkid=2199013&clcid=0x409)**

- Release number: 18.12.1
- Build number: 15.0.18424.0
- Release date: June 21, 2022

Available languages:

- [Chinese (Simplified)](https://go.microsoft.com/fwlink/?linkid=2199013&clcid=0x804)
- [Chinese (Traditional)](https://go.microsoft.com/fwlink/?linkid=2199013&clcid=0x404)
- [English (United States)](https://go.microsoft.com/fwlink/?linkid=2199013&clcid=0x409)
- [French](https://go.microsoft.com/fwlink/?linkid=2199013&clcid=0x40c)
- [German](https://go.microsoft.com/fwlink/?linkid=2199013&clcid=0x407)
- [Italian](https://go.microsoft.com/fwlink/?linkid=2199013&clcid=0x410)
- [Japanese](https://go.microsoft.com/fwlink/?linkid=2199013&clcid=0x411)
- [Korean](https://go.microsoft.com/fwlink/?linkid=2199013&clcid=0x412)
- [Portuguese (Brazil)](https://go.microsoft.com/fwlink/?linkid=2199013&clcid=0x416)
- [Russian](https://go.microsoft.com/fwlink/?linkid=2199013&clcid=0x419)
- [Spanish](https://go.microsoft.com/fwlink/?linkid=2199013&clcid=0x40a)

#### What's new in 18.12.1

| New Item | Details |
| --- | --- |
| Azure Data Studio installation integration | Installation of SSMS installs Azure Data Studio 1.37. |

#### Bug fixes in 18.12.1

| New Item | Details |
| --- | --- |
| Always Encrypted | Fixed issue with Column Master Key creation generating an exception when using Azure Key Vault as the key store. |
| Data Classification | Fixed issue with "Couldn't load file or assembly 'Microsoft.Information.Protection', Version=1.10.98.0" after upgrading to SSMS 18.10 or higher. See [Latest SSMS 18.11.1 breaks the Data Classification. Get missing assembly error after updating](https://feedback.azure.com/d365community/idea/af89d5d7-45a4-ec11-a81c-0022484ee92d). |
| SSMS General | Resolved error related to dacpac deployment using the Deploy Data-tier application option in Azure SQL DB with MFA. |

### 17.9.1

:::image type="icon" source="includes/media/download.svg" border="false"::: **[Download SSMS 17.9.1](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x409)**

- Release number: 17.9.1
- Build number: 14.0.17289.0
- Release date: November 21, 2018

Available languages:

- [Chinese (Simplified)](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x804)
- [Chinese (Traditional)](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x404)
- [English (United States)](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x409)
- [French](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x40c)
- [German](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x407)
- [Italian](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x410)
- [Japanese](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x411)
- [Korean](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x412)
- [Portuguese (Brazil)](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x416)
- [Russian](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x419)
- [Spanish](https://go.microsoft.com/fwlink/?linkid=2043154&clcid=0x40a)

#### What's new in 17.9.1

SQL Server utility is no longer available in versions 17.x and newer.

#### Bug fixes in 17.9.1

- Fixed an issue where users could experience their connection being closed and reopened with each query invocation when using "Azure Active Directory - Universal with MFA support" authentication with the SQL query editor. Side effects of the connection closing included global temporary tables being dropped unexpectedly and sometimes a new session ID (SPID) given to the connection.
- Fixed a long outstanding issue where a restore plan would fail to find a restore plan or generate an inefficient one under certain conditions.
- Fixed issue in the "Import Data-tier Application" wizard, which could result in an error when connected to an Azure SQL Database.

> [!NOTE]  
> Non-English localized releases of SSMS 17.x require the [KB 2862966 security update package](https://support.microsoft.com/kb/2862966) if installed on: Windows 8, Windows 7, Windows Server 2012, and Windows Server 2008 R2.

#### Uninstall and reinstall SSMS 17.x

If your SSMS installation is having problems, and a standard uninstall and reinstall doesn't resolve them, you can first try [repairing](https://support.microsoft.com/help/4028054/) the Visual Studio 2015 IsoShell. If repairing the Visual Studio 2015 IsoShell doesn't resolve the problem, the following steps have been found to fix many random issues:

1. Uninstall SSMS the same way you uninstall any application (using **Add or remove programs**).

1. Uninstall Visual Studio 2015 IsoShell **from an elevated cmd prompt**:

   ```cmd
   PUSHD "C:\ProgramData\Package Cache\FE948F0DAB52EB8CB5A740A77D8934B9E1A8E301\redist"
   vs_isoshell.exe /Uninstall /Force /PromptRestart
   ```

1. Uninstall Microsoft Visual C++ 2015 Redistributable the same way you uninstall any application. Uninstall both x86 and x64 if they're on your computer.

1. Reinstall Visual Studio 2015 IsoShell **from an elevated cmd prompt**:

   ```cmd
   PUSHD "C:\ProgramData\Package Cache\FE948F0DAB52EB8CB5A740A77D8934B9E1A8E301\redist"
   vs_isoshell.exe /PromptRestart
   ```

1. Reinstall SSMS.

1. Upgrade to the [latest version of the Visual C++ 2015 Redistributable](/cpp/windows/latest-supported-vc-redist) if you're not currently up to date.

### 16.5.3

:::image type="icon" source="includes/media/download.svg" border="false"::: **[Download SSMS 16.5.3](https://go.microsoft.com/fwlink/?LinkID=840946)**

- Release number: 16.5.3
- Build number: 13.0.16106.4
- Release date: January 30, 2017

Available languages:

- [Chinese (Simplified)](https://go.microsoft.com/fwlink/?linkid=840946&clcid=0x804)
- [Chinese (Traditional)](https://go.microsoft.com/fwlink/?linkid=840946&clcid=0x404)
- [English (United States)](https://go.microsoft.com/fwlink/?linkid=840946&clcid=0x409)
- [French](https://go.microsoft.com/fwlink/?linkid=840946&clcid=0x40c)
- [German](https://go.microsoft.com/fwlink/?linkid=840946&clcid=0x407)
- [Italian](https://go.microsoft.com/fwlink/?linkid=840946&clcid=0x410)
- [Japanese](https://go.microsoft.com/fwlink/?linkid=840946&clcid=0x411)
- [Korean](https://go.microsoft.com/fwlink/?linkid=840946&clcid=0x412)
- [Portuguese (Brazil)](https://go.microsoft.com/fwlink/?linkid=840946&clcid=0x416)
- [Russian](https://go.microsoft.com/fwlink/?linkid=840946&clcid=0x419)
- [Spanish](https://go.microsoft.com/fwlink/?linkid=840946&clcid=0x40a)

#### Bug fixes in 16.5.3

- Fixed issue introduced in SSMS 16.5.2, which was causing the expansion of the 'Table' node when the table had more than one sparse column.

- Users can deploy SQL Server Integration Services (SSIS) packages containing OData Connection Manager, which connects to a Microsoft Dynamics AX/CRM Online resource to the SSIS catalog. For more information, For details, see [OData Connection Manager](/sql/integration-services/connection-manager/odata-connection-manager).

- Configuring Always Encrypted on an existing table fails with errors on unrelated objects.

- Configuring Always Encrypted for an existing database with multiple schemas doesn't work.

- The Always Encrypted, Encrypted Column wizard fails due to the database containing views that reference system views.

- When you encrypt with Always Encrypted, errors from refreshing modules after encryption are incorrectly handled.

- *Open recent* menu doesn't show recently saved files.

- SSMS is slow when right-clicking an index for a table (over a remote (Internet) connection).

- Fixed an issue with the SQL Designer scrollbar.

- Context menu for tables momentarily stops responding.

- SSMS occasionally throws exceptions in Activity Monitor and crashes.

- SSMS crashes with the error: "The process was terminated due to an internal error in the .NET Runtime at IP 71AF8579 (71AE0000) with exit code 80131506."

## More downloads

For a list of all SQL Server Management Studio downloads, search the [Microsoft Download Center](https://www.microsoft.com/download/search.aspx?q=sql%20server%20management%20studio&p=0&r=10&t=&s=Relevancy~Descending).

For the latest release of SQL Server Management Studio, see [Install SQL Server Management Studio](install/install.md).

## Related content

- [Install SQL Server Management Studio](install/install.md)
- [Download Azure Data Studio](/azure-data-studio/download-azure-data-studio)
- [Azure Data Studio release notes](/azure-data-studio/release-notes-azure-data-studio)
