---
title: Roadmap for SQL Server Management Studio
description: Roadmap for SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: maghan, randolphwest, mbarickman
ms.date: 07/24/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
ai-usage: ai-assisted
---

# SQL Server Management Studio product roadmap

Following the GA release of SSMS 21, we continue our commitment to delivering a modern, consistent, and capable management tool for SQL Server and SQL databases across the Microsoft data platform. We're focused on enabling support for SQL Server 2025, deepening integration with Fabric SQL experiences, and expanding platform capability with an initial focus enabling Arm64 support. We're also continuing our investment in AI-powered tooling enhancements to improve productivity and make intelligent recommendations more accessible throughout the management workflow.

## How we build our roadmap

When planning future SSMS updates, we focus on two primary inputs:

- **Platform requirements**: These include updates required to stay aligned with the latest drivers, libraries, and Visual Studio platform dependencies. This ensures that SSMS continues to support modern security, compatibility, and performance standards.

- **User feedback**: We actively monitor suggestions and issues [submitted by our community](https://aka.ms/ssms-feedback), which help shape feature priorities and usability improvements.

## SSMS roadmap

The following areas represent key investments we plan to make in future releases of SSMS. This roadmap is intended to provide a general sense of direction, and is subject to change.

### Support for SQL Server 2025

Following the [!INCLUDE [sssql25-md](includes/sssql25-md.md)] announcement, we're working to bring full support for [!INCLUDE [sssql25-md](includes/sssql25-md.md)] to SSMS, with enhancements to ensure compatibility with new engine capabilities and management features.

### Integration with SQL experiences in Microsoft Fabric

We're continuing to enhance the SSMS experience for Microsoft Fabric. We're building on early integration work to provide a more cohesive and productive environment for managing Fabric SQL workloads, aligning the SSMS experience with the Fabric web editor.

### Continued investment in AI experiences

With Copilot in SSMS in preview, expect further efforts to bring intelligent, context-aware experiences to your development workflow. This includes enhancements to code assistance, diagnostics, and recommendations powered by AI.

### Arm64 support

A highly requested item from the community, we're taking an important step toward Arm64 compatibility by exploring options to ensure SSMS can function effectively on Arm64 devices.
