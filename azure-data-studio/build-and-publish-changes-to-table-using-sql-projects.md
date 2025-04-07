---
title: Building and Publishing Changes to Database Tables Using the SQL Database Projects Extension
description: How to use SQL Database Projects to build and publish changes to a database table in Azure Data Studio
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest, maghan
ms.date: 02/06/2025
ms.service: azure-data-studio
ms.topic: tutorial
ms.collection:
  - data-tools
---

# Building and Deploying Changes to tables using the SQL Database Projects extension

[!INCLUDE [azure-data-studio-deprecation](includes/azure-data-studio-deprecation.md)]

[!INCLUDE [sql-asdb-asmi](includes/applies-to-version/sql-asdb-asmi.md)]

With the help of the SQL Database Projects extension, SQL projects (including tables, views, and stored procedures) can be edited without the need to be connected to a server instance in Azure Data Studio. The tutorial below shows you how to:

1. Create a SQL Database Project of the [!INCLUDE [sssampledbobject-md](includes/sssampledbobject-md.md)] database.

2. Make and deploy changes to a table in the [!INCLUDE [sssampledbobject-md](includes/sssampledbobject-md.md)] database using SQL Database Projects and confirming this change in the locally connected server instance where this database resides.

[!INCLUDE [article-uses-adventureworks](includes/article-uses-adventureworks.md)]

You will also need to have the SQL Database Projects extension installed. Refer to the [SQL Database Projects documentation](extensions/sql-database-project-extension.md) to learn more about this extension.

## Create a SQL Database Project

1. Navigate to the [!INCLUDE [sssampledbobject-md](includes/sssampledbobject-md.md)] database object located in the object explorer, right-click on it and select **Create Project from Database**:

    :::image type="content" source="media/table-designer-azure-data-studio/table-designer-show-how-to-create-project-from-database.png" alt-text="Screenshot of the object explorer in Azure Data Studio showing how to create a project from a database object.":::

2. Select the location in which you want to store your **Target project** in and name the file containing the project to your preference. You can also configure the **Folder structure** settings to any of the provided options in the drop-down. In this tutorial, we will use the ***Schema/Object*** type folder structure. When done, select **Create**. When this project has been extracted, you will see a **Extract project files succeeded** message.

3. From the Azure Data Studio sidebar menu, select the **Database Projects** icon to open the SQL Database Projects extension. Navigate to the database project folder you created. Then, in the **Person** schema folder in this project, navigate to the **Tables** folder, and expand the drop-down of this folder. Right-click and open any of the tables in the designer mode to open the table design of this table. In this example, we work on the ***Person.sql*** table.

    :::image type="content" source="media/table-designer-azure-data-studio/table-designer-show-how-to-open-table-in-sql-projects.png" alt-text="Screenshot of Azure Data Studio showing how to open a table in offline mode using the SQL database projects extension.":::

    > [!NOTE]
    > Please note that the project file's location could vary depending on the folder structure defined in Step 2 above.

## Deploy Changes to the Database from the Project

1. The original table shows the table design of the ***Person*** table with thirteen (13) column names, starting from ***BusinessEntityID*** and ending with ***ModifiedDate***.
    Add another column named ***Citizenship*** of type nvarchar(50) and publish this change:
        :::image type="content" source="media/table-designer-azure-data-studio/table-designer-publish-changes-to-sql-project.png" alt-text="Screenshot of Azure Data Studio showing how to publish changes SQL Database Projects.":::

2. From the file menu in the Database Projects, right-click on the project root node in which your project resides, and select **Build** to build this project. You should see a success or error message in the output terminal for a successful or failed build. When finished, right-click this same folder and select **Publish** to publish this project to the [!INCLUDE [sssampledbobject-md](includes/sssampledbobject-md.md)] database in your local host server connection.

    :::image type="content" source="media/table-designer-azure-data-studio/table-designer-show-how-to-build-and-publish-changes-to-sql-project.png" alt-text="Screenshot of Azure Data Studio showing how to build and publish changes SQL Database Projects.":::

    > [!NOTE]
    > Please note that you must be connected to your local host for this step. This can be done by clicking the plug icon in **Publish Project** dialog box.

3. Exit the SQL Database Projects view. Then, go to the object explorer in your server connection and navigate to the **Tables** folder of [!INCLUDE [sssampledbobject-md](includes/sssampledbobject-md.md)] database. Open the table design of the table you made changes to and confirm the change made. In this case, we added a new column, ***Citizenship*** to the ***Person.Person*** table:

    :::image type="content" source="media/table-designer-azure-data-studio/table-designer-confirm-changes-made-to-project-in-local-host.png" alt-text="Screenshot of Azure Data Studio showing the changes made to the table in the local host connection.":::

## Next steps

- [Download Azure Data Studio](./download-azure-data-studio.md)
