---
title: "What Is GitHub Copilot in SQL Server Management Studio (Preview)?"
titleSuffix: GitHub Copilot in SQL Server Management Studio (Preview)
description: Overview of GitHub Copilot in SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 11/11/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to understand what is GitHub Copilot in SQL Server Management Studio.
---
# What is GitHub Copilot in SQL Server Management Studio (Preview)?

GitHub Copilot in SQL Server Management Studio (SSMS) helps you write Transact-SQL (T-SQL) faster and with greater accuracy. It can also answer general SQL questions and assist with administrator tasks, directly in your SSMS environment.

GitHub Copilot in SSMS doesn't retain any of your information (prompts, responses, system metadata, etc.) and doesn't use any of your data to train or retrain models. For more information, see [How GitHub Copilot handles data](https://resources.github.com/learn/pathways/copilot/essentials/how-github-copilot-handles-data/).

GitHub Copilot in SSMS can answer questions for databases in SQL Server, Azure SQL Database, Azure SQL Managed Instance, and SQL Database in Fabric. GitHub Copilot executes queries based on the permissions for your login. For example, if you don't have permission to select from the table `Sales.Orders` and you ask GitHub Copilot to write and execute a select query such as `SELECT TOP 100 * FROM Sales.Orders`, the query execution can't occur.

## How GitHub Copilot works in SSMS

GitHub Copilot in SSMS uses your GitHub account with [Copilot access](https://docs.github.com/copilot/get-started/what-is-github-copilot#getting-access-to-copilot). The integration allows you to select a model, and GitHub Copilot in SSMS sends your prompts to the model. The model generates the response and sends it back to SSMS. GitHub Copilot in SSMS might send additional information about the version of SQL to which you're connected, or information about your database, along with your prompt to help improve the response.

## Features of GitHub Copilot in SSMS

GitHub Copilot in SSMS includes [chat capabilities](chat.md) in the chat window and through the inline chat view. From either location you can use natural language to ask questions about your database, or get help writing T-SQL. Copilot in SSMS also includes code assistance, available using [slash commands](chat-context.md#use-slash-commands-for-code-assistance) such as `/doc`, to provide assistance documenting, explaining, fixing, or optimizing your T-SQL queries. To enable GitHub Copilot in SSMS, see [Install GitHub Copilot in SQL Server Management Studio (Preview)](installation-state.md).

## Best practices for using GitHub Copilot in SSMS

To maximize your productivity with GitHub Copilot in SSMS, open a query editor that is connected to your database, and then open the chat window. By default, the chat window has context about the database to which you're connected based on the active query editor. When writing prompts, be specific in your request as vague questions lead to vague responses. For more best practices, see [Best practices for GitHub Copilot in SQL Server Management Studio (Preview)](best-practices.md).

## Example prompts

The following example prompts are clear, specific, and tailored to the properties of your schema and database, making it easier for GitHub Copilot in SSMS to generate accurate replies.

  ```copilot-prompt
    - What are the top-selling products by quantity?
    - How do I change the compability mode for this database?
    - Is there blocking in my database right now?
  ```

More examples can be found in [Scenarios for GitHub Copilot in SQL Server Management Studio (Preview)](scenarios.md)

## Responsible AI use of Copilot

Microsoft is committed to ensuring that our AI systems are guided by our [AI principles](https://www.microsoft.com/ai/principles-and-approach). To learn more about GitHub Copilot's security, privacy, compliance, and transparency, see the [GitHub Copilot Trust Center FAQ](https://copilot.github.trust.page/faq). Our AI principles include empowering our customers to use these systems effectively and in line with their intended uses. Our approach to responsible AI is continually evolving to proactively address emerging issues.

## Limitations

Here are the current limitations of GitHub Copilot in SSMS:

- GitHub Copilot in SSMS doesn't currently support code completions in the query editor.
- GitHub Copilot might produce inaccurate results when the intent is to evaluate data.
- GitHub Copilot responses can include inaccurate or low-quality content, so review outputs before using them in your work.
- People who can meaningfully evaluate the content's accuracy and appropriateness should review the outputs.
- GitHub Copilot doesn't currently support exporting the chat.
- GitHub Copilot doesn't currently support Agent mode.

## Related content

- [Get started with GitHub Copilot in SQL Server Management Studio (Preview)](get-started.md)
- [Use GitHub Copilot for free in SQL Server Management Studio (Preview)](free-plan.md)
