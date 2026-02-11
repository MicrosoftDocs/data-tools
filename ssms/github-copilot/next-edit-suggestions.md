---
title: Next Edit Suggestions
titleSuffix: GitHub Copilot in SQL Server Management Studio (Preview)
description: Learn how to use next edit suggestions for GitHub Copilot in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: erinstellato
ms.date: 02/11/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand how to use GitHub Copilot Completions in SQL Server Management Studio.
---

# Use Next Edit Suggestions in SQL Server Management Studio (Preview)

The Next Edit Suggestions (NES) feature of GitHub Copilot uses your recent edits to anticipate the next edit that you might want to make, and the location of that edit. With this capability, Copilot suggests revisions to your code and comments.

Inline completions are great at autocompleting a section of code. NES helps you stay in the logical edit flow by suggesting changes that are relevant to your current work. You can use the <kbd>Tab</kbd> key to quickly move through and accept suggestions. Suggestions might span one or more lines, depending on the scope of the potential change.

## Prerequisites

Next Edit Suggestions for GitHub Copilot in SSMS supports the Transact-SQL (T-SQL) language.

1. Install SSMS 22.2 or a later version with the [AI Assistance workload](installation-state.md#install-github-copilot-in-ssms-using-the-visual-studio-installer).

1. Sign in to your GitHub account with Copilot access.

[Use GitHub Copilot for free](free-plan.md). Sign up and use AI to code faster and more efficiently.

## Enable Next Edit Suggestions

To get started with GitHub Copilot NES, enable the feature in **Tools** > **Options** > **All Settings** > **Text Editor** > **Code Completions** > **General**. Select **Copilot Next Edit Suggestions (Next-edit predictions from Copilot)** in the **Code Completions Providers** section.

## Start using Next Edit Suggestions

With **Copilot Next Edit Suggestions (Next-edit predictions from Copilot)** enabled, start writing T-SQL to see suggestions from NES. When the feature suggests a code edit, you can move to it by using the <kbd>Tab</kbd> key, and then accept it by using the <kbd>Tab</kbd> key again. You save time by quickly jumping to the next relevant edit, without needing to manually search through files or references yourself. An arrow in the gutter indicates whether an edit suggestion is available.

## Understand use cases

NES is helpful in various scenarios by suggesting not only obvious repetitive changes, but also logical changes.

### Catch and correct mistakes

NES helps with mistakes like typos. For example, it catches errors if you write `SELCT` instead of `SELECT`.

### Match a change in intent

NES suggests changes to the rest of your code that match a change in intent. For example, if you update a query and add an alias for a table, NES shows suggestions that use the new alias.

## Refactor

If you rename an object or variable once in a file, NES suggests updating it throughout the file. If you introduce a new name or naming pattern, the feature suggests updates to subsequent code to match.

## Hide NES

You can hide suggestions from NES in SSMS and review them only when you choose.

In **Tools** > **Options** > **All Settings** > **Text Editor** > **Code Completions** > **General** > **Copilot Completions Model**, select **Collapse Next Edit Suggestions**. Your edits still trigger NES, but when a suggestion is available, only the margin indicator appears in the gutter. This indicator points to the relevant line. The suggestion itself remains hidden until you choose to view it.

To view a hidden suggestion, select the margin indicator or the <kbd>Tab</kbd> key and the suggestion appears. You can select the <kbd>Tab</kbd> key again to accept the suggestion or select the <kbd>Esc</kbd> key to dismiss it. After you accept a suggestion, any related suggestions appear automatically. Unrelated new suggestions remain hidden until you choose to view them.

## Related content

- [Use Code Completions in SQL Server Management Studio (Preview)](code-completions.md)
- [Get started with GitHub Copilot in SQL Server Management Studio (Preview)](get-started.md)
- [Troubleshoot GitHub Copilot in SQL Server Management Studio (Preview)](troubleshoot.md)
