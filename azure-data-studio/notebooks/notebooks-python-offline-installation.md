---
title: Python Installation in an Offline Windows Environment
description: This tutorial shows how you can install Python in an offline Windows environment
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest, maghan
ms.date: 02/06/2025
ms.service: azure-data-studio
ms.topic: how-to
ms.collection:
  - data-tools
ms.custom:
  - intro-installation
---

# Install Python in an offline Windows environment

[!INCLUDE [azure-data-studio-deprecation](../includes/azure-data-studio-deprecation.md)]

This tutorial demonstrates how to install and use the Python kernel in an offline Windows environment with notebooks.

## Prerequisites

- [Azure Data Studio installed](../download-azure-data-studio.md)

## Download Python and dependencies

1. On a machine that has internet access, download the latest [Azure Data Studio Python package](https://go.microsoft.com/fwlink/?linkid=2163338). Unzip the file into a local directory (for example: `C:\azuredatastudio-python`).

   > [!NOTE]  
   > The latest Azure Data Studio Python version is 3.8.10.

1. In a terminal, navigate to the Python directory.

    ```cmd
    cd C:\azuredatastudio-python
    ```

1. Create a text file named **requirements.txt** with the following contents.

    ```txt
    pandas>=0.24.2
    jupyter>=1.0.0
    sparkmagic>=0.12.9
    powershell-kernel>=0.1.3
    ```

1. Create a sub directory named `wheelhouse`.

    ```cmd
    mkdir wheelhouse
    ```

1. Run the following command to download the required dependencies to the sub directory.

    ```cmd
    python.exe -m pip download -r requirements.txt -d wheelhouse
    ```

> [!NOTE]
> Check to make sure you have the latest pip version installed.
> If you aren't sure, you can upgrade it by running the following command: `C:\azuredatastudio-python\python.exe -m pip install --upgrade pip`.

## Install Python on a machine that doesn't have internet access

1. On a machine that doesn't have internet access, copy the Python folder to a local directory (for example: `C:\azuredatastudio-python`).

1. In a terminal, navigate to the Python folder.

    ```cmd
    cd C:\azuredatastudio-python
    ```

1. Run the following to install the dependencies.

    ```cmd
    python.exe -m pip install -r requirements.txt --no-index --find-links wheelhouse
    ```

## Use the Python Installation in Azure Data Studio

1. Open Azure Data Studio
1. From the Command Palette, search for *Configure Python for Notebooks*.
1. In the **Configure Python for Notebooks** wizard, select **Use existing Python installation**, and browse to the installed Python location (for example: `C:\azuredatastudio-python`).

Once the wizard is completed, open a new notebook and change the kernel to Python.

## Related content

- [Python in Azure Data Studio](notebooks-python-kernel.md)
