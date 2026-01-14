---
title: Rules for Entering Search Values
description: "Rules for entering search values (Visual Database Tools)"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
helpviewer_keywords:
  - "time [SQL Server], searches"
  - "date searches"
  - "dates [SQL Server], searches"
  - "embedding apostrophes [SQL Server]"
  - "logical value searches [SQL Server]"
  - "case-sensitive search matches"
  - "search criteria [SQL Server], rules"
  - "text value searches [SQL Server]"
  - "numeric value searches [SQL Server]"
---
# Rules for entering search values (Visual Database Tools)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

This article discusses the conventions you must use when entering the following types of literal values for a search condition:

- Text values
- Numeric values
- Dates
- Logical values

> [!NOTE]  
> The information in this article is derived from the rules for standard SQL-92. However, each database can implement SQL in its own way. Therefore, the guidelines provided here might not apply in every case. If you have questions about how to enter search values for a particular database, refer to the documentation for the database that you're using.

## Search on text values

The following guidelines apply when you enter text values in search conditions:

- **Quotation marks** Enclose text values in single quotation marks, as in this example for a last name:

  ```sql
  'Smith'
  ```

  If you're entering a search condition in the [Criteria Pane (Visual Database Tools)](criteria-pane-visual-database-tools.md), you can simply type the text value and the Query and View Designer automatically puts single quotation marks around it.

  > [!NOTE]  
  > In some databases, terms in single quotation marks are interpreted as literal values, whereas terms in double quotation marks are interpreted as database objects such as column or table references. Therefore, even though the Query and View Designer can accept terms in double quotation marks, it might interpret them differently than you expect.

- **Embedding apostrophes** If the data you're searching for contains a single quotation mark (an apostrophe), you can enter two single quotation marks to indicate that you mean the single quotation mark as a literal value and not a delimiter. For example, the following condition searches for the value "Swann's Way:"

  ```sql
  ='Swann''s Way'
  ```

- **Length limits** Don't exceed the maximum length of the SQL statement for your database when entering long strings.

- **Case sensitivity** Follow the case sensitivity rules for the database you're using. The database you're using determines whether text searches are case sensitive. For example, some databases interpret the operator "=" to mean an exact case-sensitive match, but others allow matches on any combination of uppercase and lowercase characters.

  If you're unsure about whether the database uses a case-sensitive search, you can use the UPPER or LOWER functions in the search condition to convert the case of the search data, as illustrated in the following example:

  ```sql
  WHERE UPPER(lname) = 'SMITH'
  ```

## Search on numeric values

The following guidelines apply when you enter numeric values in search conditions:

- **Quotation marks**

  Don't enclose numbers in quotation marks.

- **Non-numeric characters**

  Don't include non-numeric characters except the decimal separator (as defined in the **Regional Settings** dialog box of Windows Control Panel) and negative sign (-). Don't include digit grouping symbols (such as a comma between thousands) or currency symbols.

- **Decimal marks**

  If you're entering whole numbers, you can include a decimal mark, whether the value you're searching for is an integer or a real number.

- **Scientific notation**

  You can enter very large or very small numbers using scientific notation, as in this example:

  ```bash
  > 1.23456e-9
  ```

## Search on dates

The format you use to enter dates depends on the database you're using and in what pane of the Query and View Designer you're entering the date.

> [!NOTE]  
> If you don't know which format your data source uses, type a date into the filter column of the Criteria pane in any format familiar to you. The designer converts most of such entries into the appropriate format.

The Query and View Designer can work with the following date formats:

- **Locale-specific**

  The format specified for dates in the **Windows Regional Settings Properties** dialog box.

- **Database-specific**

  Any format understood by the database.

- **ANSI standard date**

  A format that uses braces, the marker 'd' to designate the date, and a date string, as in the following example:

  ```json
  { d '1990-12-31' }
  ```

- **ANSI standard datetime**

  Similar to ANSI-standard date, but uses 'ts' instead of 'd' and adds hours, minutes, and seconds to the date (using a 24-hour clock), as in this example for December 31, 1990:

  ```json
  { ts '1990-12-31 00:00:00' }
  ```

  In general, the ANSI standard date format is used with databases that represent dates using a true date data type. In contrast, the datetime format is used with databases that support a datetime data type.

The following table summarizes the date format that you can use in different panes of the Query and View Designer.

| Pane | Date format |
| --- | --- |
| Criteria | Locale-specific Database-specific ANSI standard<br /><br />Dates entered in the [Criteria Pane (Visual Database Tools)](criteria-pane-visual-database-tools.md) are converted to a database-compatible format in the SQL pane. |
| SQL | Database-specific ANSI standard |
| Results | Locale-specific |

## Search on logical values

The format of logical data varies from database to database. Very frequently, a value of False is stored as zero (0). A value of True is most frequently stored as 1 and occasionally as -1. The following guidelines apply when you enter logical values in search conditions:

- To search for a value of False, use a zero, as in the following example:

  ```sql
  SELECT *
  FROM authors
  WHERE contract = 0;
  ```

- If you aren't sure what format to use when searching for a True value, try using 1, as in the following example:

  ```sql
  SELECT *
  FROM authors
  WHERE contract = 1;
  ```

- Alternatively, you can broaden the scope of the search by searching for any non-zero value, as in the following example:

  ```sql
  SELECT *
  FROM authors
  WHERE contract <> 0;
  ```

## Related content

- [Specify search criteria (Visual Database Tools)](specify-search-criteria-visual-database-tools.md)
