---
title: "Use the Query Hint Recommendation Tool (Preview)"
titleSuffix: SQL Server Management Studio
description: Learn how to use the Query Hint Recommendation tool.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 01/16/2026
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to learn how to use the Query Hint Recommendation tool so that I can improve query performance.
---
# Use the Query Hint Recommendation tool (Preview)

The Query Hint Recommendation tool helps users of SQL Server Management Studio (SSMS) explore [query hints](/sql/t-sql/queries/hints-transact-sql-query) to improve query performance.

> [!NOTE]  
> Query hints can be helpful in scenarios where you can't immediately change application code, or need to temporarily mitigate poor performance of a query. Once you identify and address the root cause of the performance problem, remove the query hint.

Regardless of your role, the Query Hint Recommendation tool can help you become more efficient in finding one or more query hints to improve the performance of a query.

## Get started

The Query Hint Recommendation tool works with a single query in the active query editor window. It runs the query with different query hints applied.

1. Connect to a database in a query editor window.
1. Select the entire query that you want the tool to evaluate.
1. Open the Query Hint Recommendation tool by selecting **Tools** > **Query Hint Recommendation Tool**.
1. The tool window opens next to the query editor.
1. Enter the following input parameters:
   1. **Maximum tuning time**: The maximum amount of total time, in seconds, the tool spends trying to find a beneficial query hint. The default is 300 seconds (five minutes).
      1. **Minimum improvement percentage**: The minimum percentage improvement in query performance that you're willing to accept. This parameter helps filter out less effective hints and uses the allocated time on hints that can deliver significant improvement. Specify this parameter as a percentage. The default is 50%, or at least a 2x improvement in elapsed time.
1. Select **Start** to begin running the query with different hints.

:::image type="content" source="media/hint-tool.png" alt-text="Screenshot of Query Hint Recommendation Tool window." lightbox="media/hint-tool.png":::

| Key | Description |
| --- | --- |
| 1 | Title bar |
| 2 | Tool window controls, to pin or close the window |
| 3 | Required input parameters (maximum tuning time and minimum improvement percentage) |
| 4 | Folder selection button |
| 5 | Start button (initiate query hint exploration) |
| 6 | Advanced options to configure the space of query hints |
| 7 | Hint recommendation summary |
| 8 | Chart to visualize query duration improvement |
| 9 | Toggle to show or hide the chart |
| 10 | Tabular view of explored query hints |

### Log file

The Query Hint Recommendation tool creates a log file that contains detailed information about the evaluation process, including errors, and can be useful for troubleshooting. The log file is stored in your `%TEMP%` folder by default. You can change the location by using the folder selection button in the tool window.

## Visualizing the tuning process

The Query Hint Recommendation tool includes a chart to provide a visual representation of the tuning process. This chart shows you the performance impact of different query hints in real-time. The chart includes a baseline performance measurement and then overlays the performance of increasingly helpful hints as they're found.

## Tabular view of explored hints

The Query Hint Recommendation tool also provides a tabular view of all explored hints. This view includes key information such as the hint text, its performance impact, and whether it was skipped to save tuning time. Use this view  to quickly assess the effectiveness of different hints, and make an informed decision about which hint to apply.

| Column | Description |
| --- | --- |
| Timestamp | The time at which the query was executed with the specified query hint. |
| Test ID | The unique identifier for the test run. |
| Elapsed Time (ms) | Query execution duration with the query hint applied, measured in milliseconds (ms). When the query isn't executed with the specific query hint, the reason for skipping the execution is included. |
| Gain % | The percentage improvement in query execution duration achieved by the query hint. |
| Hint | The query hint applied to the query. |

### Skipping query hints

The Query Hint Recommendation tool uses the following criteria to improve tuning efficiency by skipping certain hints.

| Skip Reason | Description |
| --- | --- |
| Invalid query plan | A valid query plan isn't generated when the query hint is applied to the query. |
| Skipped (No improvement expected) | Using the query hint creates an execution plan that's the same as a previously applied hint, or isn't expected to help compare to the best query hint found so far. |
| Stopped (Exceed the time limit) | Query execution is terminated because its expected duration is higher than the best plan so far. |

## Append a hint to the selected query

The Query Hint Recommendation tool enables you to easily append a hint to the currently selected query in the editor window. This option streamlines the process of applying a hint without manually modifying the query text.

1. Confirm the query is highlighted in the editor window.
1. Right-click on the query hint you want to apply.
1. Select **Append Hint to Query**.
1. The query hint is added to the query in the editor.

To persist the query hint beyond execution of the query in the editor, apply it as a Query Store hint. For more information, see [Query Store hints](/sql/relational-databases/performance/query-store-hints).

### Advanced options

The Query Hint Recommendation tool provides advanced options to customize the space of query hints. These options allow you to configure specific hints to explore, including:

- **Plan Space Hints**: Hints that control the operators and join order in the query.
- **Cardinality Model Hints**: Hints that modify the cardinality model used to estimate cardinalities in the execution plan.
- **Miscellaneous**: Other query hints, including controlling the degree of parallelism.

By default, the Query Hint Recommendation tool explores all of the predefined query hints and certain combinations of query hints. The advanced options panel allows you to customize the space of hints to be explored, such as excluding hint combinations, certain hint categories, or specific hints.

:::image type="content" source="media/hint-advanced.png" alt-text="Screenshot of Query Hint Recommended Tool advanced options." lightbox="media/hint-advanced.png":::

## Related content

- [Install the Query Hint Recommendation tool (Preview)](hint-tool-install.md)
