---
title: "XML Editor (SQL Server Management Studio)"
description: Learn how to use the visual tools of the SQL Server Management Studio XML Editor to work with XML schemas (XSDs), ADO.NET datasets, and XML documents.
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/15/2025
ms.service: sql-server-management-studio
ms.topic: article
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.editor.xml.f1"
  - "sql13.swb.editorxml.f1"
  - "vs.xmleditor"
  - "sql13.swb.xmleditor.f1"
helpviewer_keywords:
  - "XML Designer [SQL Server Management Studio]"
---

# XML editor (SQL Server Management Studio)

[!INCLUDE [SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

Provides a set of visual tools for working with XML Schemas, ADO.NET datasets, and XML documents. The XML Designer supports the XML Schema Definition (XSD) language defined by the World Wide Web Consortium (WC3). The designer doesn't support DTDs (document type definitions) or other XML schema languages, such as XDR (XML-Data Reduced).

To display the designer, add a dataset, XML Schema, or XML file to your project or open any of the file types listed in the following table.

> [!CAUTION]  
> There's no **Undo** command when working in Schema view. Plan your work carefully and save your files often.

The designer provides the following three views (or modes) to work on XML files, XML Schemas, and datasets:

| View | Description | File types supported |
| --- | --- | --- |
| **Schema** | Visually create and modify XML Schemas and ADO.NET datasets. | `.xsd` |
| **Data** | Visually modify XML data files in a structured data grid. | `.xml` |
| **XML** | Edit XML; the source editor provides color-coding and IntelliSense, including complete word and list members. | `.xml`, `.xsd`, `.xslt`, `.wsdl`, `.web`, `.resx`, `.tdl`, `.wsf`, `.hta`, `.disco`, `.vsdisco`, `.config` |
| **ShowPlan** | Displays XML query plans created using the `SET SHOWPLAN_XML ON` option. | `.showplan` |

## Schema view

Schema view provides a visual representation of the elements, attributes, types, and so on, that make up XML Schemas and ADO.NET datasets.

In Schema view you can construct schemas and datasets by dropping elements on the design surface from either the XML Schema tab of the Toolbox or from Server Explorer. Additionally, you can add elements to the designer by right-clicking the design surface and selecting Add from the shortcut menu.

In Schema view you can:

- Construct and modify existing XML Schemas and ADO.NET datasets
- Create and edit relationships between tables
- Create and edit keys
- Generate ADO.NET datasets from XML Schemas

> [!NOTE]  
> The layout of elements in Schema view is stored in the `.xsx` file, which can be seen by selecting **Show All Files** in the Solution Explorer toolbar, and then expanding the `.xsd` file. If there's no `.xsx` file present, it means the `.xsd` file was never opened in the XML Designer.

### Customize Schema view

The following features modify the visual layout of elements in Schema view:

- Zooming
- Expanding or collapsing of nested elements
- Automatically arranging layout of elements
- Resetting default state of collapsed elements

#### Expand hidden nested elements

Select the plus icon on the bottom of the element.

#### Collapse nested elements

Select the minus icon on the bottom-most element that you want to appear on the designer.

## Data view

Data view provides a data grid that can be used to modify `.xml` files. Only the content (but not the tags and structure) in an XML file can be edited in Data view.

There are two separate areas in Data view: **Data Tables** and **Data**. The **Data Tables** area is a list of relations defined in the XML file, in the order of its nesting (from the outermost to the innermost). The **Data** area is a data grid that displays data based on the selection in the Data Tables area.

> [!NOTE]  
> Newly created XML files contain no data and therefore can't be displayed in Data view. There are also some instances of XML documents where data view can't be invoked at all. Although the XML would be considered well formed, if it isn't structured data, trying to switch to Data view generates the following message:

```output
Although this document is well formed, it contains structure that Data View cannot display.
```

In Data view you can:

- Manually populate data tables
- Edit existing data tables
- Generate an XML Schema from an XML document

## XML view

XML view provides an editor for editing raw XML and provides IntelliSense and color coding. Statement completion is available when working on `.xsd` files and `.xml` files that have an associated schema. Type < to initiate a tag and you're presented with a list of elements that are valid at that location. After you type the element name and press the SPACEBAR, you're presented with a list of attributes that the element supports.

> [!NOTE]  
> [!INCLUDE [msCoName](../includes/msconame-md.md)] IntelliSense options aren't available on the toolbar. When in the XML Editor, to access the options, on the **Edit** menu, select **IntelliSense**.

## SHOWPLAN view

Query plans can be saved in XML format when created using `SET SHOWPLAN_XML ON` option. Double-click a file with the `.showplan` extension to open the query plan.

## Related content

- [Save an Execution Plan in XML Format](/sql/relational-databases/performance/save-an-execution-plan-in-xml-format)
