---
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest, maghan
ms.date: 02/06/2025
ms.service: azure-data-studio
ms.topic: include
---

### Linux installation

You can install Azure Data Studio on Red Hat Enterprise Linux (RHEL), SUSE Linux Enterprise Server (SLES), Ubuntu, Debian, and Windows Subsystem for Linux (WSL).

#### [RHEL](#tab/redhat-install)

> [!NOTE]
>  Azure Data Studio installation failure is a known issue on RHEL 8. Manually install glibc-2.29 and add it to the Library Path and then re-install ADS to resolve the issue.

#### Install using .tar.gz file

1. Download Azure Data Studio for Linux by using the [.tar.gz](https://azuredatastudio-update.azurewebsites.net/latest/linux-x64/stable) file.

1. To extract the file, open a new terminal window, and then run the following commands:

   ```bash
   cd ~
   cp ~/Downloads/azuredatastudio-linux-<version string>.tar.gz ~
   tar -xvf ~/azuredatastudio-linux-<version string>.tar.gz
   ```

1. Move the extracted folder to `/opt` for system-wide availability:
   
   ```bash
   sudo mv ~/azuredatastudio-linux-x64 /opt/azuredatastudio
   ```

1. Create a symbolic link for easier command-line access:
   
   ```bash
   sudo ln -s /opt/azuredatastudio/azuredatastudio /usr/local/bin/azuredatastudio
   ```

1. (Optional) Add Azure Data Studio to the GNOME application menu:

   ```bash
   sudo tee /usr/share/applications/azuredatastudio.desktop > /dev/null <<EOL
   [Desktop Entry]
   Name=Azure Data Studio
   Exec=/opt/azuredatastudio/azuredatastudio
   Icon=/opt/azuredatastudio/resources/app/resources/linux/code.png
   Type=Application
   Categories=Development;Database;
   StartupWMClass=azuredatastudio
   EOL
   ```

1. Update the desktop database:

   ```bash
   sudo update-desktop-database
   ```

1. To start Azure Data Studio, run this command:

   ```bash
   azuredatastudio
   ```

If you have missing dependencies, install them with the following command:

```bash
sudo yum install libxss1 libgconf-2-4 libunwind8
```

#### [SLES](#tab/suse-install)

1. Download Azure Data Studio for SUSE Linux Enterprise Server by using the [.rpm](https://azuredatastudio-update.azurewebsites.net/latest/linux-rpm-x64/stable) file.

1. Install it using:

   ```bash
   sudo zypper install ./Downloads/azuredatastudio-linux-<version string>.rpm
   ```

1. To start Azure Data Studio, run:

   ```bash
   azuredatastudio
   ```

If you have missing dependencies:

```bash
sudo zypper install libXScrnSaver
```

#### [Ubuntu and Debian](#tab/ubuntu-install)

#### Install using .tar.gz file

1. Download Azure Data Studio for Ubuntu or Debian by using the [.tar.gz](https://azuredatastudio-update.azurewebsites.net/latest/linux-x64/stable) file.

1. To extract the file, open a new terminal window, and then run the following commands:

    ```bash
    cd ~
    cp ~/Downloads/azuredatastudio-linux-<version string>.tar.gz ~
    tar -xvf ~/azuredatastudio-linux-<version string>.tar.gz
    ```

1. Move the extracted folder to `/opt`:
   
   ```bash
   sudo mv ~/azuredatastudio-linux-x64 /opt/azuredatastudio
   ```

1. Create a symbolic link:
   
   ```bash
   sudo ln -s /opt/azuredatastudio/azuredatastudio /usr/local/bin/azuredatastudio
   ```

1. (Optional) Add Azure Data Studio to the GNOME application menu:

   ```bash
   sudo tee /usr/share/applications/azuredatastudio.desktop > /dev/null <<EOL
   [Desktop Entry]
   Name=Azure Data Studio
   Exec=/opt/azuredatastudio/azuredatastudio
   Icon=/opt/azuredatastudio/resources/app/resources/linux/code.png
   Type=Application
   Categories=Development;Database;
   StartupWMClass=azuredatastudio
   EOL
   ```

1. Update the desktop database:

   ```bash
   sudo update-desktop-database
   ```

1. To start Azure Data Studio, run:

    ```bash
    azuredatastudio
    ```

If you have missing dependencies:

```bash
sudo apt-get install libxss1 libgconf-2-4 libunwind8
```

#### [Windows Subsystem for Linux](#tab/windows-install)

1. Install Azure Data Studio for Windows. Then, use the `azuredatastudio` command in a Windows Subsystem for Linux (WSL) terminal just as you would in a standard command prompt. By default, the application is stored in your *AppData* folder.

1. Start Azure Data Studio from the WSL command prompt:

   ```bash
   /mnt/c/Users/<your user name>/AppData/Local/Programs/Azure Data Studio/azuredatastudio.exe
   ```
   When you're using the default Windows installation, start the application by running the following command. Replace `<your user name>` with your user name: