---
title: System Requirements for SQL Server Management Studio
description: Learn about the system requirements for SQL Server Management Studio (SSMS) on Windows.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan, mbarickman
ms.date: 06/02/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
keywords:
  - "requirements ssms, system requirements ssms"
  - "SQL Server Management Studio requirements"
  - "SSMS system requirements"
---
# System requirements for SQL Server Management Studio

[!INCLUDE [ssms-21-md](includes/ssms-21-md.md)] is a powerful tool for managing SQL Server instances, Azure SQL databases, and Azure SQL managed instances. This document outlines the system requirements needed to install and run [!INCLUDE [ssms-21-md](includes/ssms-21-md.md)] effectively.

Ensure your system meets these requirements to take full advantage of the features and capabilities of SQL Server Management Studio (SSMS). For more information about [!INCLUDE [ssms-21-md](includes/ssms-21-md.md)], see [Release notes for SQL Server Management Studio (SSMS)](release-notes-21.md).

## Download SQL Server Management Studio 21

To download the latest version of [!INCLUDE [ssms-21-md](includes/ssms-21-md.md)], see [Install SQL Server Management Studio](install/install.md). For instructions on installing and updating [!INCLUDE [ssms-21-md](includes/ssms-21-md.md)], see [Update SQL Server Management Studio](install/update.md). Also, see instructions on how to [install offline](install/create-offline.md).

[Download SSMS 21](https://aka.ms/ssms/21/release/vs_SSMS.exe)

## SQL Server Management Studio system requirements

[!INCLUDE [ssms-21-md](includes/ssms-21-md.md)] is supported on the following 64-bit operating systems:

- Windows 11 minimum supported OS version or higher: Home, Pro, Pro Education, Pro for Workstations, Enterprise, and Education
  - For supported Windows 11 versions, see [Windows 11 Enterprise and Education Support](/lifecycle/products/windows-11-enterprise-and-education)
- Windows 10 minimum supported OS version or higher: Home, Professional, Education, and Enterprise.
  - For supported Windows 10 versions, see [Windows 10 Enterprise and Education Support](/lifecycle/products/windows-10-enterprise-and-education)
- Windows Server 2025: Standard and Datacenter.
- Windows Server 2022: Standard and Datacenter.
- Windows Server 2019: Standard and Datacenter.
- Windows Server 2016: Standard and Datacenter.

The following operating systems aren't supported:

- 32-bit, Arm32, and Arm64 operating systems.
- [Windows 11 Home in S mode](https://support.microsoft.com/windows/windows-10-and-windows-11-in-s-mode-faq-851057d6-1ee9-b9e5-c30b-93baebeebc85#WindowsVersion=Windows_11), [Windows Enterprise IoT](/windows/iot/product-family/windows-iot), [Windows 10 IoT Core](/windows/iot-core/windows-iot), [Windows 10 Enterprise LTSC edition](/windows/deployment/update/waas-overview), [Windows 10 S](https://support.microsoft.com/windows/windows-10-and-windows-11-in-s-mode-faq-851057d6-1ee9-b9e5-c30b-93baebeebc85), and [Windows 10 Team Edition](/surface-hub).
- Server IoT and Minimal Server Interface options for Windows Server.
- Windows containers.
- Running in virtual machine environment without a full Windows operating system.
- Application virtualization solutions such as Microsoft App-V or MSIX for Windows, or third-party app virtualization technologies.
- Multiple simultaneous users using the software on the same machine, including shared virtual desktop infrastructure machines or a pooled Windows Virtual Desktop hostpool.

### Hardware

- x64 processor; Quad-core or better recommended.
  - Arm64 processors aren't supported.
  - Arm32 processors aren't supported.
- Minimum of 4-GB of RAM. Many factors impact resources used; we recommend 16-GB RAM for typical professional solutions.
- Hard disk space: Minimum of 4-GB up to 50-GB of available space, depending on features installed; typical installations require 20-50 GB of free space. We recommend installing Windows and SSMS on a solid-state drive (SSD) to increase performance.
- Video card that supports a minimum display resolution of WXGA (1366 by 768); SSMS works best at a resolution of 1920 by 1080 or higher.
  - Minimum resolution assumes zoom, DPI settings, and text scaling are set at 100%. If not set to 100%, minimum resolution should be scaled accordingly. For example, if you set the Windows display **Scale and layout** setting on your Surface Book, which has a 3000x2000 physical display, to 200%, then SSMS would see a logical screen resolution of 1500x1000, meeting the minimum 1366x768 requirement.

### Supported languages

[!INCLUDE [ssms-21-md](includes/ssms-21-md.md)] is available in English, Chinese (Simplified), Chinese (Traditional), Czech, French, German, Italian, Japanese, Korean, Polish, Portuguese (Brazil), Russian, Spanish, and Turkish. You can select the language of SSMS during installation. The Visual Studio Installer is available in the same 14 languages, and matches the language of Windows, if available.

### Additional requirements and guidance

- Administrator rights are required to install or update [!INCLUDE [ssms-21-md](includes/ssms-21-md.md)].
- Refer to [Create an offline installation of SQL Server Management Studio](install/create-offline.md) for guidance on how to install, deploy, update, and configure SQL Server Management Studio in an offline scenario.
- .NET Framework 4.7.2 or above is required to *install* [!INCLUDE [ssms-21-md](includes/ssms-21-md.md)]. [!INCLUDE [ssms-21-md](includes/ssms-21-md.md)] requires .NET Framework 4.8 to run. If .NET Framework 4.8 isn't already installed, it's installed during setup.
- Team Foundation Server 2019 Office Integration requires Office 2016, Office 2013, or Office 2010.
- Smart App Control, which is a Windows feature, isn't recommended to be enabled on machines. Any setting other than "off" might negatively impact SQL Server Management Studio performance.

## Related content

- [Install SQL Server Management Studio](install/install.md)
- [Modify SQL Server Management Studio workloads, components, and language packs](install/modify.md)
- [Create an offline installation of SQL Server Management Studio](install/create-offline.md)
- [Use command-line parameters to install SQL Server Management Studio](install/command-line-parameters.md)
