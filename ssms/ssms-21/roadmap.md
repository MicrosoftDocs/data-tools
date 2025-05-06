---
title: Roadmap for SQL Server Management Studio 21 Preview
description: Roadmap for SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: maghan, randolphwest
ms.date: 04/16/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
---
# SQL Server Management Studio 21 Preview product roadmap

[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] continues to be an integrated environment for managing any SQL infrastructure, which can be used to access, configure, manage, administer, and develop all components of SQL Server, Azure SQL Database, Azure SQL Managed Instance, SQL Server on Azure VM, and Azure Synapse Analytics. SSMS provides a single comprehensive application that combines a broad group of graphical tools with a rich script editor to provide access to SQL Server and Azure SQL databases for data professionals, database administrators, and database developers of all skill levels.

This roadmap describes the work planned for subsequent [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] releases, and encompasses themes including modernization, AI, Git integration, and general improvements across the application.

## Modernization

[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] introduces updates that significantly enhance the user experience and functionality. These improvements include updating to Visual Studio 2022 which brings support for 64-bit, installation using the Visual Studio Installer, support for automatic updates, and initial support for dark theme. Full support for dark theme across all dialogs will take numerous releases to fully implement. Initial support exists for dialogs that are most frequently accessed by users, including Object Explorer, Query Editor, Results pane, and Template Explorer. If you plan to use dark theme, and would like to provide feedback on the dialogs that you use the most, please go to the [SSMS 21 dark theme support](https://feedback.azure.com/d365community/idea/35006f2b-73a0-ef11-8a69-7c1e520a48ea) feedback item and add a comment.

## AI with Copilot

AI with Copilot in SSMS brings a sidecar chat associated with the Query Editor window from which it launches. Copilot has both server and database context, based on the connection. This feature allows users to ask SQL questions and get assistance writing, editing, and fixing Transact-SQL using natural language prompts. Copilot in SSMS will be an optional installation, available as an extension. Initially, Copilot in SSMS is only available in preview.

## Extensibility and personalization

Extensibility in [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] starts with parity of what is available in the current release of SSMS. Third-party extensions [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] can be installed manually from an exe or msi file. Existing extensions might not work with SSMS 21 until they're modified to have 64-bit support, and might require additional updates. Over time, we plan to provide full support for extensions, including the ability to browse extensions from within SSMS, a presence in the Visual Studio marketplace, and support of the VSIX Installer.

## Git tooling

Git integration returns to SSMS, allowing administrators and database developers to manage script repositories. This integration supports common Git operations such as cloning, committing, pushing, and pulling changes directly from SSMS. You can create internal GitHub repos with better guardrails to ensure security, providing a seamless and secure way to manage your codebase.

## Performance and productivity

[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] also includes performance and productivity improvements:

- A [new connection experience](../quickstarts/ssms-connect-query-sql-server.md?tabs=modern#connect-to-a-sql-server-instance) that simplifies the process of connecting to SQL Server instances and Azure SQL databases.
- Start time improvements, reducing the time it takes to launch SSMS and get to work.

## Query Editor

The Query Editor experience is enhanced with new features, including support for vertical tabs, sorting of tabs, setting minimum and maximum widths for tabs, and coloring tabs based on project or file extension.

## Security

Azure support continues to improve with the adoption of the Azure authentication methods used by Visual Studio, ultimately rolling out to all Azure integration dialogs. With [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)], you can create logins and users for Azure SQL Database with the UI. New security features in [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] include an Always Encrypted Assessment wizard, to help determine which columns in a database are candidates for encryption.
