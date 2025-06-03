---
title: Using Templates in SQL Server Management Studio
description: "Learn about the prebuilt Transact-SQL (T-SQL) templates that are available in SQL Server Management Studio (SSMS)."
author: MashaMSFT
ms.author: mathoma
ms.date: 03/13/2018
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

* [Install SQL Server Management Studio](../install/install.md).
* Install [SQL Server 2017 Developer Edition](https://www.microsoft.com/sql-server/sql-server-downloads).

## Use Template Browser

In this section, you learn how to locate and use Template Browser.

1. Open SQL Server Management Studio.

2. In the **View** menu, select **Template Browser** (Ctrl+Alt+T):

    ![Open Template Browser](media/templates-ssms/templatebrowser.png)

    You can see recently used templates at the bottom of the template browser.

3. Expand the node you're interested in. Right-click the template, and then select **Open**:

    ![Open a template](media/templates-ssms/opentemplate.png)

    You can also double-click the template name to open it.

4. A new query window opens. The T-SQL script is already populated.

5. Modify the template to suit your needs, and then select **Execute** to run the query:

    ![Create a DB template](media/templates-ssms/createdbtemplate.png)

## Edit an existing template

You can also edit existing templates in Template Browser.  

1. In Template Browser, go to the template you want to work with.

2. Right-click the template, and then select **Edit**:

    ![Edit  a template](media/templates-ssms/edittemplate.png)

3. In the query window that opens, make the changes that you want to make.

4. To save the template, select **File** > **Save** (Ctrl+S).

5. Close the query window.

6. Reopen the template. Your edits should appear.

## Locate templates on disk

When a template is open, you can locate the templates that are on disk.

1. In Template Browser, select a template, and then select **Edit**.

2. Right-click **Query Title**, and then select **Open Containing Folder**. 
The explorer should open where the templates are stored on disk: 

   ![Templates on disk](media/templates-ssms/templatesondisk.png)
  
## Create a new template

You can also create a new template in Template Browser. The following steps show you how to create a new folder, and then create a new template in that folder. You can also use these steps to create a custom template in an existing folder. 

1. Open Template Browser.

2. Right-click **SQL Server Templates**, and then select **New** > **Folder**.

3. Name this folder **Custom Templates**:

    ![Create a custom templates folder](media/templates-ssms/creatingcustomtemplate.png)

4. Right-click the newly created Custom Templates folder, and then select **New** > **Template**. Enter a name for your template:

    ![Create a custom template](media/templates-ssms/createnewtemplate.png)

5. Right-click the template you created, and then select **Edit**. The New Query Window opens.

6. Enter the T-SQL text that you want to save.

7. In the **File** menu, select **Save**.

8. Close the existing query window, and then open your new custom template.

## Next steps

The best way to get acquainted with SSMS is through hands-on practice. These *tutorial* and *how-to* articles help you with various features available within SSMS.  These articles teach you how to manage the components of SSMS and how to find the features that you use regularly.

* [Connect to and query an instance](../quickstarts/ssms-connect-query-sql-server.md)
* [Scripting](../tutorials/scripting-ssms.md)
* [SSMS Configuration](../tutorials/ssms-configuration.md)
* [Additional Tips and Tricks for using SSMS](../tutorials/ssms-tricks.md)
