---
title: Advanced Troubleshooting for SQL Server Management Studio
description: Capture diagnostic data for a SQL Server Management Studio (SSMS) problem or crash
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: maghan, randolphwest
ms.date: 07/08/2025
ms.service: sql-server-management-studio
ms.topic: troubleshooting-general
ms.collection:
  - data-tools
---

# Advanced troubleshooting for SQL Server Management Studio

This article provides information on how to troubleshoot SQL Server Management Studio (SSMS).

## Capture logs

There are multiple logs that can be captured within SSMS using the Output window.

1. Go to **Tools** > **Options** > **Output Window**.
1. Enable the relevant channels. For a description of the channels, see [Options (Output Window - General)](../menu-help/options-output-window-page.md).
1. Select **OK**.
1. If necessary, restart SSMS.
1. Select **View** > **Output** to display the Output window.
1. Complete the steps or task for which you want to capture logs.
1. Save the output from each channel to its own `.txt` file.

## Enable verbose logging

The information logged from SSMS doesn't always provide enough detail for troubleshooting, and verbose logging can be enabled to capture more details.

1. Determine the location of the SSMS executable (`ssms.exe`). The default location for SSMS 21 is `C:\Program Files\Microsoft SQL Server Management Studio 21\Release\Common7\IDE`, but might be different on your machine.

1. Open a command prompt and run the following two commands, using the `ssms.exe` location in the previous step for the second line.

   ```cmd
   SET VsLogActivity=1
   "C:\Program Files\Microsoft SQL Server Management Studio 21\Release\Common7\IDE\ssms.exe"
   ```

1. SSMS starts.

1. Open Windows Explorer and navigate to %USERPROFILE%\AppData\Roaming\Microsoft\SSMS.

1. Close SSMS to stop the verbose logging.

1. Find the folder with the most recent date. Within that folder, inspect the ActivityLog.xml file, which now contains more details that can assist with troubleshooting.

## Clear SSMS cache files

Data stored in cache files might unexpectedly interfere with SSMS behavior. To rule out this problem, you can clear the files manually.

1. Close all instances of SSMS.

1. Remove all files in the following folders, after making a copy of the `RegSrvr*.xml` file to retain any entries under **Local Server Groups** in **Registered Servers**.

   - `%USERPROFILE%\AppData\Local\Microsoft\SQL Server Management Studio`
   - `%USERPROFILE%\AppData\Roaming\Microsoft\SQL Server Management Studio`

1. Start SSMS and observe if removing the cache files resolved the issue.

## Share the information

1. To share log information with the SSMS Team, create a feedback item on the [SSMS user feedback site](https://aka.ms/ssms-feedback).

1. Attach the log files to the feedback item. The files can be submitted using a private message so they aren't publicly available.

   > [!IMPORTANT]  
   > Log files might contain sensitive information.

## Related content

- [Get a full memory dump to troubleshoot SSMS](get-full-memory-dump.md)
- [SQL Server Management Studio (SSMS) setup failed or requires restarting the machine](install-failed-requires-restart.md)
- [What is SQL Server Management Studio (SSMS)?](../sql-server-management-studio-ssms.md)
