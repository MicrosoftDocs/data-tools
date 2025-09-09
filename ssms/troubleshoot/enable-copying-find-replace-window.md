---
title: Enable Copying from Find and Replace Window
description: Use a workaround to enable copying from the Find and Replace window in SQL Server Management Studio.
author: dzsquared
ms.author: drskwier
ms.reviewer: maghan, randolphwest
ms.date: 09/09/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---

# Workaround to enable copying from Find and Replace window

[!INCLUDE [Applies to](../includes/appliesto-ss-asdb-asdw-xxx-md.md)]

For SQL Server Management Studio (SSMS) 21 and earlier versions, a workaround is required to enable copying from the Find and Replace window. If you can't copy from the Find and Replace window in SSMS, follow the [workaround](#workaround). This problem does not exist in SSMS 22 Preview and later versions.

## Error message

When you attempt to copy text from the Find and Replace window in SQL Server Management Studio, you might get the following error message.

```output
Unsaved documents cannot be cut or copied to the clipboard from the Miscellaneous Files project. You must save the unsaved document(s) before cutting or copying them.
```

## Workaround

To enable copying text from the Find and Replace window, follow these steps:

1. In the **Tools** menu, open **Options**.

1. Under **Environment** > **Documents**, uncheck the item for **Show Miscellaneous files in Solution Explorer**.

1. Close and reopen SQL Server Management Studio.
