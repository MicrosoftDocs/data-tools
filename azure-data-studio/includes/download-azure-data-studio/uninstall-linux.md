---
author: markingmyname
ms.author: maghan
ms.date: 10/17/2023
ms.service: azure-data-studio
ms.topic: include
---

## Linux

### [RHEL](#tab/redhat-uninstall)

Use the `rpm`, `yum`, or `dnf` command to delete Azure Data Studio under Red Hat Enterprise Linux.

To list installed software, run one of the following commands:

```bash
sudo rpm -qa | less
sudo yum list | less
sudo dnf list | less
```

To get information about the `azuredatastudio` package, run one of the following commands:

```bash
sudo rpm -qa azuredatastudio
sudo yum list azuredatastudio
sudo dnf list azuredatastudio
```

To delete a package called `azuredatastudio`, run one of the following commands:

```bash
sudo rpm -e azuredatastudio
sudo yum remove azuredatastudio
sudo dnf remove azuredatastudio
```

### [SLES](#tab/suse-uninstall)

Use the `rpm` or `zypper` command to delete Azure Data Studio under SUSE Linux Enterprise Server.

To list installed software, run one of the following commands:

```bash
sudo rpm -qa | less
sudo zypper list | less
```

To get information about the `azuredatastudio` package, run one of the following commands:

```bash
sudo rpm -qa azuredatastudio
sudo zypper list azuredatastudio
```

To delete a package called `azuredatastudio`, run one of the following commands:

```bash
sudo rpm -e azuredatastudio
sudo zypper remove azuredatastudio
```

### [Ubuntu and Debian](#tab/ubuntu-uninstall)

You can uninstall Azure Data Studio under Ubuntu or Debian.

To list installed software, run the following command:

```bash
sudo dpkg --list | less
```

To list installed software that matches `azuredatastudio`, run the following command:

```bash
sudo dpkg --list | grep azuredatastudio
```

To delete the software, run the following commands:

```bash
sudo apt-get remove azuredatastudio
```