---
title: Get Full Memory Dump to Troubleshoot SSMS
description: "Get full memory dump"
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: maghan, randolphwest
ms.date: 06/26/2025
ms.service: sql-server-management-studio
ms.topic: troubleshooting-general
ms.collection:
  - data-tools
---

# Get a full memory dump to troubleshoot SSMS

In this article, you learn how to capture diagnostic information to troubleshoot a crash or an unresponsive system that you experience in SQL Server Management Studio (SSMS).

## Get a full memory dump after an unresponsive system or crash

Get a full memory dump of SQL Server Management Studio (SSMS) when it stops responding or crashes.

To capture diagnostic information to troubleshoot a crash or an unresponsive SSMS, use the following steps:

1. Download [ProcDump](/sysinternals/downloads/procdump).
1. Unzip the download into a folder.
1. Open a Command Prompt (such as `cmd.exe`), and run the following command.

    ```console
    <PathToProcDumpFolder>\procdump.exe -e -h -ma -w ssms.exe
    ```

    It should prompt you to accept a license agreement, select **Agree**.

1. Start SQL Server Management Studio (SSMS) if not started already.
1. Reproduce your issue.
1. Wait as the text appears in the cmd prompt about writing the dump file, don't proceed until it finishes.
1. Create a new folder and copy the *.dmp file that is written out to that folder.
1. Copy the following files into the same folder.

    * "C:\Windows\Microsoft.NET\Framework\v4.0.30319\mscordacwks.dll"
    * "C:\Windows\Microsoft.NET\Framework\v4.0.30319\SOS.dll"
    * "C:\Windows\Microsoft.NET\Framework\v4.0.30319\clr.dll"

1. Zip up the folder.

## Get a full memory dump using Visual Studio

There are scenarios where trying to capture a full memory dump for SSMS doesn't generate the expected output, and it requires advanced troubleshooting.

The following steps require [Visual Studio](https://visualstudio.microsoft.com/vs/community/)(Community Edition or higher) to be installed.

To capture a diagnostic information with Visual Studio to troubleshoot a crash or an unresponsive SSMS, use the following steps:

1. Open Visual Studio.
1. Select **Continue without code** to open an empty window.
1. Start SSMS, if it's not already open.
1. Select **Debug > Attach to Process...**.
1. In the **Attach to Process** dialog, within the **Filter processes** box, enter SSMS.
1. In the list of processes select SSMS.exe and then **Attach**.
1. An Output window appears, with **Debug** selected for **Show output from:**.
1. Recreate the problematic behavior in SSMS.
1. Once SSMS closes, select **Debug** > **Save Dump As...** in Visual Studio and save the `.dmp` file to a folder.
1. Zip up the folder.
1. Stop debugging before closing Visual Studio.

## OutOfMemoryException

You can also get the Full Memory Dump of SSMS when it throws an OutOfMemoryException (can be any managed exception).

To capture diagnostic information to troubleshoot an OutOfMemoryException from SSMS, use the following steps:

1. Download [ProcDump](/sysinternals/downloads/procdump).
1. Unzip the download into a folder.
1. Open Command Prompt and run the following command.

    ```cmd
    <PathToProcDumpFolder>\procdump.exe -e 1 -f System.OutOfMemoryException -ma -w ssms.exe
    ```

    It should prompt you to accept a license agreement, select **Agree**.

1. Start SQL Server Management Studio if not started already.
1. Repro the issue.
1. Wait as the text appears in the cmd prompt about writing the dump file, don't proceed until it finishes.
1. Create a new folder and copy the *.dmp file that is written out to that folder.
1. Copy the following files into the same folder.

    * "C:\Windows\Microsoft.NET\Framework\v4.0.30319\mscordacwks.dll"
    * "C:\Windows\Microsoft.NET\Framework\v4.0.30319\SOS.dll"
    * "C:\Windows\Microsoft.NET\Framework\v4.0.30319\clr.dll"

1. Zip up the folder.

## Share the information

1. To share information with the SSMS Team, create a feedback item on the [SSMS user feedback site](https://aka.ms/ssms-feedback).
1. Attach the memory dump to the feedback item. The dump file can be submitted using a private message so they are not publicly available.
 
    > [!Important]
    > Memory dump files may contain sensitive information.

## Related content

- [Advanced troubleshooting for SQL Server Management Studio (SSMS)](ssms-troubleshoot.md)
- [SQL Server Management Studio (SSMS) setup failed or requires restarting the machine](install-failed-requires-restart.md)
- [SQL Server Management Studio](../sql-server-management-studio-ssms.md)
