---
title: Server Properties (Security Page)
titleSuffix: SQL Server Management Studio
description: View and modify server authentication, login auditing, proxy account, and other security options by using the Security page of the Server Properties window.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mbarickman
ms.date: 09/03/2026
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.serverproperties.security.f1"
ai-usage: ai-assisted
---
# Server Properties (Security page)

[!INCLUDE [sql-asdbmi](../includes/applies-to-version/sql-asdbmi.md)]

Use this page to view or modify server security options.

## Server authentication

| Setting | Description |
| --- | --- |
| **Windows Authentication mode** | Uses Windows Authentication to validate attempted connections. If the `sa` account's password is blank when you change the security mode, you're prompted to enter a password for `sa`. |
| **SQL Server and Windows Authentication mode** | Uses mixed mode authentication for backward compatibility with earlier versions of the [!INCLUDE [ssdenoversion-md](../includes/ssdenoversion-md.md)]. If the `sa` account's password is blank, you're prompted to enter a password for `sa`. |

> [!IMPORTANT]  
> Windows Authentication is more secure than SQL Server Authentication. When possible, use Windows Authentication. For more information, see [Choose an authentication mode](/sql/relational-databases/security/choose-an-authentication-mode).

Changing the server authentication mode requires a restart of the service. When you change to **SQL Server and Windows Authentication mode**, the `sa` account isn't automatically enabled. To use the `sa` account, run [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) with the `ENABLE` option.

## Login auditing

| Setting | Description |
| --- | --- |
| **None** | Turns off login auditing. |
| **Failed logins only** | Audits unsuccessful logins only. |
| **Successful logins only** | Audits successful logins only. |
| **Both failed and successful logins** | Audits all login attempts. |

Changing the audit level requires restarting the service.

## Server proxy account

| Setting | Description |
| --- | --- |
| **Enable server proxy account** | Enables an account for use by `xp_cmdshell`. Proxy accounts allow for the impersonation of logins, server roles, and database roles when an operating system command runs. |
| **Proxy account** | The proxy account used. |
| **Password** | The password for the proxy account. |

> [!CAUTION]  
> The login used by the server proxy account should have the least privileges required to perform the intended work. Excessive privileges for the proxy account could allow a malicious user to compromise your system security.

## Options

### Enable Common Criteria compliance

Enables the Common Criteria compliance requirements. For more information, see [Server configuration: common criteria compliance enabled](/sql/database-engine/configure-windows/common-criteria-compliance-enabled-server-configuration-option).

### Enable C2 audit tracing

Audits all attempts to access statements and objects and records them to a file in the `\MSSQL\Data` directory for default instances of the [!INCLUDE [ssde-md](../includes/ssde-md.md)], or the `\MSSQL$<instancename>\Data` directory for named instances. For more information, see [Server configuration: c2 audit mode](/sql/database-engine/configure-windows/c2-audit-mode-server-configuration-option).

### Cross database ownership chaining

Select this option to allow the database to be the source or target of a cross-database ownership chain. For more information, see [Server configuration: cross db ownership chaining](/sql/database-engine/configure-windows/cross-db-ownership-chaining-server-configuration-option).

## Related content

- [Server Properties window in SQL Server Management Studio](server-properties-window.md)
- [Server configuration options](/sql/database-engine/configure-windows/server-configuration-options-sql-server)
