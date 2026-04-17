---
title: Code Completions
titleSuffix: GitHub Copilot in SQL Server Management Studio
description: Learn how to use completions from GitHub Copilot in SQL Server Management Studio (SSMS).
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: erinstellato
ms.date: 04/17/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand how to use GitHub Copilot Completions in SQL Server Management Studio.
---

# Use Completions in SQL Server Management Studio

Use GitHub Copilot in SQL Server Management Studio (SSMS) to enhance your Transact-SQL (T-SQL) development with AI assistance. GitHub Copilot helps you be more productive and efficient when writing T-SQL in the query editor.

Copilot provides two kinds of inline suggestions, both of which take your existing T-SQL into account:

- Completions: As you type in the editor, Copilot provides ghost text suggestions at your current cursor location.
- Next edit suggestions (NES): Based on your current editing patterns, [NES](next-edit-suggestions.md) predicts both where your next code edit will be and what changes you'll make.

For related information about GitHub Copilot Chat, see [Use the GitHub Copilot Chat experience in SQL Server Management Studio](chat.md).

## How Code Completions work

Code Completions for GitHub Copilot in SSMS use advanced machine learning models trained on a vast dataset of publicly available code from GitHub repositories. As you type code, the AI analyzes the context and provides relevant suggestions in real time. Context for GitHub Copilot in SSMS includes the schema for the database to which you're connected in the active editor and the contents of the current editor. You can also obtain suggestions by writing a comment, often preceded by `--`, in natural language that describes what you want the code to do.

## Prerequisites

Code Completions for GitHub Copilot in SSMS supports the T-SQL language.

1. Install SSMS 22.2 or a later version with the [AI Assistance workload](installation-state.md#install-github-copilot-in-ssms-using-the-visual-studio-installer).

1. Sign in to your GitHub account with Copilot access.

[Use GitHub Copilot for free](free-plan.md). Sign up and use AI to code faster and more efficiently.

## Use GitHub Copilot for code completions and suggestions

As you type comments or T-SQL in the editor, GitHub Copilot provides ghost text code suggestions: sometimes the completion of the current line, sometimes a whole new block of code. You can accept all, or part of a suggestion, or you can keep typing and ignore the suggestions.

1. Open SSMS and connect to your database in query editor.

1. In the editor, enter a comment to see inline code suggestions from GitHub Copilot:

   ```output
   --list all tables in this database
   ```

1. Select enter to see the suggestion.

1. To accept the suggestion, select <kbd>Tab</kbd>. To reject the suggestion, select <kbd>Esc</kbd> or continue typing.

Suggestions can also be accepted, either partially or entirely, with a mouse or other pointing device starting in SSMS 22.3. All inline suggestions settings can be found via **Tools** > **Options** > **Text Editor** > **Inline Suggestions**. You can also access settings using **Settings** > **Options** from the Copilot badge.

## Shortcuts and settings

Several keyboard shortcuts are available for completions:

- To manually trigger a completion, use <kbd>Alt</kbd>+<kbd>.</kbd> or <kbd>Alt</kbd>+<kbd>,</kbd>.
- To cycle through available completions, use <kbd>Alt</kbd>+<kbd>.</kbd> to move to the next suggestion and <kbd>Alt</kbd>+<kbd>,</kbd> to move to the previous suggestion.
- To partially accept a completion word by word, use <kbd>Ctrl</kbd>+<kbd>Right arrow</kbd>.
- To partially accept a completion line by line, use <kbd>Ctrl</kbd>+<kbd>Down arrow</kbd>.

You can customize your completion experience by changing selected settings.

If completions appear too quickly and interrupt your typing, adjust the display timing under **Tools** > **Options** > **Text Editor** > **Inline Suggestions** > **Preferences**. Select **Show code completions only after a pause in typing** to add a short pause (a *debounce* delay) so completions don't flash and disappear while you're still typing.

By default, each keystroke automatically triggers a completion. To disable this setting, go to **Tools** > **Options** > **Text Editor** > **Inline Suggestions** > **General** and set **Invocation** to **Manual**. You can then trigger completions manually by using the <kbd>Alt</kbd>+<kbd>.</kbd>, or <kbd>Alt</kbd>+<kbd>,</kbd> keyboard shortcut.

Starting in SSMS 22.5, you can also customize the keyboard shortcuts for accepting Copilot inline suggestions. You can change the key for accepting the full suggestion, the next word, or the next line, in standard keyboard settings.

To set your preferred shortcuts:

1. Select **Tools** > **Options** > **Environment** > **Keyboard**

1. Search for the command you want to customize:

   - `Edit.AcceptSuggestion`
   - `Edit.AcceptNextWordInSuggestion`
   - `Edit.AcceptNextLineInSuggestion`

1. Remove the existing key binding.

1. Select **Inline Suggestion Active** from the **Use new shortcut in:** dropdown list.

1. Add the new shortcut within **Press shortcut keys:**.

1. Select **Assign**.

## Completions model

The GPT-4.1 Copilot model for code completions is currently the only available model for code completions in SSMS.

If you're a Copilot Business or Enterprise user, your administrator needs to enable this model for your organization. Your administrator can opt in to editor preview features in the Copilot policy settings on GitHub.com. If you're a Copilot Free user, using this model counts toward your 2,000 free monthly completions.

## Related content

- [Use Next Edit Suggestions in SQL Server Management Studio](next-edit-suggestions.md)
- [Get started with GitHub Copilot in SQL Server Management Studio](get-started.md)
- [Troubleshoot GitHub Copilot in SQL Server Management Studio](troubleshoot.md)
