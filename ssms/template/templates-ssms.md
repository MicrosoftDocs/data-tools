---
title: Using Templates in SQL Server Management Studio
description: "Learn about the prebuilt Transact-SQL (T-SQL) templates that are available in SQL Server Management Studio (SSMS)."
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mathoma
ms.date: 09/07/2025
ms.service: sql-server-management-studio
ms.topic: tutorial
ms.collection:
  - data-tools
helpviewer_keywords:
  - "templates [SQL Server], SQL Server Management Studio"
  - "source controls [SQL Server Management Studio], tutorials"
  - "Help [SQL Server], SQL Server Management Studio"
  - "tutorials [SQL Server Management Studio]"
  - "Transact-SQL tutorials"
  - "SQL Server Management Studio [SQL Server], tutorials"
  - "scripts [SQL Server], SQL Server Management Studio"
keywords:
  - SQL Server
  - SSMS
  - SQL Server Management Studio
  - Templates
---

# Use templates in SQL Server Management Studio

This tutorial introduces you to the prebuilt Transact-SQL (T-SQL) templates that are available in SQL Server Management Studio (SSMS). In this article, you learn how to:

## Prerequisites

To complete this tutorial, you need SQL Server Management Studio and access to a SQL Server.

- [Install SQL Server Management Studio](../install/install.md).
- Install [SQL Server 2022 Developer edition](https://www.microsoft.com/sql-server/sql-server-downloads).

## Use Template Browser

In this section, you learn how to locate and use Template Browser.

1. Open SQL Server Management Studio.

1. In the **View** menu, select **Template Browser** (**Ctrl**+**Alt**+**T**):

   :::image type="content" source="media/templates-ssms/templatebrowser.png" alt-text="Screenshot of Open Template Browser.":::

   You can see recently used templates at the bottom of the template browser.

1. Expand the node you're interested in. Right-click the template, and then select **Open**:

   :::image type="content" source="media/templates-ssms/opentemplate.png" alt-text="Screenshot of Open a template.":::

   You can also double-click the template name to open it.

1. A new query window opens. The T-SQL script is already populated.

1. Modify the template to suit your needs, and then select **Execute** to run the query:

   :::image type="content" source="media/templates-ssms/createdbtemplate.png" alt-text="Screenshot of Create a DB template." lightbox="media/templates-ssms/createdbtemplate.png":::

## Edit an existing template

You can also edit existing templates in Template Browser.

1. In Template Browser, go to the template you want to work with.

1. Right-click the template, and then select **Edit**:

   :::image type="content" source="media/templates-ssms/edittemplate.png" alt-text="Screenshot of Edit a template.":::

1. In the query window that opens, make the changes that you want to make.

1. To save the template, select **File** > **Save** (**Ctrl**+**S**).

1. Close the query window.

1. Reopen the template. Your edits should appear.

## Locate templates on disk

When a template is open, you can locate the templates that are on disk.

1. In Template Browser, select a template, and then select **Edit**.

1. Right-click **Query Title**, and then select **Open Containing Folder**.

   The explorer should open where the templates are stored on disk:

   :::image type="content" source="media/templates-ssms/templatesondisk.png" alt-text="Screenshot of Templates on disk." lightbox="media/templates-ssms/templatesondisk.png":::

## Create a new template

You can also create a new template in Template Browser. The following steps show you how to create a new folder, and then create a new template in that folder. You can also use these steps to create a custom template in an existing folder.

1. Open Template Browser.

1. Right-click **SQL Server Templates**, and then select **New** > **Folder**.

1. Name this folder **Custom Templates**:

   :::image type="content" source="media/templates-ssms/creatingcustomtemplate.png" alt-text="Screenshot of Create a custom templates folder.":::

1. Right-click the newly created Custom Templates folder, and then select **New** > **Template**. Enter a name for your template:

   :::image type="content" source="media/templates-ssms/createnewtemplate.png" alt-text="Screenshot of Create a custom template.":::

1. Right-click the template you created, and then select **Edit**. The New Query Window opens.

1. Enter the T-SQL text that you want to save.

1. In the **File** menu, select **Save**.

1. Close the existing query window, and then open your new custom template.

## Related content

- [Quickstart: Connect and query a SQL Server instance using SQL Server Management Studio (SSMS)](../quickstarts/ssms-connect-query-sql-server.md)
- [Script objects in SQL Server Management Studio](../tutorials/scripting-ssms.md)
- [SQL Server Management Studio components and configuration](../tutorials/ssms-configuration.md)
- [Tips and tricks for using SQL Server Management Studio (SSMS)](../tutorials/ssms-tricks.md)
