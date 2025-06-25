---
title: "Scenarios"
titleSuffix: Copilot in SQL Server Management Studio
description: Learn about example scenarios for Copilot in SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 05/19/2025
ms.update-cycle: 180-days
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - ce-skilling-ai-copilot
# CustomerIntent: As a database administrator or database developer, I want to understand various scenarios where I can leverage Copilot in SQL Server Management Studio.
---
# Scenarios for Copilot in SQL Server Management Studio

Copilot in SSMS is an advanced AI tool designed to assist users of SQL Server Management Studio (SSMS) with managing and developing SQL databases. Whether you're a database administrator, database developer, application administrator, business analyst, or somewhere in between, Copilot in SSMS can save you time and help you become more efficient in your workflow.

Use Copilot in SSMS to answer questions about databases in SQL Server, Azure SQL Database, Azure SQL Managed Instance, or SQL Database in Fabric. You can also request assistance with writing Transact-SQL (T-SQL) queries using *natural language* (NL2SQL). Copilot can also assist with error messages, documenting, explaining, and fixing T-SQL queries.

## Database and environment exploration

Ask Copilot any question, in any order, in the sidecar chat. For example:

- `What version of SQL is this?`
- `List the databases on this instance.`
- `List server configuration settings that have been changed from the default in table format with the setting and current value`
- `How do I find out who is connected to this database?`
- `What is the compatibility mode for the database?`
- `hat's the largest table in the database?`
- `What columns store email addresses?`
- `How many customers do we have and where are they located?`
- `Have any SQL Agent jobs have failed in the last week and if so, which ones?`

## Multi-turn experience

Ask Copilot a series of questions, with each subsequent question related to, or in response to, a previous answer. For example:

- `What is the compatibility mode for this database?`
- `What is the latest compatibility mode available for this version of SQL?`
- `How do I change the compatibility mode?`
- `How will this change affect query performance?`
- `Give me step-by-step instructions for testing a change in compatibility mode for a query without changing the compatibility mode for the entire database.`

## Multi-turn experience with scripting

When asking Copilot a series of questions, you can also ask it to create queries related to the topic.

- `What is a database backup?`
- `What is the difference between a full and log backup?`
- `How do I create a database backup?`
- `Does my database need a transaction log backup?`
- `How do I create a transaction log backup?`
- `Create the script to backup the database`
- `How do I automate backups?`
- `What should my backup schedule be if the RPO is 30 minutes?`
- `Create the script to create SQL Agent jobs for the recommended backup schedule`

## Use Copilot for help with Transact-SQL

Copilot in SSMS has context based on your query editor connection, but it currently doesn't have direct access to the query editor. Specifically, typing in a blank editor doesn't invoke Copilot assistance. In addition, it currently can't read directly from the editor (if you have something highlighted) or copy something to it.

### Write Transact-SQL

Copilot can assist with writing T-SQL using the prompt you provide (natural language to T-SQL, or NLtoSQL) within the sidecar chat.

- `Write a query to return sales information for the last week`
- `Write a query to find all the customers who placed orders in July 2024 that totaled more than $1000 and order based on total descending`
- `Write the query to change the ReferenceID column in the Tickets table from an INT to a VARCHAR(25)`
- `Give me the query to find how much space is being used in tempdb`
- `Give me the query to find all open transactions`

### Get help writing T-SQL queries as a multi-turn experience

In addition to asking Copilot for help with writing a query, you can ask for assistance with query development in the chat, in the same way that you might write the query yourself.

- `How many customers spent over $100000 in 2023?`
- `Give me the query you ran to find that information`
- `Take the inner query and change it to select customer ID, customer name, and total spent and order it by total spent descending`
- `I forgot I want to include the state where the company is located in the output, please update the query to add that`

## Approve queries for Copilot to execute

By default, Copilot runs in a read-only mode. Copilot only executes queries that read data. However, you can change the mode to **Read/Write with Approval** using the `/rwa` command in the chat.

1. Change the mode:

   `/rwa`

1. Ask Copilot to update statistics that are out of date:

   `Update statistics that are out of date`

1. Provide more details to Copilot so it can perform the correct analysis:

   `List the name of statistics that haven't been updated in over a week that have more than 10% data changed for all tables in the database`

1. Copilot lists the statistics, and asks if you want to update them. If it doesn't ask, you can tell it to update the statistics.

1. Copilot provides the T-SQL for the update, and gives the option to select **Run** or **Cancel**.

1. Select **Run** to have Copilot update statistics.

## Use Copilot for database development

Copilot can help you quickly develop objects in your database in the **Read/Write** mode. To enable **Read/Write** mode, use the `/rw` command.

1. Change the mode:

   `/rw`

1. Ask Copilot to create a set of tables for the database:

   `We're designing a database for a fictional company called Contoso Wireless. They are similar to existing wireless companies in the sense that they sell cell phones, accessories, phone plans, chargers, headsets, and more. Can you suggest some tables that will support my application? This application will support browsing a website, creating orders, paying bills, tracking customer activity, tracking usage, etc. Please provide scripts to create all the tables you see fit and make sure each table has a clustered index for the primary key.`

1. Ask Copilot to create indexes:

   `Are there any indexes you think I need based on the kinds of queries that we will run to find data?`

1. Ask Copilot to create sample data:

   `We need to generate data for each of the tables. Each table should have 100-1000 rows. The data needs to be realistic (we can't repeat names, products, etc.). Can you help generate scripts for that? It's ok if the scripts are long. Variability in the data is more important than having a short script. For the customers table, use a combination of 50 first names and 50 last names and also use 30 different city/state combinations.`

## Other examples

You can ask Copilot any question about SQL or writing T-SQL. Always review scripts before execution, as AI can make mistakes.

- `List the 10 largest tables in the database based on row count in a bulleted list`

- `What are the file sizes for this database, their file growth settings, and how much free space do they have?`

- `What are the worst performing queries for the last hour?`

- `What queries executed most frequently in the last two hours?`

- `List all employes and their email address in comma delimited format`

- `What are the top 5 products ordered the most in 2024?`

- `Calculate the total number of orders for each company in 2023`

- `Create a table named Offices in the Sales schema. It should have the columns officeID, office name, address, city, state, zip code, and office manager ID which is foreign key to the People table.`

## Related content

- [Use the chat window for Copilot in SQL Server Management Studio](copilot-in-ssms-chat.md)
- [Code assistance for Copilot in SQL Server Management Studio](copilot-in-ssms-code-assistance.md)
