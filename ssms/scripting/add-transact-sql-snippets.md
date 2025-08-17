---
title: "Add Transact-SQL Snippets"
description: Learn how to add your own Transact-SQL code snippets to the set of predefined snippets included in SQL Server.
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/15/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---

# Add Transact-SQL snippets

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

You can add your own Transact-SQL code snippets to the set of predefined snippets included in [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)].

## Create a Transact-SQL snippet file

The first part of creating a [!INCLUDE [tsql](../includes/tsql-md.md)] code snippet is to create an XML file with the text of your code snippet. The file must have a `.snippet` file extension, and meet the requirements of the [Code Snippets Schema](/previous-versions/visualstudio/visual-studio-2015/ide/code-snippets-schema-reference). Set the snippet language to SQL.

You can use the predefined snippets that ship with [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] as examples. To find the predefined snippets, open SQL Server Management Studio, select the **Tools** menu, and select **Code Snippet Manager**. Select **SQL** in the **Language** list box, the path to the [!INCLUDE [tsql](../includes/tsql-md.md)] snippets is displayed in the **Location** box.

## Register the code snippet

After creating the snippet file, use the Code Snippets Manager to register the snippet with SQL Server Management Studio. You can either add a folder containing multiple snippets, or import individual snippets to the **My Code Snippets** folder.

## Procedures

### Add a snippet folder

1. Open SQL Server Management Studio.
1. Select the **Tools** menu, and select **Code Snippets Manager**.
1. Select the **Add** button.
1. Navigate to the folder containing your code snippets, and select the **Select Folder** button.

#### Import a snippet

1. Open SQL Server Management Studio.
1. Select the **Tools** menu, and select **Code Snippets Manager**.
1. Select the **Import** button.
1. Navigate to the folder containing your snippet, select the `.snippet` file, and select the **Open** button.

## Examples

The following example creates a `TRY...CATCH` surround-with snippet and imports it to SQL Server Management Studio.

1. Paste the following code into notepad, then save as a file named `TryCatch.snippet`.

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <CodeSnippets
       xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
       <_locDefinition
           xmlns="urn:locstudio">
           <_locDefault _loc="locNone" />
           <_locTag _loc="locData">Title</_locTag>
           <_locTag _loc="locData">Description</_locTag>
           <_locTag _loc="locData">Author</_locTag>
           <_locTag _loc="locData">ToolTip</_locTag>
           <_locTag _loc="locData">Default</_locTag>
       </_locDefinition>
       <CodeSnippet Format="1.0.0">
           <Header>
               <Title>TryCatch</Title>
               <Shortcut></Shortcut>
               <Description>Example Snippet for Try-Catch.</Description>
               <Author>SQL Server Documentation Example</Author>
               <SnippetTypes>
                   <SnippetType>SurroundsWith</SnippetType>
               </SnippetTypes>
           </Header>
           <Snippet>
               <Declarations>
                   <Literal>
                       <ID>CatchCode</ID>
                       <ToolTip>Code to handle the caught error</ToolTip>
                       <Default>CatchCode</Default>
                   </Literal>
               </Declarations>
               <Code Language="SQL">
                   <![CDATA[
      BEGIN TRY

      $selected$ $end$

      END TRY
      BEGIN CATCH

      $CatchCode$

      END CATCH;
      ]]>
               </Code>
           </Snippet>
       </CodeSnippet>
   </CodeSnippets>
   ```

1. Open SQL Server Management Studio.

1. Select the **Tools** menu, and select **Code Snippets Manager**.

1. Select the **Import** button.

1. Navigate to the folder containing `TryCatch.snippet`, select the `TryCatch.snippet` file, and select the **Open** button. You should now have a `TryCatch` snippet in your **My Code Snippets** folder.

## Related content

- [Insert Surround-with Transact-SQL snippets](insert-surround-with-transact-sql-snippets.md)
