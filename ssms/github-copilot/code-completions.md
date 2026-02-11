---
title: Code Completions
titleSuffix: GitHub Copilot in SQL Server Management Studio (Preview)
description: Learn how to use code completions from GitHub Copilot in SQL Server Management Studio (SSMS).
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

# Use Code Completions in SQL Server Management Studio (Preview)

Use GitHub Copilot in SQL Server Management Studio (SSMS) to enhance your Transact-SQL (T-SQL) development with AI assistance. GitHub Copilot helps you be more productive and efficient when writing T-SQL.

In this article, you learn how to use GitHub Copilot Completions, which provide you with context-aware code completions, suggestions, and even entire code snippets. This feature helps reduce the time spent on repetitive tasks and minimizes errors.

For related information about GitHub Copilot Chat, see [Use the GitHub Copilot Chat experience in SQL Server Management Studio (Preview)](chat.md).

## How Code Completions work

Code Completions for GitHub Copilot in SSMS use advanced machine learning models trained on a vast dataset of publicly available code from GitHub repositories. As you type code, the AI analyzes the context and provides relevant suggestions in real time. Context for GitHub Copilot in SSMS includes the schema for the database to which you're connected in the active editor, the contents of the current and all open editors. You can also obtain suggestions by writing a comment, often preceeded by `--`, in natural language that describes what you want the code to do.

## Prerequisites

Code Completions for GitHub Copilot in SSMS supports the T-SQL language.

1. Install SSMS 22.2 or a later version with the [AI Assistance workload](installation-state.md#install-github-copilot-in-ssms-using-the-visual-studio-installer).

1. Sign in to your GitHub account with Copilot access.

[Use GitHub Copilot for free](free-plan.md). Sign up and use AI to code faster and more efficiently.

## Use GitHub Copilot for code completions and suggestions

As you type comments or T-SQL in the editor, GitHub Copilot provides context-aware code completions and suggestions.

1. Open SSMS and connect to your database in query editor.
1. In the editor, enter a comment to see inline code suggestions from GitHub Copilot:

   ```sql
    --list all tables in this database
   ```

1. Select enter to see the suggestion.
1. To accept the suggestion, select <kbd>Tab</kbd>. To reject the suggestion, select <kbd>Esc</kbd> or continue typing.

Suggestions can also be accepted, either partially or entirely, with a mouse click starting in SSMS 22.3. To change the keyboard shortcut used to accept suggestions, go to **Tools** > **Options** > **All Settings** > **Text Editor** > **Code Completions** > **Preferences** > **Accept code compeltions using keyboard shortcuts**.

## Shortcuts and settings

Several keyboard shortcuts are available for completions:

- To manually trigger a completion, use <kbd>Alt</kbd>+<kbd>.</kbd> or <kbd>Alt</kbd>+<kbd>,</kbd>.
- To cycle through available completions, use <kbd>Alt</kbd>+<kbd>.</kbd> to move to the next suggestion and <kbd>Alt</kbd>+<kbd>,</kbd> to move to the previous suggestion.
- To partially accept a completion word by word, use <kbd>Ctrl</kbd>+<kbd>Right arrow</kbd>.
- To partially accept a completion line by line, use <kbd>Ctrl</kbd>+<kbd>Down arrow</kbd>.

You can customize your completion experience by changing selected settings.

If completions appear too quickly and interrupt your typing, you can adjust the display timing in **Tools** > **Options** > **All Settings** > **Text Editor** > **Code Completions** > **Preferences**. Select **Show code completions only after a pause in typing** to stop displaying completions while you're typing. This setting adds a debounce delay, so completions don't flash and disappear while you're typing.

By default, each keystroke automatically triggers completions. You can disable automatic completions in **Tools** > **Options** > **All Settings** > **Text Editor** > **Code Completions** > **General** when you set **Code Completion Invocation** to **Manual**. After you make this change, you can manually trigger completions using the <kbd>Alt</kbd>+<kbd>,</kbd> keyboard shortcut.

## Completions model

The GPT-4.1 Copilot model for code completions is currently the only available model for GitHub Copilot in SSMS. You can find the setting in **Tools** > **Options** > **All Settings** > **Text Editor** > **Code Completions** > **General** > **Copilot Completions Model**.

If you're a Copilot Business or Enterprise user, your administrator needs to enable this model for your organization. Your administrator can opt in to editor preview features in the Copilot policy settings on GitHub.com. If you're a Copilot Free user, using this model counts toward your 2,000 free monthly completions.

## Related content

- [Use Next Edit Suggestions in SQL Server Management Studio (Preview)](next-edit-suggestions.md)
- [Get started with GitHub Copilot in SQL Server Management Studio (Preview)](get-started.md)
- [Troubleshoot GitHub Copilot in SQL Server Management Studio (Preview)](troubleshoot.md)
