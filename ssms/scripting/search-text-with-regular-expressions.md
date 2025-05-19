---
title: "Search Text with Regular Expressions"
description: "Learn how to use regular expressions in the Find what field of a Find and Replace dialog box to specify a pattern to be matched."
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: randolphwest
ms.date: 05/19/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
f1_keywords:
  - "vswildcardsbuilder"
  - "vsregexbuilder"
helpviewer_keywords:
  - "searches [SQL Server Management Studio], wildcards"
  - "Query Editor [SQL Server Management Studio], wildcard searches"
  - "wildcard options [SQL Server Management Studio]"
  - "searches [SQL Server Management Studio], regular expressions"
  - "Query Editor [SQL Server Management Studio], regular expression searches"
  - "regular expression options [SQL Server Management Studio]"
  - "searches [SQL Server Management Studio], regex"
  - "Query Editor [SQL Server Management Studio], regex searches"
  - "regex options [SQL Server Management Studio]"
---

# How to search text with regular expressions

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

The following regular expressions can replace characters or digits in the **Find what** field of the [!INCLUDE [ssManStudioFull](../includes/ssmanstudiofull-md.md)] **Find and Replace** dialog box.

## Prerequisites

- [Install SQL Server Management Studio](../install/install.md)

## How to enable regular expressions

Here are steps to enable regular expressions in search.

1. Go to **Edit** > **Find and Replace** > **Quick Find**.
1. Next to the search bar select the *down arrow* > **Find in Files**.
1. In the **Find and Replace** window, expand **Find options**, and select **Use Regular Expressions**.

The **Expression Builder** button next to the **Find what** field then becomes available. Select this button to display a list of the available regular expressions. When you choose any item from the **Expression Builder**, it is inserted into the **Find what** string.

The following table describes some of the regular expressions in the **Expression Builder**.

| Expression | Description |
| --- | --- |
| `.` | Match any single character (except a line break) |
| `.*` | Match any character zero or more times |
| `.+` | Match any character one or more times |
| `[abc]` | Match any character in the set `abc` |
| `[^abc]` | Match any character not in the set `abc` |
| `\d` | Match any numeric character |
| `(?([^\r\n])\s)` | Match any whitespace character |
| `\b` | Match at the beginning or end of the word |
| `^` | Match at beginning of line |
| `.$` | Match any line break |
| `\w\r?\n` | Match a word character at end of line |
| `(dog | cat)` | Capture and implicitly number the expression `dog | cat` |
| `(?<pet>dog | cat)` | Capture subexpression `dog | cat` and name it `pet` |

## Examples

Some examples of using regular expressions.

### Example 1: Find all select statements

You want to find all `SELECT` statements in your T-SQL scripts.

  ```sql
  SELECT\s+.*\s+FROM
  ```

#### Example 1 explanation

- `SELECT\s+`: Matches the word `SELECT` followed by one or more whitespace characters.
- `.*`: Matches any character (except for line terminators) zero or more times.
- `\s+FROM`: Matches one or more whitespace characters followed by the word `FROM`.

### Example 2: Find procedures with specific naming patterns

You want to find all stored procedures that start with `usp_` in your T-SQL scripts.

  ```sql
  CREATE\s+PROCEDURE\s+usp_[A-Za-z0-9_]+
  ```

#### Example 2 explanation

- `CREATE\s+PROCEDURE\s+`: Matches the words `CREATE PROCEDURE` followed by one or more whitespace characters.
- `usp_`: Matches the literal string `usp_`.
- [A-Za-z0-9_]+: Matches one or more alphanumeric characters or underscores.

### Example 3: Find comments in T-SQL scripts

You want to identify all single-line comments (starting with `--`) in your T-SQL scripts.

  ```sql
  --.*
  ```

#### Example 3 explanation

- `--`: Matches the literal string `--`.
- `.*`: Matches any character (except for line terminators) zero or more times.

### Example 4: Find all update statements

You want to find all the `UPDATE` statements in your T-SQL scripts.

  ```sql
  UPDATE\s+.*\s+SET
  ```

#### Example 4 explanation

- `UPDATE\s+`: Matches the word `UPDATE` followed by one or more whitespace characters.
- `.*`: Matches any character (except for line terminators) zero or more times.
- `\s+SET`: Matches one or more whitespace characters followed by the word `SET`.

### Example 5: Find table names in DDL statements

You want to extract table names from `CREATE TABLE` statements in your T-SQL scripts.

```sql
CREATE\s+TABLE\s+(\w+)
```

#### Example 5 explanation

- `CREATE\s+TABLE\s+`: Matches the words `CREATE TABLE` followed by one or more whitespace characters.
- `(\w+)`: Matches one or more word characters (alphanumeric and underscore) and captures them for extraction.

For more examples, visit [Regular Expressions in Visual Studio](/visualstudio/ide/using-regular-expressions-in-visual-studio)

## Related content

- [Search and Replace](search-and-replace.md)
- [Search Documents Interactively](search-documents-interactively.md)
- [Search Documents Using Results Lists](search-documents-using-results-lists.md)
