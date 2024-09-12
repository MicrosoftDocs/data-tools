---
title: Database Migration Service Pack for Oracle
description: An Azure SQL migration extension pack that comprises other Oracle extension for assessing and code conversion.
author: nilabjaball
ms.author: niball
ms.reviewer: randolphwest
ms.date: 11/22/2023
ms.service: azure-data-studio
ms.subservice: migration-extension
ms.topic: conceptual
ms.custom: sql-migration-content
---

# Database Migration Service Pack for Oracle

> [!NOTE]  
> This extension will be retired on **December 15, 2024**. We will stop supporting this tool for any issues that arise, and will not issue any bug fixes or further updates.

The Database Migration Service Pack for Oracle is a comprehensive extension pack to facilitate the seamless migration of Oracle databases to Azure SQL Database, Azure SQL Managed Instance, and SQL Server on Azure Virtual Machines. This service pack comprises two essential extensions:

- Database Assessment for Oracle
- Database Schema Conversion Toolkit

The extension pack installs all relevant [!INCLUDE [azure-data-studio-short](../includes/azure-data-studio-short.md)] extensions and their dependencies.

## Database Assessment for Oracle

The [Database Migration Assessment for Oracle extension](database-migration-assessment-for-oracle-extension.md) is a critical component of the Database Migration Service Pack, focusing on two key aspects: *workload assessment* and *code assessment*.

### Workload assessment

Workload assessment involves analyzing the existing Oracle database workload to understand its performance characteristics and resource utilization. The Database Assessment for Oracle provides tools to gather and evaluate metrics related to query performance, transaction throughput, and system resource usage.

#### Workload assessment features

- Static and configuration assessment
- Performance data collection and analysis for target sizing
- Feature assessment

### Code assessment

Code assessment is a crucial step in preparing for database migration. The Database Assessment for Oracle examines the existing Oracle database codebase, identifying potential issues and incompatibilities that can arise during migration.

#### Code assessment features

- Code compatibility checks
- Migration readiness reports

## Database Schema Conversion Toolkit

The [Database Schema Conversion Toolkit (DSCT)](dsct/database-schema-conversion-toolkit.md) is a powerful tool designed to perform detailed code conversion and generate a SQL project that can be published to the target database management system (DBMS).

### Detailed code conversion

The toolkit analyzes the Oracle database schema and converts the schema objects, such as tables, indexes, and stored procedures, into the syntax compatible with the target DBMS. It ensures a high degree of accuracy in code translation, minimizing manual intervention.

#### Supported schema objects

- Tables
- Indexes
- Views
- Stored procedures
- Triggers
- Packages

### SQL project creation

The Database Schema Conversion Toolkit creates a SQL project encapsulating the converted code, making it easy to manage and deploy on the target DBMS. The project includes all the necessary scripts and configurations required for a successful migration.

#### SQL project components

- SQL scripts
- Configuration files
- Migration documentation

You can either install individual extensions for assessment and conversion, or do a one-click install of the Database Migration Service Pack for Oracle, and get started with the Oracle Migration to Azure SQL.

## Related content

- [Extension for Oracle (Preview)](extension-for-oracle.md)
- [Quickstart: Use Azure Data Studio to connect and explore Oracle databases](../quickstart-oracle.md)
