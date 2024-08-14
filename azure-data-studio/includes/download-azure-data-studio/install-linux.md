---
author: markingmyname
ms.author: maghan
ms.date: 10/17/2023
ms.service: azure-data-studio
ms.topic: include
---

### Linux installation

You can install Azure Data Studio on Red Hat Enterprise Linux (RHEL), SUSE Linux Enterprise Server (SLES), Ubuntu, Debian, and Windows Subsystem for Linux (WSL).

#### [RHEL](#tab/redhat-install)

> [!NOTE]
>  Azure Data Studio installation failure is a known issue on RHEL 8. Manually install glibc-2.29 and add it to the Library Path and then re-install ADS to resolve the issue.

#### Install using .rpm file

1. Download Azure Data Studio for Red Hat Enterprise Linux by using the [.rpm](https://azuredatastudio-update.azurewebsites.net/latest/linux-rpm-x64/stable) file.

1. To extract the file, open a new terminal window, and then run the following commands:

   ```bash
   cd ~
   sudo yum install ./Downloads/azuredatastudio-linux-<version string>.rpm
   ```

1. To start Azure Data Studio, run this command:

   ```bash
   azuredatastudio
   ```

If you have missing dependencies, run this command:

```bash
yum install libXScrnSaver
```

#### Install using .tar.gz file

1. Download Azure Data Studio for Red Hat Enterprise Linux by using the [.tar.gz](https://azuredatastudio-update.azurewebsites.net/latest/linux-x64/stable) file.

1. To extract the file, open a new terminal window, and then run the following commands:

   ```bash
   cd ~
   cp ~/Downloads/azuredatastudio-linux-<version string>.tar.gz ~
   tar -xvf ~/azuredatastudio-linux-<version string>.tar.gz
   echo 'export PATH="$PATH:~/azuredatastudio-linux-x64"' >> ~/.bashrc
   source ~/.bashrc
   ```

1. To start Azure Data Studio, run this command:

   ```bash
   azuredatastudio
   ```

If you have missing dependencies, install them with the following command:

```bash
yum install libxss1 libgconf-2-4 libunwind8
```

#### [SLES](#tab/suse-install)

#### Install using .rpm file

1. Download Azure Data Studio for SUSE Linux Enterprise Server by using the [.rpm](https://azuredatastudio-update.azurewebsites.net/latest/linux-rpm-x64/stable) file.

1. To extract the file, open a new terminal window, and then run the following commands:

   ```bash
   cd ~
   sudo zypper install ./Downloads/azuredatastudio-linux-<version string>.rpm
   ```

1. To start Azure Data Studio, run this command:

   ```bash
   azuredatastudio
   ```

If you have missing dependencies, install them with the following command:

```bash
sudo zypper install libXScrnSaver
```

#### Install using .tar.gz file

1. Download Azure Data Studio for SUSE Linux Enterprise Server by using the [.tar.gz](https://azuredatastudio-update.azurewebsites.net/latest/linux-x64/stable) file.

1. To extract the file, open a new terminal window, and then run the following commands:

   ```bash
   cd ~
   cp ~/Downloads/azuredatastudio-linux-<version string>.tar.gz ~
   tar -xvf ~/azuredatastudio-linux-<version string>.tar.gz
   echo 'export PATH="$PATH:~/azuredatastudio-linux-x64"' >> ~/.bashrc
   source ~/.bashrc
   ```

1. To start Azure Data Studio, run this command:

   ```bash
   azuredatastudio
   ```

If you have missing dependencies, install them with the following command:

```bash
sudo zypper install libxss1 libgconf-2-4 libunwind8
```

#### [Ubuntu and Debian](#tab/ubuntu-install)

#### Install using .deb file

1. Download Azure Data Studio for Ubuntu or Debian by using the [.deb](https://azuredatastudio-update.azurewebsites.net/latest/linux-deb-x64/stable) file.

1. To extract the .deb file, open a new terminal window, and then run the following commands:

   ```bash
   cd ~
   sudo dpkg -i ./Downloads/azuredatastudio-linux-<version string>.deb
   ```

1. To start Azure Data Studio, run this command:

   ```bash
   azuredatastudio
   ```

If you have missing dependencies, install them with the following command:

```bash
sudo apt-get install libunwind8
```

#### Install using .tar.gz file

1. Download Azure Data Studio for Ubuntu or Debian by using the [.tar.gz](https://azuredatastudio-update.azurewebsites.net/latest/linux-x64/stable) file.

1. To extract the file, open a new terminal window, and then run the following commands:

    ```bash
    cd ~
    cp ~/Downloads/azuredatastudio-linux-<version string>.tar.gz ~
    tar -xvf ~/azuredatastudio-linux-<version string>.tar.gz
    echo 'export PATH="$PATH:~/azuredatastudio-linux-x64"' >> ~/.bashrc
    source ~/.bashrc
    ```

1. To start Azure Data Studio, run this command:

    ```bash
    azuredatastudio
    ```

If you have missing dependencies, install them with the following command:

```bash
sudo apt-get install libxss1 libgconf-2-4 libunwind8
```

#### [Windows Subsystem for Linux](#tab/windows-install)

1. Install Azure Data Studio for Windows. Then, use the `azuredatastudio` command in a Windows Subsystem for Linux (WSL) terminal just as you would in a standard command prompt. By default, the application is stored in your *AppData* folder.

1. Start Azure Data Studio from the WSL command prompt. When you're using the default Windows installation, start the application by running the following command. Replace `<your user name>` with your user name:

   ```bash
   /mnt/c/Users/<your user name>/AppData/Local/Programs/Azure Data Studio/azuredatastudio.exe
   ```
