---
title: "Replace Template Parameters"
description: "Replace Template Parameters"
author: rwestMSFT
ms.author: randolphwest
ms.date: "01/19/2017"
ms.service: sql-server-management-studio
ms.topic: conceptual
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.swb.templates.replaceparameters.f1"
helpviewer_keywords:
  - "template parameters [Template Explorer]"
  - "templates [Transact-SQL], replacing parameters"
  - "Replace (Query) Template Parameters dialog box"
  - "replacing template parameters"
---
# Replace Template Parameters
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW](../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]
Templates contain parameters that can be replaced by implementation-specific values each time the template is used. After opening a template in a code editor, you can replace the parameters with values relevant to your implementation.  
  
## Before You Begin  
The **Specify Values for Template Parameters** dialog is a grid with three columns. The **Parameter** and **Type** columns are read-only and cannot be changed. Review the contents of the **Value** column, and change any of the defaults to values appropriate for your implementation.  
  
To use this dialog box, you must have parameters in your script enclosed in angle brackets (`< >`) in the format `<`*parameter_name*`,` *data_type*`,` *default_value*`>`.  
  
## Replace Template Parameters  
After opening the template in a code editor window:  
  
1.  On the **Query** menu, click **Specify Values for Template Parameters**.  
  
2.  In the **Specify Values for Template Parameters** dialog box, the **Values** column contains a suggested value for each parameter. Accept the value or replace it with a new value.  
  
3.  Click **OK** to close the **Specify Values for Template Parameters** dialog box and modify the script in the query editor.  
  
## See Also  
[Template Explorer](template-explorer.md)  
[Open a Template](open-a-template.md)  
  
