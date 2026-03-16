---
title: Install Certificates Required for an Offline Installation of SQL Server Management Studio
description: Install the certificates required for an offline installation of SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, mbarickman
ms.date: 10/24/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
---
# Install certificates for an offline installation of SQL Server Management Studio

SQL Server Management Studio (SSMS) is designed to be installed on an internet-connected machine, because the application and its components are updated regularly. However, you can deploy SSMS in an environment where a working internet connection is unavailable.

The SSMS setup engine installs only content that is trusted. It checks Authenticode signatures of the content being downloaded and verifies that all content is trusted before installing it. This verification keeps your environment safe from attacks where the download location is compromised.

Therefore, SSMS setup requires several standard Microsoft root and intermediate certificates to be installed and up-to-date on a user's machine. If the machine is kept up to date with Windows Update, signing certificates usually are up to date. If the machine is connected to the internet, during installation Visual Studio might refresh certificates as necessary to verify file signatures. If the machine is offline, the certificates must be refreshed another way.

## How to install or refresh certificates when offline

There are three options for installing or updating certificates in an offline environment.

### Option 1 - Manually install certificates from a layout folder

When you create an [offline layout](create-offline.md), the necessary certificates are downloaded to the Certificates folder. You can manually install the certificates by right-clicking each of the certificate files, selecting Install Certificate, and then clicking through the Certificate Manager wizard. If asked for a password, leave it blank.

### Option 2 - Distribute trusted root certificates in an enterprise environment

For enterprises with offline machines that don't have the latest root certificates, an administrator can use the instructions on the [Configure Trusted Roots and Disallowed Certificates](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012) page to update them.

### Option 3 - Install certificates as part of a scripted deployment of SSMS

If you're scripting the deployment of SSMS in an offline environment to client workstations, you can follow these steps:

1. Copy the [Certificate Manager Tool](/dotnet/framework/tools/certmgr-exe-certificate-manager-tool) (certmgr.exe) to the layout folder. Certmgr.exe isn't included as part of Windows, but is available as part of the [Windows SDK](https://developer.microsoft.com/windows/downloads/windows-sdk).

1. Create a batch file with the following commands:

   ```console
   certmgr.exe -add [layout path]\certificates\manifestRootCertificate.cer -n "Microsoft Root Certificate Authority 2011" -s -r LocalMachine root

   certmgr.exe -add [layout path]\certificates\manifestCounterSignRootCertificate.cer -n "Microsoft Root Certificate Authority 2010" -s -r LocalMachine root

   certmgr.exe -add [layout path]\certificates\vs_installer_opc.RootCertificate.cer -n "Microsoft Root Certificate Authority 2010" -s -r LocalMachine root
   ```

   Alternatively, create a batch file that uses certutil.exe, which ships with Windows, with the following commands:

   ```console
   certutil.exe -f -addstore "Root" "[layout path]\certificates\manifestRootCertificate.cer"

   certutil.exe -f -addstore "Root" "[layout path]\certificates\manifestCounterSignRootCertificate.cer"

   certutil.exe -f -addstore "Root" "[layout path]\certificates\vs_installer_opc.RootCertificate.cer"
   ```

1. Deploy the batch file to the client. This command should run from an elevated process.

## Validate a certificate for offline installations

Installing SSMS on an offline machine can require a valid certificate. If you try to install SSMS on an offline machine using a layout, and the installer exits with no exception, it might be due to an invalid certificate. Go to the `%TEMP%` folder and open the most recent bootstrapper file named `dd_bootstrapper_yyyyMMddHHmmss.log`. The following messages indicate the installation is failing because of an invalid certificate:

```output
Certificate is invalid: <YourSSMSFolder>\vs_installer.opc
Error: Unable to verify the certificate: InvalidCertificate
Error 0x80131509: Signature verification failed. Error: Unable to verify the integrity of the installation files: the certificate could not be verified.
```

To ensure the installation completes successfully, follow these steps:

1. On a machine with internet connection, download the [Microsoft Windows Code Signing PCA 2024 certificate](https://www.microsoft.com/pkiops/certs/Microsoft%20Windows%20Code%20Signing%20PCA%202024.crt).
1. Move the .crt file to the offline machine.
1. From the offline machine, right-click the .crt file and select **Install Certificate**.
1. Select **Local Machine** as Store Location and then **Next**.
1. Keep **Automatically select the certificate store based on the type of certificate**, then select **Next**.
1. Select **Finish**.
1. You see the prompt, **The import was successful**.
1. Install SSMS using the local layout.

Alternatively, create a batch file that uses certutil.exe, which ships with Windows, with the following commands:

```console
certutil.exe -f -addstore "CA" "[layout path]\certificates\Microsoft Windows Code Signing PCA 2024.crt)"
```

## Maintain an offline machine

For users maintaining offline machines, [obtain the required certificates](https://www.microsoft.com/pkiops/certs/Microsoft%20Windows%20Code%20Signing%20PCA%202024.crt) and deploy them manually.

## What are the certificates files in the Certificates folder?

There are three certificates files in the `Certificates` folder.

- `manifestRootCertificate.cer` contains:
  - **Root certificate**: Microsoft Root Certificate Authority 2011

- `manifestCounterSignRootCertificate.cer` and `vs_installer_opc.RootCertificate.cer` contain:
  - **Root certificate**: Microsoft Root Certificate Authority 2010

The **Visual Studio Installer** requires only the root certificates to be installed on the system.

## Why are the certificates from the Certificates folder not installed automatically?

When a signature is verified in an online environment, Windows APIs are used to download and add the certificates to the system. Verification that the certificate is trusted and allowed via administrative settings occurs during this process. This verification process can't occur in most offline environments. Installing the certificates manually allows enterprise administrators to ensure the certificates are trusted and meet the security policy of their organization.

## Check if certificates are already installed

You can check to see if the certificates are already installed using these steps.

1. Run **mmc.exe**.
1. Select **File**, and then select **Add/Remove Snap-in**.
1. Double-click **Certificates**, select **Computer account**, and then select **Next**.
1. Select **Local computer**, then **Finish**.
1. Expand **Certificates (Local Computer)**.
1. Expand **Trusted Root Certification Authorities**, then select **Certificates**.
1. Check this list for the necessary root certificates.
1. Expand **Intermediate Certification Authorities**, then select **Certificates**.
1. Check this list for the required intermediate certificates.
1. Select **File**, and then select **Add/Remove Snap-in**.
1. Double-click **Certificates**, select **My user account**, and then select **Finish**.
1. Expand **Certificates – Current User**.
1. Expand **Intermediate Certification Authorities**, then select **Certificates**.
1. Check this list for the required intermediate certificates.

If the certificates names aren't in the **Issued To** columns, they must be installed. If an intermediate certificate is only in the **Current User Intermediate Certificate** store, then it's available only to the user that is logged in. You might need to install it for other users.

## Install SSMS

After you install the certificates on the client machine, then you're ready to [install SSMS](create-offline.md) from the layout.

## Related content

- [Create an offline installation of SQL Server Management Studio](create-offline.md)
- [Use command-line parameters to install SQL Server Management Studio](command-line-parameters.md)
- [Workload and component IDs for SQL Server Management Studio](workload-component-ids.md)
- [Install SQL Server Management Studio](install.md)
- [Modify SQL Server Management Studio workloads, components, and language packs](modify.md)
