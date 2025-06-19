---
title: Source Control
description: Azure Data Studio supports Git for Source Control Management (SCM). Learn how to open an existing Git repository, and how to initialize a new one.
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest, maghan
ms.date: 02/06/2025
ms.service: azure-data-studio
ms.topic: how-to
ms.collection:
  - data-tools
---

# Source control in Azure Data Studio

[!INCLUDE [azure-data-studio-deprecation](includes/azure-data-studio-deprecation.md)]

Azure Data Studio supports Git for version/source control.

## Git support in Azure Data Studio

Azure Data Studio ships with a Git source control manager (SCM), but you still need to [install Git (version 2.0.0 or later)](https://git-scm.com/download) before these features are available.

## Open an existing Git repository

1. Under the **File** menu, select **Open Folder...**
1. Browse to the folder that contains your files tracked by git, and select **Select Folder**. Subfolders in your local repository are okay to select here.

## Initialize a new git repository

1. Select **Source Control**, then select the git icon.

   :::image type="content" source="media/source-control/source-control.png" alt-text="Screenshot of source control git icon." lightbox="media/source-control/source-control.png":::

1. Enter the path to the folder you want to initialize as a Git repository and press **Enter**.

   :::image type="content" source="media/source-control/initialize-git-repository.png" alt-text="Screenshot of initialize Git repository." lightbox="media/source-control/initialize-git-repository.png":::

## Working with Git repositories

Azure Data Studio inherits its Git implementation from VS Code, but doesn't currently support additional SCM providers. For the details about working with Git after you open or initialize a repository, see [Git support in VS Code](https://code.visualstudio.com/docs/editor/versioncontrol#_git-support).

## Related content

- [Download Azure Data Studio from](download-azure-data-studio.md)
