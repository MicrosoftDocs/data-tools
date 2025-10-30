---
author: mbarickman
ms.author: mbarickman
ms.date: 10/29/2025
ms.service: sql-server-management-studio
ms.topic: include
---
SQL Server Management Studio (SSMS) caches Microsoft Entra ID tokens briefly. When a user is added to a Microsoft Entra ID group and immediately tries to authenticate from SSMS, the following error message is thrown:

```output
Login failed for user '<token-identified principal>'.
(Microsoft SQL Server, Error: 18456)
```

If you recently obtained access to a server, you can clear the Microsoft Entra ID token cache from **Help** > **Clear Entra ID Token Cache**.

:::image type="content" source="../media/refresh-entra-id-cache/help-clear-entra-id-token-cache.png" alt-text="Screenshot of the Help menu, with the Clear Entra ID Token Cache option highlighted in red.":::

The following dialog describes why this option is useful if you recently received access to a server and require re-authentication.

:::image type="content" source="../media/refresh-entra-id-cache/clear-entra-id-token-cache-confirmation.png" alt-text="Screenshot of dialog box requesting confirmation to clear the Microsoft Entra ID user token cache.":::
