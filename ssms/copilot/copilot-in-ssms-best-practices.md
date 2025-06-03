---
title: Best Practices
titleSuffix: Copilot in SQL Server Management Studio
description: Learn about best practices for using Copilot in SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 05/21/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
# CustomerIntent: As a database administrator or database developer, I want to understand the best practices to optimize my use of Copilot in SQL Server Management Studio.
---
# Best practices for Copilot in SQL Server Management Studio

A primary goal of Copilot in SQL Server Management Studio (SSMS) is to accelerate your productivity within your workflow in SSMS, including writing and editing Transact-SQL (T-SQL). To get the most out of Copilot in SSMS, it's not just about turning it on, it's about learning how to collaborate with it effectively. Like any partner, Copilot in SSMS performs best when given clear direction and appropriate context. Optimal use of the chat window also enhances the quality of your experience with Copilot in SSMS.

## Chat window

The icons and capabilities of the chat window are documented in [Use the chat window for Copilot in SQL Server Management Studio](copilot-in-ssms-chat.md), but there are other considerations specific to prompts.

Primarily, don't treat the chat window as a results window. When you ask Copilot questions about your schema or data, it might directly execute a query to return information to you in the chat window. Copilot in SSMS doesn't determine the number of rows returned by a query before it executes, and if the query returns 1,000 rows, it tries to display that information in the chat. Large result sets aren't easily readable, and can't be manipulated, within the chat window.

Asking Copilot in SSMS to write the query to return the information is often preferred, and creates a better interaction and experience with Copilot in SSMS.

## Consistency

A common frustration among users of copilots is an inconsistency in responses. AI responses can be inconsistent because they're generated probabilistically rather than deterministically. This means that even when asked the same question, the model might choose a different, but still plausible, set of words or sentence structure based on subtle variations in context, configuration, or internal randomness. Additionally, AI models weigh many potential interpretations of a prompt, so small changes in phrasing or timing can lead to different outcomes. This variability is part of what makes AI so flexible and powerful, but it can also lead to unpredictable results if prompts aren't optimally constructed.

## Prompt writing

Inherent in working with AI is writing prompts to submit, and just like performance tuning, it's an art and a science. You don't need to be a prompt engineer to write good prompts. But you do need to be aware of general guidelines when engaging with AI.

As an example, if you ask `Find the hottest tables in the database`, Copilot in SSMS might not understand that in the context of this prompt, the hottest tables are those tables that are the busiest, or most active. Instead, try `List the top 10 tables in the database that have the most reads`.

General recommendations for prompt writing include:

| Recommendation | Details |
| --- | --- |
| **Use natural language** | You don't need to use specialized vocabulary, but try to avoid informal phrases, slang, and jargon. |
| **Be clear and specific** | Provide enough detail so Copilot is clear about what you're asking. |
| **Provide context** | Copilot in SSMS has database context based on the query editor connection, but you can provide extra context such as a timeframe, or specific database objects. |
| **Use examples** | Build on previous responses, such as `Modify the last query to order the results by CustomerID`. |
| **Define the output format** | Copilot can provide information in text, table, or list format. It chooses for you, but you can specifically ask for information to be returned in a desired format. |

Example prompts:

| Recommendation | Avoid | Try |
| --- | --- | --- |
| **Use natural language** | `Yo cook me up something cool for grabbing sales data` | `Write a SQL query that selects the top 10 most recent orders from the Sales.Orders table` |
| **Be clear and specific** | `Okay, so I've got this thing where I need to maybe get some kind of report or output or whatever for yesterday's stuff but like only for users that are new but not too new, if that makes sense` | `Write a query to return users who registered yesterday and have not yet made a purchase` |
| **Provide context** | `List western schools with no language reqs` | `List schools in the US-West geo that have a lang_req value of 0` |
| **Use examples** | `Write a query to get recent customer info` | `Write a query to get customer ID, name, and total number of orders for the last 10 business days ordered by total desc` |
| **Define the output format** | `Give me hospital locations and size with the busiest emergency rooms` | `List the hospitals with the busiest emergency rooms in table format and include city state and size` |

## Related content

- [Use the chat window for Copilot in SQL Server Management Studio](copilot-in-ssms-chat.md)
- [Scenarios for Copilot in SQL Server Management Studio](copilot-in-ssms-scenarios.md)
