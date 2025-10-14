---
title: Ask Mode
titleSuffix: GitHub Copilot in SQL Server Management Studio (Preview)
description: Learn how to use the GitHub Copilot Chat experience in SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 10/14/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand how to use GitHub Copilot Chat in SQL Server Management Studio.
---
# Use the GitHub Copilot Chat experience in SQL Server Management Studio (Preview)

The Chat window for GitHub Copilot in SQL Server Management Studio (SSMS) enables enhanced AI-assisted database administration and development in SSMS, helping you be more productive and efficient when working with your SQL database.

In this article, you learn about using GitHub Copilot Chat in SSMS, a fully integrated AI-powered chat experience from GitHub Copilot that exists directly in SSMS. It enables you to get Transact-SQL (T-SQL) support, including syntax and context-specific help, without leaving the SSMS UI. Use the chat interface to submit your question as prompt and provide intent for better scoped answers.

## Why use GitHub Copilot Chat in SSMS?

GitHub Copilot Chat provides AI assistance to help you make informed decisions about your SQL database and write better T-SQL faster. With an integration in SSMS that includes connection context and schema understanding, GitHub Copilot Chat understands what you're working on and can help with tasks including:

- T-SQL assistance:

  - Get context-specific code suggestions and recommendations
  - Understand and document what a query does
  - Get assistance fixing syntax errors in your query
  - Refactor queries

- Database administration:

  - Get help managing settings, security, and more
  - Configure and monitor database maintenance
  - Implement new SQL features

- Database development:

  - Schema design
  - Data type selection
  - Indexing recommendations

## Prerequisites

To use GitHub Copilot Chat in SSMS, you need SSMS 22 (Preview) or higher, and a GitHub account with [Copilot access](https://docs.github.com/copilot/get-started/what-is-github-copilot#getting-access-to-copilot). Otherwise, you can use [Use GitHub Copilot for free in SQL Server Management Studio (Preview)](free-plan.md).

## Use Copilot Chat in SSMS

Ask database and T-SQL questions in natural language and GitHub Copilot Chat will answer them in the context of your database and its connection.

There are two places you can ask Copilot these questions; in the chat window, or directly inline in the code that you're looking to modify, using inline chat. For questions where your goal is to modify or add to the SQL file you have open in the editor, the inline chat view might work best, whereas more general T-SQL questions are best answered in the chat pane.

See tips to improve Copilot chat results to learn how to use [slash commands](chat-context.md#use-slash-commands-for-code-assistance), [reference files](chat-context.md#reference-other-files), and [threads](chat-context.md#manage-chat-history-context-with-threads) to get better answers with scoped context in Copilot Chat.

### Ask questions in the chat window

The chat window of Copilot Chat in SSMS enables you to ask your questions and see answers in the chat pane. It's usually the preferred way to work with Copilot for database help and general T-SQL questions.

1. Open a query editor window and connection to your database.
1. In SSMS, select **View** > **GitHub Copilot Chat**.
1. Use the example starter prompts in the chat window to start exploring Copilot Chat, or type in a prompt and select **Enter** or **Send** to submit your question.
1. If Copilot Chat offers a T-SQL suggestion you want to use, select **Apply** to apply the code to the active query editor, **Copy code block** to copy the suggestion, or **Add to new file** to insert the code suggestion in a new file.
   - If you ask for help with understanding your code, the **Insert in new file** option isn't available.
1. If you select **Apply**, the code suggestion is applied to the active editor in the diff view pattern. You can review and refine what is being proposed and apply it using **Tab**, or discard it using **Alt** + **Delete**.

### Ask questions in the inline chat view

The inline chat view of Copilot Chat in SSMS enables you to ask your questions and see answers inline with the code directly in the editor window. With inline chat, you don't have to go back and forth to the chat window. You might find it easier to work with Copilot on questions that add to or update a currently open SQL file using inline chat.

1. In SSMS, select **Alt** + **/** to bring up the inline chat view of Copilot Chat in the editor.
1. Type your T-SQL related question in the Ask Copilot text box, and then select **Enter** or **Send** to ask your question.
1. Code suggestions from Copilot Chat appear in the diff view. You can review and refine what is being proposed and apply the change to your code using **Tab**, or discard it using **Alt** + **Delete**.
1. You can promote your inline chat thread to the chat window by selecting **View in chat window**. This preserves the record and context of your conversation, and you can continue in the chat window.
1. Select **Esc** to close the inline chat view.

## Related content

- [Get started with GitHub Copilot in SQL Server Management Studio (Preview)](get-started.md)
- [Add context for GitHub Copilot in SQL Server Management Studio (Preview)](chat-context.md)
- [Troubleshoot GitHub Copilot in SQL Server Management Studio (Preview)](troubleshoot.md)
