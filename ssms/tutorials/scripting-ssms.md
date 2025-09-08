---
title: SSMS Script Objects
description: Generate Transact-SQL (T-SQL) scripts for various objects found within SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.date: 09/07/2025
ms.service: sql-server-management-studio
ms.topic: tutorial
ms.collection:
  - data-tools
helpviewer_keywords:
  - "projects [SQL Server Management Studio], tutorials"
  - "source controls [SQL Server Management Studio], tutorials"
  - "Help [SQL Server], SQL Server Management Studio"
  - "tutorials [SQL Server Management Studio]"
  - "Transact-SQL tutorials"
  - "solutions [SQL Server Management Studio], tutorials"
  - "SQL Server Management Studio [SQL Server], tutorials"
  - "scripts [SQL Server], SQL Server Management Studio"
keywords:
  - SQL Server
  - SSMS
  - SQL Server Management Studio
  - Scripts
  - Scripting
---

# Script objects in SQL Server Management Studio

This tutorial teaches you to generate Transact-SQL (T-SQL) scripts for various objects found within SQL Server Management Studio (SSMS). In this tutorial, you find examples of how to script the following objects:

> [!div class="checklist"]
> - Queries, when you perform actions within the GUI
> - Databases in two different ways (Script As and Generate Script)
> - Tables
> - Stored procedures
> - Extended events

To script any object in **Object Explorer**, right-click it and select the **Script Object As** option. This tutorial shows you the process.

## Prerequisites

To complete this tutorial, you need SQL Server Management Studio, access to a server that's running SQL Server, and an [!INCLUDE [sssampledbobject-md](../includes/sssampledbobject-md.md)] database.

- [Install SQL Server Management Studio](../install/install.md).
- Install [SQL Server Developer edition](https://www.microsoft.com/sql-server/sql-server-downloads).
- Download [AdventureWorks sample databases](https://github.com/Microsoft/sql-server-samples/releases).

Instructions for restoring databases in SSMS are here: [Restore a Database Backup Using SSMS](/sql/relational-databases/backup-restore/restore-a-database-backup-using-ssms).

## Script queries from the GUI

You can generate the associated T-SQL code for a task whenever you use the GUI in SSMS to complete it. The following examples show how to do so when you back up a database and when you shrink the transaction log. These same steps can be applied to any action that completes via the GUI.

### Script T-SQL when you back up a database

1. Connect to a server that's running SQL Server.

1. Expand the **Databases** node.

1. Right-click the database **AdventureWorks2022** > **Tasks** > **Back Up**:

   :::image type="content" source="media/scripting-ssms/backupdb.png" alt-text="Screenshot of the option to Back up a database.":::

1. Configure the backup the way you want. For this tutorial, everything is left at default. However, any changes made in the window also reflect in the script.

1. Select **Script** > **Script Action to New Query Window**:

   :::image type="content" source="media/scripting-ssms/scriptdbbackup.PNG" alt-text="Screenshot of Script database backup--script action.":::

1. Review the T-SQL populated in the query window.

   :::image type="content" source="media/scripting-ssms/dbbackupscript.PNG" alt-text="Screenshot of Script database backup--review T-SQL." lightbox="media/scripting-ssms/dbbackupscript.PNG":::

1. Select **Execute** to execute the query to back up the database via T-SQL.

### Script T-SQL when you shrink the transaction log

1. Right-click the database **AdventureWorks2022** > **Tasks** > **Shrink** > **Files**:

   :::image type="content" source="media/scripting-ssms/shrinkfiles.png" alt-text="Screenshot of Shrink files." lightbox="media/scripting-ssms/shrinkfiles.png":::

1. Select **Log** from the **File type** dropdown list box:

   :::image type="content" source="media/scripting-ssms/shrinktlog.png" alt-text="Screenshot of Shrink transaction log.":::

1. Select **Script** and **Script Action to Clipboard**:

   :::image type="content" source="media/scripting-ssms/scriptactiontoclipboard.png" alt-text="Screenshot of Script to clipboard.":::

1. Open a **New Query** window and paste. (Right-click in the window. Then select **Paste**.)

   :::image type="content" source="media/scripting-ssms/paste.png" alt-text="Screenshot of Paste script.":::

1. Select **Execute** to execute the query and shrink the transaction log.

## Script databases

The following section teaches you to script out the database by using the **Script As** and **Generate Scripts** options. The **Script As** option re-creates the database and its configuration options. You can script both the schema and the data by using the **Generate Scripts** option. In this section, you create two new databases. You use the **Script As** option to create *AdventureWorks2022a*. You use the **Generate Scripts** option to create *AdventureWorks2022b*.

### Script a database by using the Script option

1. Connect to a server that's running SQL Server.

1. Expand the **Databases** node.

1. Right-click the database **AdventureWorks2022** > **Script Database As** > **Create To** > **New Query Editor Window**:

   :::image type="content" source="media/scripting-ssms/scriptdb.png" alt-text="Screenshot of Script database." lightbox="media/scripting-ssms/scriptdb.png":::

1. Review the database creation query in the window:

   :::image type="content" source="media/scripting-ssms/scriptedoutdb.png" alt-text="Screenshot of Scripted-out database." lightbox="media/scripting-ssms/scriptedoutdb.png":::

   This option scripts out only the database configuration options.

1. On your keyboard, select Ctrl+F to open the **Find** dialog box. Select the down arrow to open the **Replace** option. On the top **Find** line, type AdventureWorks2022, and on the bottom **Replace** line, type AdventureWorks2022a.

1. Select **Replace All** to replace all instances of *AdventureWorks2022* with *AdventureWorks2022a*.

   :::image type="content" source="media/scripting-ssms/findandreplace.png" alt-text="Screenshot of Find and replace." lightbox="media/scripting-ssms/findandreplace.png":::

1. Select **Execute** to execute the query and create your new AdventureWorks2022a database.

### Script a database by using the Generate Scripts option

1. Connect to a server that's running SQL Server.

1. Expand the **Databases** node.

1. Right-click **AdventureWorks2022** > **Tasks** > **Generate Scripts**:

   :::image type="content" source="media/scripting-ssms/generatescriptsfordb.png" alt-text="Screenshot of Generate scripts for databases.":::

1. The **Introduction** page opens. Select **Next** to open the **Chose Objects** page. You can select the entire database or specific objects in the database. Select **Script entire database and all database objects**.

   :::image type="content" source="media/scripting-ssms/scriptobjects.png" alt-text="Screenshot of Generate scripts for objects.":::

1. Select **Next** to open the **Set Scripting Options** page. Here you can configure where to save the script and some additional advanced options.

   a. Select **Save to new query window**.

   b. Select **Advanced** and make sure these options are set:

   - **Script Statistics** set to *Script Statistics*.
   - **Types of data to script** set to *Schema only*.
   - **Script Indexes** set to *True*.

   :::image type="content" source="media/scripting-ssms/advancedscripts.png" alt-text="Screenshot of Script objects." lightbox="media/scripting-ssms/advancedscripts.png":::

   > [!NOTE]  
   > You can script the data for the database when you select *Schema and data* for the **Types of data to script** option. However, this isn't ideal with large databases. It can take more memory than SSMS can allocate. This limitation is okay for small databases. If you want to move data for a larger database, use the [Import and Export Data with the SQL Server Import and Export Wizard](/sql/integration-services/import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard).

1. Select **OK**, and then select **Next**.

1. Select **Next** on the **Summary**. Then select **Next** again to generate the script in a **New Query** window.

1. On your keyboard, open the **Find** dialog box (Ctrl+F). Select the down arrow to open the **Replace** option. On the top **Find** line, enter *AdventureWorks2022*. On the bottom **Replace** line, enter *AdventureWorks2022b*.

1. Select **Replace All** to replace all instances of *AdventureWorks2022* with *AdventureWorks2022b*.

   :::image type="content" source="media/scripting-ssms/adventureworks2016b.png" alt-text="Screenshot of AdventureWorks 2016." lightbox="media/scripting-ssms/adventureworks2016b.png":::

1. Select **Execute** to execute the query and create your new AdventureWorks2022b database.

## Script tables

This section covers how to script out tables from your database. Use this option to either create the table or drop and create the table. You can also use this option to script the T-SQL associated with modifying the table. An example is to insert into it or update to it. In this section, you drop a table and then re-create it.

1. Connect to a server that's running SQL Server.

1. Expand your **Databases** node.

1. Expand your **AdventureWorks2022** database node.

1. Expand your **Tables** node.

1. Right-click **dbo.ErrorLog** > **Script Table as** > **DROP And CREATE To** > **New Query Editor Window**:

   :::image type="content" source="media/scripting-ssms/scripttable.png" alt-text="Screenshot of Script table.":::

1. Select **Execute** to execute the query. This action drops the `Errorlog` table and re-creates it.

   > [!NOTE]  
   > The `Errorlog` table is empty by default in the [!INCLUDE [sssampledbobject-md](../includes/sssampledbobject-md.md)] database. So you're not losing any data by dropping the table. However, following these steps on a table with data causes data loss.

## Script stored procedures

In this section, you learn how to drop and create a stored procedure.

1. Connect to a server that's running SQL Server.

1. Expand your **Databases** node.

1. Expand your **Programmability** node.

1. Expand your **Stored Procedure** node.

1. Right-click the stored procedure **dbo.uspGetBillOfMaterials** > **Script Stored Procedure As** > **DROP And CREATE To** > **New Query Editor Window**:

   :::image type="content" source="media/scripting-ssms/script-stored-procedure.png" alt-text="Screenshot of Script stored procedures." lightbox="media/scripting-ssms/script-stored-procedure.png":::

## Script extended events

This section covers how to script out [extended events](/sql/relational-databases/extended-events/extended-events).

1. Connect to a server that's running SQL Server.

1. Expand your **Management** node.

1. Expand your **Extended Events** node.

1. Expand your **Sessions** node.

1. Right-click the extended session you're interested in > **Script Session As** > **CREATE To** > **New Query Editor Window**:

   :::image type="content" source="media/scripting-ssms/scriptxevents.png" alt-text="Screenshot of Extended New Query Editor Window session.":::

1. In the **New Query Editor Window**, modify the new name of the session from *system_health* to *system_health2*. Select **Execute** to execute the query.

1. Right-click **Sessions** in **Object Explorer**. Select **Refresh** to see your new extended event session. The green icon next to the session indicates the session is running. The red icon indicates the session is stopped.

   :::image type="content" source="media/scripting-ssms/newxevent.png" alt-text="Screenshot of New extended event session." lightbox="media/scripting-ssms/newxevent.png":::

   > [!NOTE]  
   > You can start the session by right-clicking it and selecting **Start**. However, this is a copy of the already running **system_health** session, so you can skip this step. You can delete the copy of the extended event session: right-click it and select **Delete**.

## Related content

- [Quickstart: Connect and query a SQL Server instance using SQL Server Management Studio (SSMS)](../quickstarts/ssms-connect-query-sql-server.md)
- [Use templates in SQL Server Management Studio](../template/templates-ssms.md)
- [SQL Server Management Studio components and configuration](ssms-configuration.md)
- [Tips and tricks for using SQL Server Management Studio (SSMS)](ssms-tricks.md)
