---
title: "Spatial Results Window"
description: Learn how to use the Spatial results window, which provides visual mapping tools for viewing spatial data. To view spatial results your query results must include a spatial column with either geometry or geography data.
author: rwestMSFT
ms.author: randolphwest
ms.date: "03/01/2017"
ms.service: sql-server-management-studio
ms.topic: conceptual
ms.collection:
  - data-tools
---
# Spatial Results Window
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]
  The **Spatial results** window provides visual mapping tools for viewing spatial data. To view spatial results, your query results must include a spatial column with either geometry or geography data.  
  
> [!NOTE]  
>  The **Spatial results** window is only available if your results are returned to a grid in the **Results** window. If you specify that your results are returned as text, this window is not available.  
  
## Options  
 **Select spatial column**  
 Specify the spatial column you want to view from the spatial columns in the query results. Only one column can be selected at a time.  
  
 **Select label column**  
 Specify the non-spatial column from the columns returned in the query results to label the spatial data. Only one column can be selected at a time.  
  
 This option is not available when only point instances are returned in a query.  
  
 **Select projection**  
 Display geography data in one of four projections: Equirectangular, Mercator, Robinson, or Bonne.  
  
 This option is not available for geometry data.  
  
 **Zoom**  
 Adjust the map display on an exponential scale.  
  
 **Show grid lines**  
 Toggle coordinate gridlines on or off.  
  
 For polygon shapes, the label is displayed only when the shape is large enough to hold the label text. To display labels for small shapes, adjust the zoom.  
  
> [!NOTE]  
>  Point instances cannot be labeled.  
  
## See Also  
 [View Spatial Data in Object Explorer](view-spatial-data-in-object-explorer.md)   
 [Spatial Data &#40;SQL Server&#41;](/sql/relational-databases/spatial/spatial-data-sql-server)   
 [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../f1-help/database-engine-query-editor-sql-server-management-studio.md)   
 [Query and Text Editors &#40;SQL Server Management Studio&#41;](../f1-help/database-engine-query-editor-sql-server-management-studio.md)  
  
