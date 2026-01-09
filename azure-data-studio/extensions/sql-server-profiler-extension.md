---
title: SQL Server Profiler Extension
description: Learn how to install and use the SQL Server Profiler extension. An easy-to-use SQL Server tracing solution similar to the SQL Server Management (SSMS) Profiler.
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest, maghan
ms.date: 02/06/2025
ms.service: azure-data-studio
ms.topic: get-started
ms.collection:
  - data-tools
ms.custom: sfi-image-nochange
---

# SQL Server Profiler extension (Preview)

[!INCLUDE [azure-data-studio-deprecation](../includes/azure-data-studio-deprecation.md)]

The SQL Server Profiler extension (preview) provides a simple SQL Server tracing solution similar to [SQL Server Management Studio (SSMS) Profiler](/sql/tools/sql-server-profiler/sql-server-profiler) except built using [Extended Events](/sql/relational-databases/extended-events/extended-events). SQL Server Profiler is easy to use and has good default values for the most common tracing configurations. The UX is optimized for browsing through events and viewing the associated Transact-SQL (T-SQL) text. The SQL Server Profiler for Azure Data Studio also assumes good default values for collecting T-SQL execution activities with an easy to use UX. This extension is currently in preview.

**Common SQL Profiler use-cases:**

- Stepping through problem queries to find the cause of the problem.
- Finding and diagnosing slow-running queries.
- Capturing the series of Transact-SQL statements that lead to a problem.
- Monitoring the performance of SQL Server to tune workloads.
- Correlating performance counters to diagnose problems.
- Opening an existing XEL file for review.

## Install the SQL Server Profiler extension

1. To open the extensions manager and access the available extensions, select the extensions icon, or select **Extensions** in the **View** menu.
1. Enter *SQL Server Profiler*.
1. Select the extension and **Install** it.

    :::image type="content" source="media/sql-server-profiler-extension/profiler-extension.png" alt-text="Screenshot of Profiler Extension Manager." lightbox="media/sql-server-profiler-extension/profiler-extension.png":::

## Start Profiler

1. To start Profiler, first make a connection to a server in the Servers tab.
1. After you make a connection, type **Alt + P** to launch Profiler, or right-click on the server connection and select **Launch Profiler.**
1. Select a session template from the dropdown list. For Azure SQL DB, Standard_Azure is the only template available.
1. Edit the session name if appropriate, and select Start.
1. The session will be started automatically and you will start to see events in the viewer.
1. To stop Profiler, type **Alt + S** or use the Stop button in the toolbar.
1. The hotkey **Alt + S** is a toggle. To restart Profiler, type **Alt + S** or use the Start button in the toolbar.

 :::image type="content" source="media/sql-server-profiler-extension/view-profiler.png" alt-text="Screenshot of View profiler." lightbox="media/sql-server-profiler-extension/view-profiler.png":::

## Open a saved XEL file

1. To view a XEL file that you have saved locally, open the Command Palette using **Ctrl/CMD + Shift + P** and then type **Profiler: Open XEL File** and select the command.
1. Browse to the saved XEL file and select Open.
1. The file will open in the viewer.

## Next step

> [!div class="nextstepaction"]
> [Extended Events](/sql/relational-databases/extended-events/extended-events)
