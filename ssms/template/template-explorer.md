---
title: "Template Explorer"
description: "Template Explorer"
author: rwestMSFT
ms.author: randolphwest
ms.date: "01/19/2017"
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.templates.explorer.f1"
  - "sql13.wb.templates.f1"
helpviewer_keywords:
  - "templates [SQL Server]"
  - "SQL Server Management Studio [SQL Server], Template Explorer"
  - "Template Explorer"
  - "templates [Transact-SQL]"
  - "templates [SQL Server], Template Explorer"
---

# Template Explorer

[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]
[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provides a variety of templates. Templates are boilerplate files containing SQL scripts that help you create objects in a database. The first time the template explorer is opened, a copy of the templates are placed in the user's folder in C:\Users, under AppData\Roaming\Microsoft\SQL Server Management Studio\130\Templates.  
  
You can browse the available templates in Template Explorer, then open a template to incorporate the code into a code editor window. You can also create custom templates.  
  
## Benefits of Templates  
Templates are available for solutions, projects, and various types of code editors. Templates are available to create objects like databases, tables, views, indexes, stored procedures, triggers, statistics, and functions. In addition, there are templates that help you to manage your server by creating extended properties, linked servers, logins, roles, users, and templates for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].  
  
The template scripts provided with SQL Server Management Studio contain parameters to help you customize the code. When you open a template, Use the **Specify Values for Template Parameters** dialog box to insert values into the script.  
  
Create custom templates for tasks you perform frequently. Organize your custom scripts into the existing folders or create a new folder structure.  
  
The [!INCLUDE[ssDE](../includes/ssde-md.md)] Query editor also supports code snippets, which can be inserted at specific locations in a script by right-clicking at that location.  
  
## Related Tasks  
Use the following topics to get started with templates  
  
|**Description**|**Topic**|  
|-------------------|-------------|  
|Describes how to incorporate the code from a template into a code editor window.|[Open a Template](open-a-template.md)|  
|Describes how to replace template parameter values after opening a template in a code editor.|[Replace Template Parameters](replace-template-parameters.md)|  
  
