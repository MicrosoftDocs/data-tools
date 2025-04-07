---
title: Enable the Table Space Usage Sample Insight Widget
description: This tutorial demonstrates how to enable the table space usage sample insight widget on the Azure Data Studio database dashboard.
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest, maghan
ms.date: 02/06/2025
ms.service: azure-data-studio
ms.topic: "tutorial"
ms.collection:
  - data-tools
ms.custom:
  - updatefrequency5
---

# Tutorial: Enable the table space usage sample insight widget using Azure Data Studio

[!INCLUDE [azure-data-studio-deprecation](includes/azure-data-studio-deprecation.md)]

This tutorial demonstrates how to enable an insight widget on the database dashboard, providing an at-a-glance view about the space usage for all tables in a database. During this tutorial, you learn how to:

> [!div class="checklist"]
> * Quickly turn on an insight widget using a built-in insight widget example
> * View the details of table space usage
> * Filter data and view label detail on an insight chart

## Prerequisites

This tutorial requires the SQL Server or Azure SQL Database *TutorialDB*. To create the *TutorialDB* database, complete one of the following quickstarts:

* [Connect and query SQL Server using [!INCLUDE [azure-data-studio-short](includes/azure-data-studio-short.md)]](quickstart-sql-server.md)
* [Connect and query Azure SQL Database using [!INCLUDE [azure-data-studio-short](includes/azure-data-studio-short.md)]](quickstart-sql-database.md)

## Turn on a management insight on Azure Data Studio's database dashboard

Azure Data Studio has a built-in sample widget to monitor the space used by tables in a database.

1. Open *User Settings* by pressing **Ctrl+Shift+P** to open the *Command Palette*.

2. Type *settings* in the search box and select **Preferences: Open User Settings**.

3. Type *dashboard* in Settings Search input box and locate **dashboard.database.widgets**.

4. To customize the **dashboard.database.widgets** settings, you need to edit the **dashboard.database.widgets** entry in the **USER SETTINGS** section.

   ![Screenshot showing the USER SETTINGS section with the Dashboard > Database Widgets section called out.](media/tutorial-table-space-sql-server/search-settings.png)

   If there is no **dashboard.database.widgets** in the **USER SETTINGS** section, hover over the **dashboard.database.widgets** text in the DEFAULT SETTINGS column and click the *gear* icon that appears to the left of the text and click **Copy Setting as JSON**. If the pop-up says **Replace in Settings**, don't click it! Go to the **USER SETTINGS** column to the right and locate the **dashboard.database.widgets** section and advance to the next step.

5. In the **dashboard.database.widgets** section, add the following lines:

   ```json
        {
            "name": "Space Used by Tables",
            "gridItemConfig": {
                "sizex": 2,
                "sizey": 1
            },
            "widget": {
                "table-space-db-insight": null
            }
        },
    ```

   The **dashboard.database.widgets** section should look similar to the following image:

    ![Screenshot of the settings.json file with the first object of the dashboard.database.widgets array.](./media/tutorial-table-space-sql-server/insight-table-space.png)

6. Press **Ctrl+S** to save the settings.

7. Open database dashboard by right-clicking **TutorialDB** and click **Manage**.

8. View the *table space* insight widget as shown in the following image:

   ![Widget](./media/tutorial-table-space-sql-server/insight-table-space-result.png)

## Working with the insight chart

Azure Data Studio's insight chart provides filtering and mouse-hover details. To try out the following steps:

1. Click and toggle the *row_count* legend on the chart. Azure Data Studio shows and hides data series as you toggle a legend on or off.

2. Hover the mouse pointer over the chart. Azure Data Studio shows more information about the data series label and its value as shown in the following screenshot.

   ![chart toggle and legend](./media/tutorial-table-space-sql-server/insight-table-space-toggle.png)

## Next steps

In this tutorial, you learned how to:
> [!div class="checklist"]
> * Quickly turn on an insight widget using a built-in insight widget sample.
> * View the details of table space usage.
> * Filter data and view label detail on an insight chart

To learn how to build a custom insight widget, complete the next tutorial:

> [!div class="nextstepaction"]
> [Build a custom insight widget](tutorial-build-custom-insight-sql-server.md)
