---
title: Format T-SQL in SSMS
titleSuffix: SQL Server Management Studio
description: Learn how to format SQL code in SQL Server Management Studio (SSMS), including format on demand, format on save, and configuring formatting options with .editorconfig files.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: mahyon, mbarickman
ms.date: 09/28/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
ai-usage: ai-assisted
---

# Format Transact-SQL in SSMS

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw-fabricse-fabricdw-fabricsqldb.md)]

Consistent formatting makes Transact-SQL (T-SQL) easier to read, review, and maintain, especially when multiple people contribute to the same codebase. SQL Server Management Studio (SSMS) includes a built-in SQL formatter (Preview) that you can run on demand, configure for automatic formatting on save, and customize through SSMS settings or `.editorconfig` files.

The SQL formatting functionality in SSMS is built on top of [ScriptDOM](https://github.com/microsoft/sqlscriptdom), an open-source .NET library that parses T-SQL and generates scripts based on abstract syntax trees.

## Prerequisites

- [SQL Server Management Studio](../install/install.md) 22.7 or a later version

## Format on demand

You can format T-SQL in any query editor window at any time. The formatter can apply to the entire document or only a selected section of text.

To format SQL on demand, use one of the following methods:

- **Context menu**: Right-click in a T-SQL editor window and select **Format SQL (Preview)**.
- **Edit menu**: Select **Edit** > **Advanced** > **Format SQL (Preview)**.
- **Keyboard shortcut**: Press <kbd>Ctrl</kbd>+<kbd>K</kbd>, <kbd>Ctrl</kbd>+<kbd>Q</kbd>.

When you select text, the formatter applies only to the selection. When you don't select text, the formatter applies to the entire document.

## Format on save

When you turn on the **Format on Save** option, the formatter automatically applies your configured formatting options every time you save a `.sql` file. Format on save works with named or saved query editor windows and with files in [SQL database projects](/sql/tools/sql-database-projects/sql-database-projects). Format on save keeps your SQL files consistent across pull requests and code reviews.

To enable format on save for all files:

1. Select **Tools** > **Options**.
1. Go to **SQL Formatter (Preview)** > **Formatting**.
1. Set **Format on Save** to **True**.
1. Select **OK**.

You can also set `format_on_save = true` in an `.editorconfig` file to enable format on save for all `.sql` files in your project or folder. For more information, see [.editorconfig file](#editorconfig-file).

## Configure formatting options

The formatter supports a range of options that control how your SQL is styled, such as keyword casing, indentation size, semicolons after statements, and line breaks for clauses like `FROM`, `WHERE`, and `JOIN`. You can configure these options in two ways: through SSMS settings or through an `.editorconfig` file.

When both an SSMS setting and an `.editorconfig` value exist for the same option, the `.editorconfig` value takes precedence. This precedence allows you to set your preferred defaults in SSMS and override them per-project or per-folder with an `.editorconfig` file.

### SSMS settings

To configure formatting options in SSMS:

1. Select **Tools** > **Options**.
1. Go to **SQL Formatter (Preview)**.
1. Adjust the settings in the subcategories: **General**, **Alignment**, **Paths**, **Formatting**, **Indentation**, **Multiline**, **New Line**, and **Spacing**.
1. Select **OK**.

### .editorconfig file

You can define formatting options in an [`.editorconfig`](https://editorconfig.org/) file placed in your project or folder. SSMS reads these values and applies them as overrides on top of the SSMS settings.

All SQL formatter keys go under `[*.sql]` in `.editorconfig`.

#### General

| Key | Type | Values | Default |
| --- | --- | --- | --- |
| `sql_version` | enum | `Sql80` `Sql90` `Sql100` `Sql110` `Sql120` `Sql130` `Sql140` `Sql150` `Sql160` `Sql170` | `Sql170` |
| `sql_engine_type` | enum | `All` `Standalone` `SqlAzure` | `All` |

#### Alignment

| Key | Type | Values | Default | Description |
| --- | --- | --- | --- | --- |
| `align_clause_bodies` | bool | | `true` | Align bodies of `FROM`, `WHERE`, `GROUP BY`, and similar clauses. |
| `align_column_definition_fields` | bool | | `true` | Align column-definition fields, such as name, type, and constraints. |
| `align_set_clause_item` | bool | | `true` | Align `SET` clause items in `UPDATE` statements. |
| `clause_body_alignment` | enum | `Aligned` `Indented` | `Aligned` | Controls whether clause bodies are aligned with the clause keyword or placed on the next line and indented. |

#### Formatting

| Key | Type | Values | Default | Description |
| --- | --- | --- | --- | --- |
| `as_keyword_on_own_line` | bool | | `true` | Place `AS` on its own line. |
| `built_in_function_casing` | enum | `Preserve` `Uppercase` `Lowercase` `PascalCase` | `Preserve` | Controls the casing of built-in function names. |
| `column_alias_style` | enum | `AsKeyword` `EqualsSign` `Preserve` | `Preserve` | Render column aliases using the `AS` keyword, an equals sign, or preserve the original style. |
| `comma_placement` | enum | `Trailing` `Leading` | `Trailing` | Place commas at the end of the line (trailing) or the start of the next line (leading) in multiline lists. |
| `format_on_save` | bool | | `false` | Auto-format on save (SSMS-only, not in ScriptDOM). |
| `identifier_bracketing` | enum | `Preserve` `IncludeBrackets` `ExcludeBrackets` | `Preserve` | Controls whether square brackets around identifiers are preserved, added, or removed. |
| `identifier_casing` | enum | `Preserve` `Uppercase` `Lowercase` `PascalCase` | `Preserve` | Controls the casing applied to identifiers. |
| `keyword_casing` | enum | `Uppercase` `Lowercase` `PascalCase` | `Uppercase` | Keyword casing style. |
| `leading_comma_space_count` | int | (0 - 1) | `1` | Controls the number of spaces inserted after a leading comma. |
| `preserve_comments` | bool | | `true` | Preserve comments during formatting. |
| `terminate_block_statements` | bool | | `false` | Controls whether block statements end with a semicolon. |

#### Indentation

| Key | Type | Values | Default | Description |
| --- | --- | --- | --- | --- |
| `indent_set_clause` | bool | | `false` | Indent `SET` clause in `UPDATE` statements. |
| `indent_view_body` | bool | | `false` | Indent `VIEW` body. |
| `indentation_mode` | enum | `Spaces` `Tabs` | `Spaces` | Indent using spaces or tab characters. |
| `indentation_size` | int | (1 - 8) | `4` | Spaces per indent level. |

#### Multiline

| Key | Type | Default | Description |
| --- | --- | --- | --- |
| `multiline_group_by_elements_list` | bool | `true` | `GROUP BY` elements on separate lines. |
| `multiline_having_predicates_list` | bool | `true` | `HAVING` predicates on separate lines. |
| `multiline_in_values_list` | bool | `true` | `IN` expression values on separate lines. |
| `multiline_insert_sources_list` | bool | `true` | `INSERT` sources as multiline. |
| `multiline_insert_targets_list` | bool | `true` | `INSERT` columns as multiline. |
| `multiline_nested_function_calls` | bool | `true` | Parameters in nested function calls on separate lines. |
| `multiline_order_by_elements_list` | bool | `true` | `ORDER BY` elements on separate lines. |
| `multiline_partition_by_elements_list` | bool | `true` | `PARTITION BY` elements on separate lines. |
| `multiline_procedure_parameters_list` | bool | `true` | Stored procedure parameters on separate lines. |
| `multiline_select_elements_list` | bool | `true` | `SELECT` columns as multiline. |
| `multiline_set_clause_items` | bool | `true` | `SET` items as multiline. |
| `multiline_view_columns_list` | bool | `true` | `VIEW` columns as multiline. |
| `multiline_where_predicates_list` | bool | `true` | `WHERE` predicates as multiline. |
| `multiline_with_options_list` | bool | `true` | Options in `WITH` and `OPTION` clauses on separate lines. |

#### New Line

| Key | Type | Default |
| --- | --- | --- |
| `new_line_after_join_keyword` | bool | `true` |
| `new_line_before_close_parenthesis_in_multiline_list` | bool | `true` |
| `new_line_before_from_clause` | bool | `true` |
| `new_line_before_group_by_clause` | bool | `true` |
| `new_line_before_having_clause` | bool | `true` |
| `new_line_before_join_clause` | bool | `true` |
| `new_line_before_offset_clause` | bool | `true` |
| `new_line_before_on_clause` | bool | `true` |
| `new_line_before_open_parenthesis_in_multiline_list` | bool | `false` |
| `new_line_before_order_by_clause` | bool | `true` |
| `new_line_before_output_clause` | bool | `true` |
| `new_line_before_where_clause` | bool | `true` |
| `new_line_before_window_clause` | bool | `true` |
| `newline_formatted_check_constraint` | bool | `false` |
| `newline_formatted_index_definition` | bool | `false` |
| `num_newlines_after_batch_statement` | int (0 - 10) | `2` |
| `num_newlines_after_batches` | int (0 - 10) | `1` |
| `num_newlines_after_statement` | int (0 - 10) | `1` |

#### Spacing

| Key | Type | Default | Description |
| --- | --- | --- | --- |
| `space_between_data_type_and_parameters` | bool | `true` | Space between data type and parens, for example `VARCHAR (255)` |
| `space_between_parameters_in_data_type` | bool | `true` | Space between params in data types |

#### Example .editorconfig

The following example shows an `.editorconfig` file that sets a few commonly customized options. Any properties not specified in the file fall back to the SSMS settings.

```ini
[*.sql]
keyword_casing                                      = lowercase
include_semicolons                                  = true
indentation_size                                    = 2
multiline_select_elements_list                      = true
new_line_before_from_clause                         = true
```

## Share feedback

The SQL formatting functionality in SSMS is built on top of the open-source .NET library for T-SQL parsing, [ScriptDOM](https://github.com/microsoft/sqlscriptdom). Use the GitHub issues system in the ScriptDOM repository to discuss ideas and challenges. Pull requests are welcome.

Submit SSMS feedback through **Help** > **Send Feedback** in SSMS or through the [Developer Community feedback channel](https://aka.ms/ssms-feedback).

## Related content

- [Manage code formatting](manage-code-formatting.md)
- [SQL database projects](/sql/tools/sql-database-projects/sql-database-projects?view=sql-server-ver17&preserve-view=true)
- [ScriptDOM GitHub repository](https://github.com/microsoft/sqlscriptdom)
