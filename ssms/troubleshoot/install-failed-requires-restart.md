---
title: SSMS Setup Failed or Requires Restart
description: Troubleshooting SSMS installation problems
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: install-set-up-deploy
ms.collection:
  - data-tools
ms.custom:
  - intro-installation
---

# SQL Server Management Studio (SSMS) setup failed or requires restarting the machine

Infrequently, users encounter SSMS installation problems, and common error messages include:

- `Failed to install MSI package`
- `Microsoft ODBC Driver 17 for SQL Server: A previous installation required a reboot of the machine for changes to take effect`
- `Fatal error during installation (0x80070643)`

## Suggested resolution

Following these steps to uninstall **Microsoft ODBC Driver 17 for SQL Server** before beginning the SSMS installation commonly allows the setup to succeed if it fails with one of the previous or similar error messages.

1. Close any related applications, including SSMS, Visual Studio, or SQL Server Profiler.
1. Go to **Control Panel** > **Programs and Features**.
1. Locate the entry for "Microsoft ODBC Driver 17 for SQL Server" and uninstall. This step might require a restart.
1. Begin the SSMS installation of the [latest version](../install/install.md).

[!INCLUDE [get-help-sql-tools](../includes/paragraph-content/get-help-sql-tools.md)]

## Related content

- [Install SQL Server Management Studio](../install/install.md)
