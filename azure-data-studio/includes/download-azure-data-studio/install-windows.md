---
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest, maghan
ms.date: 07/25/2025
ms.service: azure-data-studio
ms.topic: include
---

### Windows installation

[!INCLUDE [ssms-azure-data-studio-install](../ssms-azure-data-studio-install.md)]

This release of Azure Data Studio includes a standard Windows installer experience and a .zip file.

We recommend the *user installer*, which simplifies installations and updates and doesn't require administrator privileges because the location is under your user Local AppData (LOCALAPPDATA) folder.

The user installer also provides a smoother background update experience. For more information, see [User setup for Windows](https://code.visualstudio.com/updates/v1_26#_user-setup-for-windows).

#### [User installer](#tab/win-user-install)

**User installer** (recommended)

1. Download and run the [x64](https://go.microsoft.com/fwlink/?linkid=2324624) or [Arm64](https://go.microsoft.com/fwlink/?linkid=2324717) user installer for Windows.

1. Start the Azure Data Studio app.

#### [System installer](#tab/win-system-install)

**System installer**

1. Download and run the [x64](https://go.microsoft.com/fwlink/?linkid=2324716) or [Arm64](https://go.microsoft.com/fwlink/?linkid=2324523) system installer for Windows.

1. Start the Azure Data Studio app.

#### [.zip install](#tab/win-zip-install)

**.zip file**

1. Download the latest [x64](https://go.microsoft.com/fwlink/?linkid=2324522) or [Arm64](https://go.microsoft.com/fwlink/?linkid=2324718) `.zip` file for Windows.

1. Go to the downloaded file and extract it.

1. Run `\azuredatastudio-windows\azuredatastudio.exe`.

#### [winget install](#tab/winget-install)

**winget (Windows Package Manager CLI)**

1. Install the [Windows Package Manager Client](/windows/package-manager/winget) if you don't already have it.
1. Run the following command to install **Azure Data Studio**.

   ```cmd
   winget install "azure data studio"
   ```

#### [Unattended install](#tab/win-unattended-install)

You can also install Azure Data Studio by using a command prompt script.

For Windows, install Azure Data Studio in the background without prompts using the following steps:

1. Open the command prompt window with elevated permissions.

1. Run the following command:

   ```console
   <path where the azuredatastudio-windows-user-setup-x.xx.x.exe file is located> /VERYSILENT /MERGETASKS=!runcode>
   ```

   Example:

   ```console
   %systemdrive%\azuredatastudio-windows-user-setup-1.24.0.exe /VERYSILENT /MERGETASKS=!runcode
   ```

   > [!NOTE]  
   > The following example also works with the system installer file.

   > ```console
   > <path where the azuredatastudio-windows-setup-x.xx.x.exe file is located> /VERYSILENT /MERGETASKS=!runcode>
   > ```
   >
   > In the preceding code, you can also pass */SILENT* instead of */VERYSILENT* to see the setup user interface.

1. If you've run the commands successfully, you can see Azure Data Studio installed.
