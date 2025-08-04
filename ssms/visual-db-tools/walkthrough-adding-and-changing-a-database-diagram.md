---
title: Add and Change a Database Diagram
description: "Walkthrough: Add and change a database diagram"
author: rwestMSFT
ms.author: randolphwest
ms.date: 08/03/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "database diagrams [SQL Server], about database diagrams"
  - "database diagrams [SQL Server], designing"
  - "database diagrams [SQL Server], creating"
---
# Walkthrough: Add and change a database diagram

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

This walkthrough illustrates how to create and modify a database diagram and make changes to the database through the database diagrams component. You see how to add tables to diagrams, create relationships between tables, create constraints and indexes on columns, and change the level of information you see for each table.

## Prerequisites

In order to complete this walkthrough, you need:

- Access to [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] with the [!INCLUDE [ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database

- An account with database owner **dbo** privileges

> [!NOTE]  
> If you attempt to make changes when using an account without sufficient privileges to make changes to tables, then an error message appears.

## Create a diagram

### Create a new database diagram

1. On the **View** menu, select **Object Explorer**.

1. Open the Databases node and then open the [!INCLUDE [ssSampleDBobject](../includes/sssampledbobject-md.md)] node.

1. Right-click the Database Diagrams node and choose **New Database Diagram**.

   If the database doesn't have objects necessary to create diagrams, the following message appears: **This database doesn't have one or more of the support objects required to use database diagramming. Do you wish to create them?** Choose **Yes**.

   The **Add Table** dialog box appears.

1. Select **AddressType (Person)** and **Address (Person)** and select **Add**.

   Two tables are added to the diagram.

1. Close the **Add Table** dialog box.

### View different column data

1. Right-click the `Address` table. On the shortcut menu, point to **Table View**, and then select **Standard**.

   The table grid shows three columns: **Column Name**, **Data Type**, and **Allow Nulls**.

1. Right-click the `Address` table, select **Table View** and select **Keys**.

   The table grid shows one column, with the table-column names. Only those columns participating in indexes appear.

## Create new tables

### Create tables within Diagram Designer

1. Right-click the Diagram Designer outside the existing tables and choose **New Table**.

1. In the **Choose Name** dialog box, select **OK** to accept the default name **Table1**.

   A new table grid appears with three columns: **Column Name**, **Data Type**, and **Allow Nulls**.

1. Add the following information to **Table1**:

   | Column name | Data type | Allow nulls |
   | --- | --- | --- |
   | `T1col1` | **int** | checked |
   | `T1col2` | **varchar(50)** | checked |
   | `T1col3` | **float** | checked |

1. Right-click `T1col1` and select **Set Primary Key**.

   A key icon appears beside the column name.

1. From the **File** menu, select **Save Diagram1**.

1. In the **Choose Name** dialog box, select **OK** to accept the default name **Diagram1**.

1. The **Save** dialog box appears with a message that `Table1` is saved to the database. Select **Yes**.

## Modify table structure

You can add check constraints and make relationships between tables in Diagram Designer.

### Create check constraints

1. In `Table1`, right-click the `T1col3` row and choose **Check Constraints**.

   The **Check Constraints** dialog box appears.

1. Select **Add**.

   A new constraint appears in the **Selected Check Constraint** list, with the default name `CK_Table1`.

1. Select the **Expression** row in the grid and select the ellipsis button.

   The **Check Constraint Expression** dialog box appears.

1. Type **T1col3 > 5** and select **OK**.

   `Table1` now has a constraint that all values entered into `T1col3` must be greater than 5.

1. Select **Close**.

### Create relationships between tables

1. Create a new table in Diagram designer named `Table2` with the following columns:

   | Column name | Data type | Allow nulls |
   | --- | --- | --- |
   | `T2col1` | **int** | not checked |
   | `T2col2` | **varchar(50)** | checked |
   | `T2col3` | **xml** | checked |

   > [!NOTE]  
   > The columns on the primary key side of a foreign key relationship must participate in either a Primary Key or a Unique Constraint.

1. Drag `T2col1` to `T1col1`.

   Two dialog boxes appear: **Foreign Key Relationship** in the background and **Tables and Columns** in the foreground.

1. Select **OK** to save the new relationship.

1. Select **OK** again.

## Create indexes

You can create indexes on most types of data, including XML.

### Create a standard index

1. Right-click `Table1` and choose **Indexes/Keys**.

   The **Indexes/Keys** dialog box appears.

1. Select **Add**.

   A new index appears in the **Selected Primary/Unique Key or Index** list, with a default name similar to `IX_Table1`.

1. Select the **Columns** row and select the ellipsis button.

   The **Index Columns** dialog box appears.

1. Select the dropdown list arrow under **Column Name** and select `T1col2`.

   > [!NOTE]  
   > You might add additional columns to this index by selecting the cell below `T1col2` and choosing another column name.

1. Select **OK** to save this index.

1. Select **Close** in the **Indexes/Keys** dialog box.

### Create an XML index

1. Right-click `T2col1` and choose **Set Primary Key**.

   > [!NOTE]  
   > Adding an XML index requires that another column in the table be set as a clustered primary key.

1. Right-click the `T2col3` row in `Table2` and select **XML Indexes**.

   The **XML Indexes** dialog box appears.

1. Select **Add**.

   An XML index with default values is added to the **Selected XML Index** list.

1. Select **Close**.

   > [!NOTE]  
   > XML indexes are created per-column. The first XML index is primary; any additional indexes are secondary.

## Save the diagram

All of the changes you make to a diagram aren't posted to the database until you save it. If there are problems or conflicts, a dialog box appears with more information.

### Save a database diagram

1. On the **File** menu, select **Save Diagram1**.

   The **Save** dialog box appears. If **Warn about Tables Affected** is selected, information about new or changed tables is listed.

1. Select **OK**.

1. If any errors occurred, the **Post-Save Notifications** dialog box appears with the errors and their causes. Fix the errors and save the diagram again.

## Related content

- [Customize the amount of information displayed in diagrams (Visual Database Tools)](customize-the-amount-of-information-displayed-in-diagrams-visual-database-tools.md)
- [Set up Database Diagram Designer (Visual Database Tools)](set-up-database-diagram-designer-visual-database-tools.md)
- [Add tables to diagrams (Visual Database Tools)](add-tables-to-diagrams-visual-database-tools.md)
- [Create relationships between tables on a diagram (Visual Database Tools)](create-relationships-between-tables-on-a-diagram-visual-database-tools.md)
- [Create XML indexes](/sql/relational-databases/xml/create-xml-indexes)
- [Copy an image of a database diagram to the clipboard (Visual Database Tools)](copy-an-image-of-a-database-diagram-to-the-clipboard-visual-database-tools.md)
- [Work with diagram layout (Visual Database Tools)](work-with-diagram-layout-visual-database-tools.md)
