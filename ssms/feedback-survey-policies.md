---
title: Configure Feedback Group Policies for SQL Server Management Studio
description: Configure group policies that control submission of feedback and survey responses for enterprise deployments of SQL Server Management Studio (SSMS)
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 05/20/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
keywords:
  - "feedback policy ssms, feedback policies ssms"
  - "SQL Server Management Studio feedback policy"
  - "SSMS feedback policy"
---
# Configure feedback group policies for SQL Server Management Studio

SQL Server Management Studio (SSMS) 21 and later versions allows you to configure and deploy global machine-wide policies across your organization. Deployment occurs by using the [Microsoft Intune settings catalog](/intune/intune-service/configuration/settings-catalog) or by importing [Visual Studio Administrative Templates (ADMX)](/visualstudio/install/administrative-templates) into legacy tools like Group Policy editor. For more information, see [Configure policies for enterprise deployments of Visual Studio](/visualstudio/install/configure-policies-for-enterprise-deployments).

One of the main categories included in the Visual Studio ADMX templates is feedback. Feedback Group Policies can be used to control the types of feedback sent through SSMS. IT administrators might find these policies useful to control whether SSMS users in their organization are permitted to submit feedback or survey responses to Microsoft. By default, users can submit both feedback and survey responses through SSMS.

## Supported policies

Two feedback group policies exist for SSMS.

| Name | Description |
| --- | --- |
| `SurveysDisabled` | Controls whether the user receives survey links in SSMS. If enabled, SSMS and the Visual Studio Installer don't display any product survey requests or links to surveys to the user. |
| `ProductFeedbackDisabled` | Controls whether the user can submit feedback through SSMS. If enabled, SSMS and the Visual Studio Installer don't allow users to submit feedback to Microsoft. Examples include, but aren't limited to reporting feedback, submitting suggestions, and providing feedback on features via a thumbs up/down control. |

## Related content

- [Visual Studio Administrator Templates (ADMX)](/visualstudio/install/administrative-templates)
- [Configure policies for enterprise deployments of Visual Studio](/visualstudio/install/configure-policies-for-enterprise-deployments)
