---
title: Roadmap for SQL Server Management Studio
description: Roadmap for SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, mbarickman
ms.date: 01/30/2026
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
ai-usage: ai-assisted
---

# SQL Server Management Studio product roadmap

In the 2025 calendar year, SSMS had an unprecedented number of releases - 23 in total (including previews, major releases, and minor releases). Since the GA release of SSMS 22, we've continued our commitment to evolve SSMS into a modern, consistent, and complete management tool for SQL Server and SQL databases across the Microsoft data platform. We're focused on extending support for [Database DevOps (Preview) in SQL Server Management Studio](database-devops.md), advancing the connection experience for all SQL databases, and investing in improvements for IntelliSense and T-SQL formatting, to provide a better experience in the query editor. We're also continuing our investment in AI-powered tooling to further ehance productivity and make intelligent recommendations more accessible throughout the management workflow.

## How we build our roadmap

When planning future SSMS updates, we focus on two primary inputs:

- **Platform requirements**: These include updates required to stay aligned with the latest drivers, libraries, and Visual Studio platform dependencies. This ensures that SSMS continues to support modern security, compatibility, and performance standards.

- **User feedback**: We actively monitor suggestions and issues [submitted by our community](https://aka.ms/ssms-feedback), which help shape feature priorities and usability improvements. You're encouraged to *vote* on feedback items that affect your workflow, which helps us understand impact across the community. We also look at votes and comments on suggestions, to determine which new features are most important to users and why.

## SSMS roadmap

The following areas represent key investments we plan to make in future releases of SSMS. This roadmap is intended to provide a general sense of direction, and is subject to change.

### Customer feedback

Customer feedback continues to be an important part of our focus. Key areas we're actively looking to improve include the connection dialog and IntelliSense, and we'll look to add support for [formatting T-SQL](https://developercommunity.visualstudio.com/t/Format-SQL-code-using-SQL-Server-Managem/10857083).

### Evolution of SQL Projects

SSMS 22.4.1 introduced SQL Projects (preview). In subsequent releases of SSMS, SQL Projects capabilities will continue to evolve and introduce support for schema comparison, alignment with migration and modernization efforts, and advancing the CLI surface to enable users and AI agents to drive the database development lifecycle.

### Performance and stability improvements

We know from customer feedback how critical performance and stability are to your day-to-day workflow. We're continuing to improve performance and stability of SSMS, and our efforts are informed by data and customer feedback reports.

### Advancement of AI experiences

With GitHub Copilot in SSMS generally available, we'll turn our efforts to Agent Mode to support advanced administrative tasks, query optimization, and troubleshooting.
