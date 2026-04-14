---
title: Chat Context
titleSuffix: GitHub Copilot in SQL Server Management Studio
description: Learn how to add context for GitHub Copilot in SQL Server Management Studio.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: erinstellato
ms.date: 04/14/2026
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand how to add context for GitHub Copilot in SQL Server Management Studio.
---

# Add context for GitHub Copilot in SQL Server Management Studio

Add more context to your prompts in GitHub Copilot in SQL Server Management Studio (SSMS) by using references, in addition to its implicit, contextual knowledge, to get better responses.

## Implicit context

GitHub Copilot in SSMS automatically provides context to the prompt based on the active query editor and its database connection. The chat context implicitly includes the following information:

- The currently selected text in the active query editor.
- The current file active in the query editor.
- The database connection for the active query editor.

Depending on your prompt, Copilot reads the contents of the active query editor, or reads the selected text in the editor.

## Chat history

As you iterate and send multiple chat prompts in a session, Copilot uses the history of chat prompts and responses as context for your current prompt. You can ask follow-up questions or clarify your previous question without having to repeat the context. For example, you can ask `How do I change the compatibility mode?`, and follow up with `How will this change affect query performance?`, `How do I test changes in query performance?`, and more.

Keep the chat conversation open and continue to iterate and prompt Copilot to improve the suggested solution. Copilot has both the context of the generated code and your current conversation history. As you keep asking questions, Copilot further refines the response according to your requirements.

### Manage chat history context with threads

Use threads to keep conversations focused and ensure answers are based on relevant history. For detailed information on creating, switching, and managing threads, see [Create threads for separate conversations](chat.md#create-threads-for-separate-conversations).

## Reference other files

You can ask your T-SQL related questions in natural language and GitHub Copilot Chat answers in the context of active editor in SSMS. References provide specific information you want Copilot to consider when answering your question.

By selecting other files open in the editor, you might be able to form better questions without having to write out or paste long pieces of information. Specifying the context also enables Copilot to provide you with more relevant answers.

To reference a file in GitHub Copilot Chat, add a # symbol at the beginning of the file name. For example, if you have a file named `GetSalesInfo.sql`, refer to it in the chat as `#GetSalesInfo.sql`.

## Reference the results pane

Starting with SSMS 22.5, you can ask questions about the components of the results pane directly in GitHub Copilot Chat. After you run a query in the active editor, you can ask about the results grid or the messages tab.

For example:

```copilot-prompt
What is the total ItemPrice for lines 1 through 10?
```

If either the estimated or actual execution plan is included in the results pane, you can ask:

```copilot-prompt
How do I optimize this query based on the execution plan?
```

## Custom instructions

Custom instructions let you automatically add contextual details to your prompts without repeating them every time. You create a custom instructions file in the root of your repository or your `USERPROFILE` folder, and Copilot Chat uses those instructions to tailor responses based on your preferences.

For example, you can specify coding conventions, preferred T-SQL patterns, or formatting standards that Copilot should follow in its responses.

For more information, see [Use custom instructions with GitHub Copilot in SQL Server Management Studio](custom-instructions.md).

## Database instructions

Database instructions provide Copilot with database-specific context and guidance that lives directly in the database. Database owners and teams use custom instructions to describe business rules, data conventions, and usage patterns so that Copilot generates more accurate and consistent responses.

For more information, see [Use database instructions with GitHub Copilot in SQL Server Management Studio](database-instructions.md).

## Use slash commands for code assistance

GitHub Copilot in SSMS offers code assistance to help you set the intent for common database development tasks. This intent can accelerate productivity and help you understand and fix queries faster. Highlight any query in the editor and use the slash commands to document, explain, fix, or optimize the query. You can use the slash commands in both the chat window and inline chat.

| Command | Usage |
| --- | --- |
| `/doc` | Add comments for selected T-SQL code to help the next person who looks at your code understand what you did. |
| `/explain` | Get in-depth details about the selected T-SQL code. |
| `/fix` | Address errors in the T-SQL code and return a correct version to review, including an explanation of the issue and what was changed. |
| `/help` | Get help on using Copilot Chat. |
| `/optimize` | Identify anti-patterns in the query and make changes consistent with T-SQL best practices. |

## Related content

- [Use the GitHub Copilot Chat experience in SQL Server Management Studio](chat.md)
- [Get started with GitHub Copilot in SQL Server Management Studio](get-started.md)
- [Scenarios for GitHub Copilot in SQL Server Management Studio](scenarios.md)
