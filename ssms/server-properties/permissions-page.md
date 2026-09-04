---
title: Server Properties (Permissions Page)
titleSuffix: SQL Server Management Studio
description: View and modify server-level permissions for logins and roles by using the Permissions page of the Server Properties window.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mbarickman
ms.date: 09/03/2026
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.serverproperties.permissions.f1"
ai-usage: ai-assisted
---
# Server Properties (Permissions page)

[!INCLUDE [sql-asdbmi](../includes/applies-to-version/sql-asdbmi.md)]

Use this page to view or modify server-level permissions for logins and roles on the [!INCLUDE [ssdenoversion-md](../includes/ssdenoversion-md.md)] instance.

## Logins or roles

The top section lists logins and server roles on the instance. Select a login or role to view its permissions in the lower section.

| Column | Description |
| --- | --- |
| **Name** | The name of the login or server role. |
| **Type** | The type of principal: **Login** or **Server role**. |

Select **Search** to find and add logins or roles to the list.

## Explicit permissions

The **Explicit** tab shows permissions that you directly grant or deny to the selected login or role.

| Column | Description |
| --- | --- |
| **Permission** | The name of the server-level permission, such as **Alter any database** or **Connect SQL**. |
| **Grantor** | The principal that granted the permission. |
| **Grant** | Select to grant this permission to the login or role. |
| **With Grant** | Select to grant this permission with the ability for the grantee to grant it to other principals. |
| **Deny** | Select to deny this permission to the login or role. |

## Effective permissions

The **Effective** tab shows the combined set of server-level permissions that are in effect for the selected login or role. It has a single **Permission** column, and it lists the permission names in uppercase. This tab is read-only, and it reflects permissions that are inherited from role memberships in addition to any explicit grants and denies.

## Related content

- [Server-level roles](/sql/relational-databases/security/authentication-access/server-level-roles)
- [Server Properties window in SQL Server Management Studio](server-properties-window.md)
