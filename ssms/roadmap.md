---
title: Roadmap for SQL Server Management Studio
description: Roadmap for SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, mbarickman
ms.date: 01/16/2026
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
ai-usage: ai-assisted
---

# SQL Server Management Studio product roadmap

In the 2025 calendar year, SSMS had an unprecedented number of releases - 23 in total (including previews, major releases, and minor releases). After the GA release of SSMS 22, we're taking time to continue our commitment to evolving SSMS into a modern, consistent, and complete management tool for SQL Server and SQL databases across the Microsoft data platform. We're focused on extending support for [!INCLUDE [sssql25-md](includes/sssql25-md.md)], continuing to integrate with Fabric SQL experiences, and expanding our efforts related to theming and Arm64 support. We're also continuing our investment in AI-powered tooling enhancements to improve productivity and make intelligent recommendations more accessible throughout the management workflow.

## How we build our roadmap

When planning future SSMS updates, we focus on two primary inputs:

- **Platform requirements**: These include updates required to stay aligned with the latest drivers, libraries, and Visual Studio platform dependencies. This ensures that SSMS continues to support modern security, compatibility, and performance standards.

- **User feedback**: We actively monitor suggestions and issues [submitted by our community](https://aka.ms/ssms-feedback), which help shape feature priorities and usability improvements. You're encouraged to vote on feedback items that affect your workflow, which helps us understand impact across the community. We also look at votes and comments on suggestions, to determine which features are most important to users and why.

## SSMS roadmap

The following areas represent key investments we plan to make in future releases of SSMS. This roadmap is intended to provide a general sense of direction, and is subject to change.

### Customer feedback

Customer feedback continues to be an important part of our focus. Key improvements we're actively investigating include [adding more export options to the results grid](https://developercommunity.microsoft.com/t/Quick-Export-Options-in-SSMS-Query-Resul/10853468) and expanding our support of [group by schema in Object Explorer](https://developercommunity.microsoft.com/t/Group-objects-by-schema-in-Object-Explor/10874158).

### Continued support for SQL Server 2025

SSMS 22 introduced significant support for [!INCLUDE [sssql25-md](includes/sssql25-md.md)]. We maintain close collaboration with [!INCLUDE [ssnoversion-md](includes/ssnoversion-md.md)] teams to continue to provide rich end-to-end experience in SSMS for new features as they become available.

### Arm64 support

SSMS 22 introduced initial support for Arm64 operating systems. We're continuing to expand that support to other experiences, including replication, SQL Server Integration Services (SSIS), and more.

### Performance and stability improvements

We know from customer feedback how critical performance and stability are to your day-to-day workflow. We're spending time to deeply investigate, plan, and improve performance and stability of SSMS, and our efforts are informed by data and customer feedback reports.

### Evolution of AI experiences

With the GitHub Copilot in SSMS in preview, expect further efforts to bring intelligent, context-aware experiences to your daily workflow. This includes enhancements to code completion, administrative tasks, query optimization, and troubleshooting.
