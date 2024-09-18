---
title: Notebooks with Python Kernel in Azure Data Studio
description: This tutorial shows how you can create and run a Python notebook.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: maghan
ms.date: 09/18/2024
ms.service: azure-data-studio
ms.topic: how-to
---

# Create and run a Python notebook

[!INCLUDE [sqlserver2019](../includes/applies-to-version/sqlserver2019.md)]

This tutorial demonstrates how to create and run a notebook in Azure Data Studio using the Python kernel.

## Prerequisites

- [Azure Data Studio installed](../download-azure-data-studio.md)

## Create a notebook

The following steps show how to create a notebook file in Azure Data Studio:

1. Open Azure Data Studio. If you're prompted to connect to a SQL Server, you might connect or select **Cancel**.

1. Select **New Notebook** in the **File** menu.

1. Select **Python 3** for the **Kernel**. **Attach to** is set to "localhost".

   :::image type="content" source="media/notebooks-python-kernel/set-kernel-and-attach-to-python.png" alt-text="Screenshot of Set Kernel.":::

You can save the notebook using the **Save** or **Save as...** command from the **File** menu.

To open a notebook, you can use the **Open file...** command in the **File** menu, select **Open file** on the **Welcome** page, or use the **File: Open** command from the command palette.

## Change the Python kernel

The first time you connect to the Python kernel in a notebook, the **Configure Python for Notebooks** page is displayed. You can select either:

- **New Python installation** to install a new copy of Python for Azure Data Studio, or
- **Use existing Python installation** to specify the path to an existing Python installation for Azure Data Studio to use

To view the location and version of the active Python kernel, create a code cell and run the following Python commands:

```cmd
import os
import sys
print(sys.version_info)
print(os.path.dirname(sys.executable))
```

To connect to a different installation of Python:

1. From the **File** menu, select **Preferences** and then **Settings**.
1. Scroll to **Notebook configuration** under **Extensions**.
1. Under **Use Existing Python**, uncheck the option "Local path to a preexisting python installation used by Notebooks."
1. Restart Azure Data Studio.

When Azure Data Studio starts and you connect to the Python kernel, the **Configure Python for Notebooks** page is displayed, You can choose to create a new Python installation or specify a path to an existing installation.

## Run a code cell

You can create cells containing SQL code that you can run in place by selecting the **Run cell** button (the round black arrow) to the left of the cell. The results are shown in the notebook after the cell finishes running.

For example:

1. Add a new Python code cell by selecting the **+Code** command in the toolbar.

   :::image type="content" source="media/notebooks-python-kernel/notebook-toolbar-python.png" alt-text="Screenshot of Notebook toolbar.":::

1. Copy and paste the following example into the cell and select **Run cell**. This example does simple math and the result appears below.

   ```python
   a = 1
   b = 2
   c = a/b
   print(c)
   ```

   :::image type="content" source="media/notebooks-python-kernel/run-notebook-cell-python.png" alt-text="Screenshot of Run notebook cell.":::

## Related content

- [Extend Python with Kqlmagic](./notebooks-kqlmagic.md)
- [How to use notebooks in Azure Data Studio](./notebooks-guidance.md)
- [Create and run a SQL Server notebook](./notebooks-sql-kernel.md)
