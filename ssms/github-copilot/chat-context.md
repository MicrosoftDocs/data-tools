---
title: Chat Context
titleSuffix: GitHub Copilot in SQL Server Management Studio (Preview)
description: Learn how to add context for GitHub Copilot in SQL Server Management Studio.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand how to add context for GitHub Copilot in SQL Server Management Studio.
---

# Add context for GitHub Copilot in SQL Server Management Studio (Preview)

Add more context to your prompts in GitHub Copilot in SQL Server Management Studio (SSMS) by using references, in addition to its contextual knowledge, to obtain better responses.

## Use slash commands for code assistance

GitHub Copilot in SQL Server Management Studio (SSMS) offers code assistance to help you set the intent for common database development tasks. This intent can accelerate productivity to help you understand and fix queries faster. Highlight any query in the editor and use the slash commands to document, explain, fix, or optimize the query. The slash commands are available in both the chat window and inline chat.

| Command | Usage |
| --- | --- |
| `/doc` | Add comments for selected T-SQL code to help the next person who looks at your code understand what you did. |
| `/explain` | Get in-depth details about the selected T-SQL code. |
| `/fix` | Address errors in the T-SQL code and return a correct version to review, including an explanation of the issue and what was changed. |
| `/help` | Get help on using Copilot Chat. |
| `/optimize` | Identify anti-patterns in the query and make changes consistent with T-SQL best practices |

## Reference other files

You can ask your T-SQL related questions in natural language and GitHub Copilot Chat answers in the context of active editor in SSMS. References provide specific information you want Copilot to consider when answering your question.

By selecting other files open in the editor, you might be able to form better questions without having to write out or paste long pieces of information. Specifying the context also enables Copilot to provide you with more relevant answers.

To reference a file in GitHub Copilot Chat, add a # symbol at the beginning of the file name. For example, if you have a file named `GetSalesInfo.sql`, refer to it in the chat as `#GetSalesInfo.sql`.

## Manage chat history context with threads

As you iterate and send multiple chat prompts in a chat session, Copilot uses the history of chat prompts and responses. The previous prompts and responses provide context to your current chat prompt. This means that you can ask follow-up questions or clarify your previous question without having to repeat the context. For example, you can ask "How do I change the compatibility mode?", "What are the differences between compatibility mode 140 and 170?", "What do I need to consider when changing compatibility mode?", and more.

To start over with a new chat session and discard the current context, start a new thread in the chat view. New threads are useful when you want to move to a different topic and avoid the previous context and history. Use threads to keep conversations focused on the task at hand, and keep the context clear so the answers are based on relevant history.

### New chat thread

Select **Create new thread** or **Ctrl**+**N** in the chat window to start a new thread.

### Switch chat thread

You can toggle between multiple ongoing threads to provide the right historical context for your question. Use **Ctrl**+**Page Down** for previous thread or **Ctrl**+**Page Up** for next thread in the chat window. **Ctrl**+**Shift**+**T** expands the thread dropdown list.

### Preserve the inline chat

To preserve the history of your inline chat, promote it to the chat window. Select **View in chat window** to maintain a record and context of the conversation, and continue in the chat window.

## Best practices

Copilot Chat uses the chat history to get context about your request. To give Copilot only the relevant history:

- Use threads to start a new conversation for a new task.
- Delete requests that are no longer relevant or that didn't give you the desired result.

Keep the chat conversation open and continue to iterate and prompt Copilot to improve the suggested solution. Copilot has both the context of the generated code and your current conversation history. As you keep asking questions, Copilot further refines the response according to your requirements.

## Related content

- [Get started with GitHub Copilot in SQL Server Management Studio (Preview)](get-started.md)
- [Scenarios for GitHub Copilot in SQL Server Management Studio (Preview)](scenarios.md)
