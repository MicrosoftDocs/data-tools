---
title: Format T-SQL in SSMS
titleSuffix: SQL Server Management Studio
description: Learn how to format SQL code in SQL Server Management Studio (SSMS), including format on demand, format on save, and configuring formatting options with .editorconfig files.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: drskwier, mbarickman
ms.date: 06/17/2026
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

- [SSMS 22.7 or later](../install/install.md)

## Format on demand

You can format T-SQL in any query editor window at any time. The formatter can apply to the entire document or only a selected section of text.

To format SQL on demand, use one of the following methods:

- **Context menu**: Right-click in a T-SQL editor window and select **Format SQL (Preview)**.
- **Edit menu**: Select **Edit** > **Advanced** > **Format SQL (Preview)**.
- **Keyboard shortcut**: Press **Ctrl+K**, **Ctrl+Q**.

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

| Key | Type | Default | Description |
| --- | --- | --- | --- |
| `align_clause_bodies` | bool | `true` | Align bodies of `FROM`, `WHERE`, `GROUP BY`, and similar clauses. |
| `align_column_definition_fields` | bool | `true` | Align column-definition fields, such as name, type, and constraints. |
| `align_set_clause_item` | bool | `true` | Align `SET` clause items in `UPDATE` statements. |

#### Paths

| Key | Type | Default |
| --- | --- | --- |
| `allow_external_language_paths` | bool | `true` |
| `allow_external_library_paths` | bool | `true` |

#### Formatting

| Key | Type | Values | Default | Description |
| --- | --- | --- | --- | --- |
| `format_on_save` | bool | | `false` | Auto-format on save (SSMS-only, not in ScriptDOM). |
| `as_keyword_on_own_line` | bool | | `true` | Place `AS` on its own line. |
| `include_semicolons` | bool | | `false` | Append semicolons to statements. |
| `keyword_casing` | enum | `Uppercase` `Lowercase` `PascalCase` | `Uppercase` | Keyword casing style. |
| `preserve_comments` | bool | | `true` | Preserve comments during formatting. |

#### Indentation

| Key | Type | Default | Description |
| --- | --- | --- | --- |
| `indent_set_clause` | bool | `false` | Indent `SET` clause in `UPDATE` statements. |
| `indentation_size` | int (1–8) | `4` | Spaces per indent level. |
| `indent_view_body` | bool | `false` | Indent `VIEW` body. |

#### Multiline

| Key | Type | Default | Description |
| --- | --- | --- | --- |
| `multiline_insert_sources_list` | bool | `true` | `INSERT` sources as multiline. |
| `multiline_insert_targets_list` | bool | `true` | `INSERT` columns as multiline. |
| `multiline_select_elements_list` | bool | `true` | `SELECT` columns as multiline. |
| `multiline_set_clause_items` | bool | `true` | `SET` items as multiline. |
| `multiline_view_columns_list` | bool | `true` | `VIEW` columns as multiline. |
| `multiline_where_predicates_list` | bool | `true` | `WHERE` predicates as multiline. |

#### New Line

| Key | Type | Default |
| --- | --- | --- |
| `new_line_before_close_parenthesis_in_multiline_list` | bool | `true` |
| `new_line_before_from_clause` | bool | `true` |
| `new_line_before_group_by_clause` | bool | `true` |
| `new_line_before_having_clause` | bool | `true` |
| `new_line_before_join_clause` | bool | `true` |
| `new_line_before_offset_clause` | bool | `true` |
| `new_line_before_open_parenthesis_in_multiline_list` | bool | `false` |
| `new_line_before_order_by_clause` | bool | `true` |
| `new_line_before_output_clause` | bool | `true` |
| `new_line_before_where_clause` | bool | `true` |
| `new_line_before_window_clause` | bool | `true` |
| `newline_formatted_check_constraint` | bool | `false` |
| `newline_formatted_index_definition` | bool | `false` |
| `num_newlines_after_statement` | int (0–5) | `1` |

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
