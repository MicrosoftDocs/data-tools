---
title: Use the Chat Window
titleSuffix: Copilot in SQL Server Management Studio
description: Learn how to use the chat window for Copilot in SQL Server Management Studio.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 10/30/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
f1_keywords:
  - "sql13.swb.copilot.chat.f1"
# CustomerIntent: As a database administrator or database developer, I want to understand how to use the chat for Copilot in SQL Server Management Studio.
---

# Use the chat window for Copilot in SQL Server Management Studio

Copilot in SQL Server Management Studio (SSMS) includes a chat window to interact with Copilot in natural language. You can ask Copilot general questions about SQL, questions specific to a database, or get assistance writing or editing T-SQL.

Within the chat window, you determine the context for the prompt you submit. The context can be the general Copilot, or a specific database, based on an open query editor window. Within the context of a database, Copilot in SSMS has knowledge of both the context (SQL version) and database (schema aware), so responses are tailored to your environment.

> [!NOTE]  
> Queries from Copilot in SSMS are executed under the context of the user's login and permissions. There are no separate permissions for Copilot in SSMS.

## Get started

Once Copilot is configured, open the chat window using:

- **View** > **Copilot**
- **Ctrl**+**Alt**+**C**
- The **Copilot** button on the toolbar

The chat window is a tool window, like Object Explorer, that you can dock to any location within SSMS. To move the Copilot in tool window, select the title bar and drag it to another location.

Use **Ctrl** + mousewheel to increase or decrease the size of the text within the Copilot in SSMS tool window.

## Change context

If you initially open Copilot in SSMS without a connected query editor window, Copilot isn't connected to any database, but you can still ask general questions about SQL or SSMS. In this scenario, the current context is Copilot in SSMS.

To query a specific database, get help with Natural Language to SQL (NL2SQL), or get other assistance, open a query editor window that is connected to that database. The chat window automatically changes to the context of the new query editor. The context includes the name of the query editor and connection information.

To change Copilot's context, enter the `@` symbol in the prompt box to display the available context list. When context changes, the editor and connection are listed as the current context above the prompt box, and the **Sync Active Editor** option isn't selected.

To resynchronize with the active editor at any time, enable the **Sync Active Editor** option.

:::image type="content" source="media/copilot-in-ssms-chat/copilot-ssms-chat.png" alt-text="Screenshot of Copilot in SSMS chat window." lightbox="media/copilot-in-ssms-chat/copilot-ssms-chat.png":::

| Key | Description |
| --- | --- |
| 1 | Title bar |
| 2 | Tool window controls, to pin or close the Copilot window |
| 3 | Chat options, to export or clear chat history |
| 4 | Copilot response context |
| 5 | Submitted prompt |
| 6 | Feedback icons |
| 7 | Copilot response, including queries |
| 8 | Current context |
| 9 | Sync Active Editor option |
| 10 | Current mode |
| 11 | Prompt box |
| 12 | Status information |
| 13 | Prompt options, to view prompt history and submit a prompt |

## Submit a prompt

Enter your prompt in the prompt box, and select the arrow icon (**Send**) or Enter to submit it. The submitted prompt appears in the chat window. A **Thinking...** message can appear while Copilot waits for a response. The response returns beneath the prompt, with the response context at the top to help you track your conversation.

For NL2SQL prompts, Copilot queries the database metadata to provide context about the objects in your database.

If you open another query editor window, Copilot displays a message with instructions on how to change to that connection. It doesn't automatically change context to a newly opened window.

## View previous prompts

Copilot keeps track of your most recent prompts, available to select from the recent history icon (**Show Recent Questions**). From the available list, select any prompt and submit it again, or edit and then submit.

## Copy and insert Transact-SQL into the query editor

Responses from Copilot can include T-SQL statements, which are presented within the response and include **Copy** and **Insert** buttons. Use **Copy** to copy the T-SQL to the clipboard, and **Insert** to insert the T-SQL directly into the query editor. The insertion occurs based on the cursor location.

## Clear chat history

To reset or clear the chat history, use the broom icon (**Clear chat history**). This action erases all existing prompts and responses from the chat history, and they can't be retrieved. Previous information from the chat is lost, and you start the chat as if you opened Copilot for the editor for the first time.

## Save chat history

You can save chat history with the export icon (**Export**). Within the **Save As** dialog, browse to the location where you want to save the file. Edit the **File name** if necessary, then select **Save** to save the chat as a Markdown file.

Markdown files can be opened in SSMS 21, and rendered in Markdown format using the Markdown viewer. To invoke the viewer, use the Preview button or **Shift**+**F7**.

## Change database context

Copilot has context about the database to which you're connected in the query editor. If you want to connect to a different database in the same editor window, use the database dropdown list, or use T-SQL (for example, `USE WideWorldImporters;`). The first time you change database context, a message that the connection changed is logged in the chat. Every time the database context changes, the current context above the prompt box updates.

## Change mode

Copilot supports multiple modes for query execution, which can be changed in the prompt box with the appropriate command. The default mode is **Read only**.

| Mode | Command | Description |
| --- | --- | --- |
| Read Only | `/ro` | Only queries that read data are executed. |
| Read/Write with Approval | `/rwa` | Queries that read data are executed, and queries that write (modify data or schema) are executed after user approval. |
| Read Write | `/rw` | Queries that read data are executed, and queries that write (modify data or schema) are executed automatically (no approval required). |

For any mode in use, Copilot only has permission to execute statements that you, as the user, can execute. For example, you might not have permission to delete data from the `Sales.Orders` table. If you ask Copilot to write a statement that deletes data, such as `DELETE * FROM Sales.Orders`, when Copilot tries to execute the query, it fails.

To change the default mode for Copilot from **Read Only** to **Read/Write with Approval**, go to **Tools** > **Options** > **Copilot**. Use the dropdown list to change the value for **Default Execution Mode**. It isn't possible to set the **Default Execution Mode** to **Read Write**.

## Additional commands

Copilot offers commands to customize your experience, capture information, and adjust throughput.

| Name | Command | Description |
| --- | --- | --- |
| Style | `/style:` | Only queries that read data are executed. |
| Log | `/log` | Saves the information in the output window directly to a file in `%USERPROFILE%\AppData\Local\SSMSCopilot`. The output window can be displayed using **View** > **Output**. Select **Copilot** from the **Show output from:** dropdown list. |
| Set Max Results Token | `/mrt:` | Sets the maximum number of tokens that can be sent back to the model from T-SQL queries issued by Copilot. The default value is 75,000 tokens. If the token size is smaller than the data returned by the query, the model adjusts its response to indicate a limitation, such as "The list of all objects in the database is too large to process in a single query." |
| Set Max Tokens Per Minute | `/tpm:` | Sets the maximum number of tokens per minute that can send to the model by Copilot. This can be adjusted to protect against sending too much data to the model too quickly, exceeding the endpoints tokens per minute (TPM) capacity. |

Commands with a colon (`:`) require more information. For example, submitting the prompt `/style respond in the style of a super friendly assistant and use emojis` doesn't change the style.

For more information about Azure OpenAI token limits, see [Azure OpenAI in Azure AI Foundry Models quotas and limits](/azure/ai-services/openai/quotas-limits).

## Provide feedback

For each response from Copilot, you can provide positive (thumbs up) or negative (thumbs down) feedback. When you select either, a **Submit Feedback to Microsoft** dialog appears. Select the option or options that represent your feedback, then select **Submit**. Prompt and response information isn't shared with Microsoft when you submit feedback.

If you would like to provide more information, such as the prompt and response, select the option to provide more detail. After selecting **Submit**, the [feedback site for SSMS](https://aka.ms/ssms-feedback) opens in your browser and you can create a feedback ticket. For optimal assistance, include the chat history or the log file with the ticket. Alternatively, you can access the feedback site from **Help** > **Send Feedback** in SSMS.

## Related content

- [Code assistance for Copilot in SQL Server Management Studio](copilot-in-ssms-code-assistance.md)
- [Scenarios for Copilot in SQL Server Management Studio](copilot-in-ssms-scenarios.md)
