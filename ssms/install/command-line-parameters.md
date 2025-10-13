---
title: Use Command-Line Parameters to Install SQL Server Management Studio
description: Use command-line parameters to install SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan, mbarickman
ms.date: 10/22/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - data-tools
---
# Use command-line parameters to install SQL Server Management Studio

[!INCLUDE [sql-asdb-asdbmi-asa](../includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

[!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] is a powerful tool for managing SQL Server instances, Azure SQL databases, and Azure SQL managed instances. This article provides detailed instructions on how to use command-line parameters to install [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)], allowing for a more customized and automated installation process. Whether you're installing [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] for the first time or updating an existing installation, these instructions provide the necessary steps to achieve your goals.

## Command-line parameters

When you install SQL Server Management Studio (SSMS) programmatically or from a command prompt, you can use various command-line parameters to control or customize the installation to perform the following actions:

- Start the installation on the client with certain options and behaviors preselected.
- Automate the installation or update process.
- Create or maintain a network layout of the product files for installing or updating client machines.

The following command-line verbs and parameters can be used with the following executables or programs:

- The setup bootstrapper, which is the small (~5 MB) file (for example, `vs_SSMS.exe`) that initiates the download process and the initial installation.
- The Visual Studio installer that might already be installed on the machine and is located in the folder `C:\Program Files (x86)\Microsoft Visual Studio\Installer\setup.exe`. You must initiate the installer programmatically from a *different* directory that the installer resides in. The installer is typically used for update or modify commands.

Not all commands or parameters work in each of these situations, and any special caveats or exceptions are documented. Furthermore, in some scenarios you might not have access to all of these executables described previously. For example, client machines might only have the installer available for programmatic execution if SSMS was installed via a layout.

To get the latest bootstrappers for [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] that always install the latest version of the selected channel, download one of the files in the following table. Alternatively, to install a specific version or a specific channel of [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)], see [Release history for SQL Server Management Studio](../release-history.md). This article has links to the fixed version bootstrappers for each servicing release.

| Channel | Version | Bootstrapper |
| --- | --- | --- | --- |
| Release | [!INCLUDE [latest-build](../includes/latest-build.md)] | [SQL Server Management Studio](https://aka.ms/ssms/21/release/vs_SSMS.exe) |

> [!TIP]  
> If you previously downloaded a bootstrapper file, you can verify the version before you try to install. Open File Explorer, right-click the bootstrapper file, select **Properties**, and then select the **Details** tab. The **Product version** field describes the [channel and version](channels-release.md) that the bootstrapper installs. The version number should always be read as "latest servicing version of what is specified," and the channel is Release unless explicitly specified. A bootstrapper with a product version that says [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] installs the latest version of [!INCLUDE [ssms-21-md](../includes/ssms-21-md.md)] from the Release channel.

## Install, update, modify, repair, uninstall, and export commands and command-line parameters

When the SSMS bootstrapper or the installer is invoked programmatically, to install the product or to maintain a layout:

- The first parameter is the command (the verb) that describes the operation to perform.
- The subsequent optional command line parameters, all prefixed by two dashes (`--`), further define how that operation is supposed to happen.

All SSMS command-line parameters are case-insensitive.

Syntax example: `vs_SSMS.exe [command] <optional parameters>...`

| **Command** | **Description** |
| --- | --- |
| (blank) | The default command both installs the product, and it's used for all layout maintenance operations. |
| `modify` | Modifies an installed product. |
| `update` | Updates an installed product. |
| `updateall` | Updates all of the installed products in sequential order. Works with `--quiet` and `--passive` parameters. |
| `repair` | Repairs an installed product. |
| `uninstall` | Uninstalls an installed product. |
| `export` | Exports installation configuration into a `*.vsconfig` file. |

> [!IMPORTANT]  
> When specifying multiple distinct workloads, components, or languages, you must repeat the `--add` or `--remove` command-line switch for each item.

| **Parameters** | **Description** |
| --- | --- |
| `--installPath <dir>` | For the default install command, this parameter is **Optional** and describes where the instance is installed on the client machine. For other commands like update or modify, this parameter is **Required** and denotes the installation directory for the instance to act upon. |
| `--productId <id>` | **Optional**: The ID of the product instance that is modified, and used with `--channelId`. The `productId` is `Microsoft.VisualStudio.Product.SSMS`. |
| `--channelUri` | **Optional**: During an update command, you can pass in a new `--channelUri` to change the update settings location. Recommend to pair with `--installPath` parameter so that it's explicit which instance of SSMS you're configuring. See [syntax examples of `--channelUri`](/visualstudio/install/command-line-parameter-examples#using---channeluri) |
| `--channelId <id>` | The ID of the channel, for example, `SSMS.21.SSMS.Preview`. `channelId` is required for modify operations, alongside either `--productId` or `--installPath`. |
| `--add <one or more workload or component IDs>` | **Optional**: During an install or modify command, this repeatable parameter specifies one or more workload or component IDs to add. The required components of the artifact are installed, but not the recommended or optional components. You can control other components globally using `--includeRecommended` and/or `--includeOptional` parameters. To include multiple workloads or components, repeat the `--add` command (for example, `--add Workload1 --add Workload2`). For finer-grained control, you can append `;includeRecommended` or `;includeOptional` to the ID (for example, `--add Workload1;includeRecommended` or `--add Workload2;includeRecommended;includeOptional`). |
| `--all` | **Optional**: During an install or modify command, this parameter causes all workloads and components for the product to be installed. |
| `--allWorkloads` | **Optional**: During an install or modify command, this parameter installs all workloads and components, but no recommended or optional components. |
| `--includeRecommended` | **Optional**: During an install or modify command, this parameter includes the recommended components for any workloads that are installed. It doesn't include the optional components. The workloads are specified either with `--allWorkloads` or `--add`. By using the `--includeRecommended` parameter, you enable your **Update Settings** dialog to "add recommended components for installed workloads on update". To change these settings, see [Customize update settings](update.md#customize-update-settings). |
| `--includeOptional` | **Optional**: During an install or modify command, this parameter includes the optional components for any workloads that are installed. It doesn't include the recommended components. The workloads are specified either with `--allWorkloads` or `--add`. |
| `--addProductLang <language-locale>` | **Optional**: During an install or modify command, this repeatable parameter specifies the UI language packs that should be installed with the product. If not present, the installation uses the language pack that corresponds to the machine locale. For more information, see the [List of language locales] |
| `--remove <one or more workload or component IDs>` | **Optional**: During a modify command, this repeatable parameter specifies one or more workload or component IDs to remove. It complements and behaves similarly to the `--add` parameter. |
| `--addProductLang <language-locale>` | **Optional**: During an install or modify command, this repeatable parameter specifies the UI language packs that should be installed with the product. If not present, the installation uses the language pack that corresponds to the machine locale. For more information, see the [List of language locales](#list-of-language-locales) section on this article. |
| `--removeProductLang <language-locale>` | **Optional**: During an install or modify command, this repeatable parameter determines the UI language packs that should be removed from the product. It complements and behaves similarly to the `--addProductLang` parameter. |
| `--in <path>` | **Optional**: The URI or path to a response file, which can contain configuration settings. |
| `--quiet` | **Optional**: This parameter, when used with any command, prevents any user interface from being displayed while the command is being executed. Not available to use programmatically by standard users regardless of how the [AllowStandardUserControl policy](https://aka.ms/vs/setup/policies) is set. |
| `--passive, -p` | **Optional**: This parameter causes the user interface to be displayed in a non-interactive manner. This parameter is mutually exclusive from (and in fact overrides) the `--quiet` parameter. Also not available to use programmatically by standard users regardless of how the [AllowStandardUserControl policy](https://aka.ms/vs/setup/policies) is set. |
| `--norestart` | **Optional**: This parameter must be paired with either the `--passive` or `--quiet` parameters. During an install, update, or modify command, adding the `--norestart` parameter delays any necessary reboot. |
| `--force` | **Optional**: This parameter forces SSMS to close even if any SSMS process is in use. Forcing SSMS to close might cause loss of work, so use it with caution. |
| `--installWhileDownloading` | **Optional**: During an install, update, or modify command, this parameter allows SSMS to both download and install the product in parallel. It's the default experience. |
| `--downloadThenInstall` | **Optional**: During an install, update, or modify command, this parameter forces SSMS to download all files before installing them. It's mutually exclusive from the `--installWhileDownloading` parameter. |
| `--nickname <name>` | **Optional**: During an install command, this parameter defines the nickname to assign to an installed product. The nickname can't be longer than 10 characters. |
| `--removeOos true` | **Optional**: During an install, update, or modify command, this parameter, followed by `true` or `false`, tells the Visual Studio Installer whether to remove all installed components transitioned to an out-of-support state. This behavior is applicable for a single event. If you want to make this behavior persistent, apply this parameter to the `modifySettings` command, described later, or configure the `removeOOS` global policy. Useful for helping to keep the machine secure. |
| `--config <path to *.vsconfig file>` | **Optional**: During an install or modify operation, you can pass in a configuration file using the `--config` parameter to specify the workloads, components, or extensions to add based on a previously saved installation configuration file. This operation is additive only; it doesn't remove anything not specified in the file. Also, items specified in the config file that don't apply to the product aren't added. Highly recommend you specify the fully qualified path to the config file. During an export operation, this parameter determines the location to save the installation configuration file. |
| `--allowUnsignedExtensions` | **Optional**: During an install or modify operation run in a `--passive` or `--quiet` context using a `--config` file, if extensions are specified in the config file, then this parameter is necessary in order to load extensions without a digital signature. |
| `--installerOnly` | **Optional**: During an install or update operation, this parameter tells the Visual Studio Installer to install just itself (the installer) and not the SSMS product. Its functionality is equivalent to the `--update` parameter, but more intuitive. Meant to be used when prepping and preconfiguring client machines. |
| `--help, --?, -h, -?` | Displays an offline version of this article. |

## Layout command and command-line parameters

All layout management operations, such as creating or updating a layout, are run using the bootstrapper exe and assume that the command is the default Install (blank). All layout management operations should start with the required `--layout` initial parameter. The following table describes the other parameters you can use to create or update a layout using the command line.

| Layout parameters | Description |
| --- | --- |
| `--layout <dir>` | Specifies a directory to create or update an offline install cache. |
| `--lang <one or more language-locales>` | **Optional**: Used with `--layout` to prepare an offline install cache with resource packages with the specified one or more specified languages. For more information, see the [List of language locales](#list-of-language-locales) section on this article. |
| `--add <one or more workload or component IDs>` | **Optional**: One or more workload or component IDs to add. The required components of the artifact are installed, but not the recommended or optional components. You can control more components globally using `--includeRecommended` and/or `--includeOptional`. For finer-grained control, you can append `;includeRecommended` or `;includeOptional` to the ID (for example, `--add Workload1;includeRecommended` or `--add Workload2;includeOptional`).<br /><br />**Note**: If `--add` is used, only the specified workloads and components and their dependencies are downloaded. If `--add` isn't specified, all workloads and components are downloaded to the layout. |
| `--includeRecommended` | **Optional**: Includes the recommended components for any workloads that are installed, but not the optional components. The workloads are specified either with `--allWorkloads` or `--add`. |
| `--includeOptional` | **Optional**: Includes the recommended *and* optional components for any workloads being included in the layout. The workloads are specified with `--add`. |
| `--wait` | **Optional**: The process waits until the install is completed before returning an exit code. `wait` is useful when automating installations where one needs to wait for the install to finish to handle the return code from that install. The `--wait` parameter can only be passed into the bootstrapper; the installer (setup.exe) doesn't support it. It's useful when updating layouts. |
| `--config <path to *.vsconfig file>` | **Optional**: If present, SSMS uses the contents of the configuration file to configure your layout. Make sure you specify the fully qualified path to the config file. |
| `--noWeb` | **Optional**: If present, SSMS setup uses the files in your layout directory to install SSMS, and it doesn't download any packages from the web. If a user tries to install components that aren't in the layout, setup fails. Don't use this parameter if you're trying to deploy a layout hosted on an internal intranet website.<br /><br />**Important**: The `--noWeb` parameter doesn't stop the Visual Studio Installer on an internet-connected client machine from checking for updates if the client is configured to look at Microsoft hosted servers for updates. In this case, `--noWeb` simply prevents the client from downloading the product packages. |
| `--verify` | **Optional**: Verify the contents of a layout. Any corrupt or missing files are listed. |
| `--fix` | **Optional**: Verify the contents of a layout. If any files are corrupt or missing, they're redownloaded. Internet access is required to fix a layout. |
| `--clean <one or more paths to catalogs>` | **Optional**: Removes old versions of components from a layout that is updated to a newer version. |

| **Advanced layout parameters** | **Description** |
| --- | --- |
| `--channelId <id>` | **Optional**: The ID of the channel for the instance to be installed, represented like `SSMS.21.SSMS.Preview`. `channelId` is required for the install command, and ignored for other commands if `--installPath` is specified. For more information, see [syntax examples](/visualstudio/install/command-line-parameter-examples#using---channeluri) of `--channelId`. |
| `--channelUri <uri>` | **Optional**: The URI of the channel manifest. This value governs the [source location of updates](update.md#configure-source-location-of-updates) and the initial value is configured in the layout's `response.json` file. If updates aren't wanted, `--channelUri` can point to a nonexistent file (for example, `--channelUri C:\doesntExist.chman`). This parameter can be used for the install command; other commands ignore it. |
| `--installChannelUri <uri>` | **Optional**: The URI of the channel manifest to use for the installation. The URI specified by `--channelUri` (which must be specified when `--installChannelUri` is specified) is used to detect updates. This parameter can be used for the install command; other commands ignore it. |
| `--installCatalogUri <uri>` | **Optional**: The URI of the catalog manifest to use for the installation. If specified, the channel manager attempts to download the catalog manifest from this URI before using the URI in the install channel manifest. This parameter is used to support offline install, where the layout cache is created with the product catalog already downloaded. This parameter can be used for the install command; other commands ignore it. |
| `--productId <id>` | **Optional**: The ID of the product for the instance that is installed. This parameter is prepopulated in normal installation conditions. The `productId` is `Microsoft.VisualStudio.Product.SSMS`. |
| `--keepLayoutVersion` | **Optional**: Apply changes to the layout without updating the product version of the layout. |
| `--locale <language-locale>` | **Optional**: Change the display language of the user interface for the installer itself. The setting is persisted. For more information, see the [List of language locales](#list-of-language-locales) section on this article. |
| `--cache` | **Optional**: If present, packages will be kept after being installed for subsequent repairs. This overrides the global policy setting to be used for subsequent installs, repairs, or modifications. The default policy is to cache packages. This policy is ignored for the uninstall command. |
| `--nocache` | **Optional**: If present, packages will be deleted after being installed or repaired. They'll be downloaded again only if needed and deleted again after use. This overrides the global policy setting to be used for subsequent installs, repairs, or modifications. The default policy is to cache packages. This policy is ignored for the uninstall command. |
| `--noUpdateInstaller` | **Optional**: If present, prevents the installer from updating itself when `quiet` is specified. The installer fails the command and returns a nonzero exit code if `--noUpdateInstaller` is specified with `quiet` when an installer update is required. |
| `--path <name>=<path>` | **Optional**: Used to specify custom install paths for the installation. Supported path names are shared, cache, and install. |
| `--path cache=<path>` | **Optional**: Uses the location you specify to download installation files. This location can only be set the first time that SSMS is installed. Example: `--path cache="C:\SSMS\cache"` |
| `--path shared=<path>` | **Optional**: Contains shared files for side-by-side SSMS and Visual Studio installations. Some tools and SDKs install to a location on this drive, while some others might override this setting and install to another drive. Example: `--path shared="C:\VS\shared"`<br /><br />**Important**: This path can be set only once and on the first time that either SSMS or Visual Studio is installed. |
| `--path install=<path>` | **Optional**: Equivalent to `–-installPath`. Specifically, `--installPath "C:\SSMS"` and `--path install="C:\SSMS"` are equivalent. Only one of these commands can be used at a time. |

## ModifySettings command and command-line parameters

You can modify the update settings and programmatically configure the source location of updates for a given instance of SSMS. This modifying can be done using the installer or the bootstrapper on the client machine, and passing in the modifySettings command and the desired update channel.

| **Command** | **Description** |
| --- | --- |
| `modifySettings` | Verb used to modify the update settings of a particular instance of SSMS. |

| **modifySettings parameters** | **Description** |
| --- | --- |
| `--installPath <dir>` | **Recommended** to use to specify which instance of SSMS to act upon. |
| `--newChannelUri` | **Required**: The URI of the channel manifest. This value specifies where the next [source location of updates](update.md#configure-source-location-of-updates) will be. If updates aren't wanted, `--channelUri` can point to a nonexistent file (for example, `--channelUri C:\doesNotExist.chman`). |
| `--channelUri` | The URI of the old channel manifest. Can be used if the `--installPath` isn't known. Must be used with `--productId` to identify the right instance to act upon. |
| `--productId <id>` | Must be used if `--channelUri` is specified and is used to identify the right instance to act upon. The `productId` is `Microsoft.VisualStudio.Product.SSMS`. |
| `--includeRecommended` | **Optional**: During a modifySettings command, this parameter (which must have the word true or false immediately after it) tells the SSMS installer to disable the "add recommended components for installed workloads on update" functionality in the Update Setting dialog. |
| `--quiet` | **Optional**: This parameter prevents any user interface from being displayed while the command is being executed. Not available to use programmatically by [standard users](https://aka.ms/vs/setup/policies). |
| `--removeOos true` | **Optional**: During a modifySettings command, this parameter tells the SSMS installer to *persistently* remove, or not remove, all installed components that transitioned to an out-of-support state. This setting must have the word true or false immediately after it. This setting helps keep the machine secure. |

Syntax examples:

  ```cmd
  C:\>"C:\Program Files (x86)\Microsoft Visual Studio\Installer\setup.exe" modifySettings --installPath "C:\Program Files\Microsoft SQL Server Management Studio 21\Release" --newChannelUri https://aka.ms/ssms/21/release/channel --removeOos true
  ```

  ```cmd
   C:\>"C:\Program Files\Microsoft SQL Server Management Studio 21\Release\vs_SSMS.exe" modifySettings --channelUri https://aka.ms/ssms/21/release/channel --productId Microsoft.VisualStudio.Product.Ssms --newChannelUri \\layoutserver\share\path\channelmanifest.json --removeOos true --quiet
  ```

## Remove channel command and command-line parameters

Channels that are available to update from, are cached on the client, and over time they can generate clutter. You can manually remove [update channels](update.md#configure-source-location-of-updates) by bringing up the Visual Studio Installer, switching to the **Available** tab, and selecting on the **X** in the top right corner of the product card. You can programmatically remove channels (for example, older layout locations) using the `removeChannel` command. You can run `vswhere` programmatically on the client machine to determine which channels are cached on the client machine.

| **Command** | **Description** |
| --- | --- |
| `removeChannel` | Command to remove a channel from the client machine. |

| **removeChannel parameters** | **Description** |
| --- | --- |
| `--channelUri` | **Required** The URI of the old channel manifest. |
| `--quiet` | **Optional** This parameter prevents any user interface from being displayed while the command is being executed. |
| `--passive` | **Optional** This parameter overrides the `--quiet` parameter. It causes the UI to appear in a non-interactive manner. |

Syntax example:

  ```cmd
  "C:\Program Files (x86)\Microsoft Visual Studio\Installer\setup.exe" removeChannel --channelUri "\\\\server\\share\\layoutdirectory\\ChannelManifest.json"
  ```

## Use winget to install or modify SSMS

You can use the [Windows Package Manager](/windows/package-manager/winget/) (**winget**) tool to programmatically install, modify, or update SSMS on your machine along with other packages managed by **winget**.

By default, **winget** just installs the SSMS core workload.

Syntax example:

  ```cmd
  winget install Microsoft.SQLServerManagementStudio.21
  ```

Visual Studio Installer operations currently require administrator privileges, so **winget** prompts you to elevate your privileges if necessary to complete the command. Also, SSMS must be closed if you're going to upgrade it to the latest version.

## List of workload IDs and component IDs

For a list of workload and component IDs sorted by SSMS product, see [Workload and component IDs for SQL Server Management Studio](workload-component-ids.md).

## List of language locales

The following table lists the language locales that can be used with the `--addProductLang` and `--removeProductLang` parameters.

| Language-locale | Language |
| --- | --- |
| `cs-cz` | Czech |
| `de-de` | German |
| `en-us` | English |
| `es-es` | Spanish |
| `fr-fr` | French |
| `it-it` | Italian |
| `ja-jp` | Japanese |
| `ko-kr` | Korean |
| `pl-pl` | Polish |
| `pt-br` | Portuguese - Brazil |
| `ru-ru` | Russian |
| `tr-tr` | Turkish |
| `zh-cn` | Chinese - Simplified |
| `zh-tw` | Chinese - Traditional |

## Error codes

Depending on the result of the operation, the `%ERRORLEVEL%` environment variable is set to one of the following values:

| Value | Result |
| --- | --- |
| 0 | Operation completed successfully |
| 740 | Elevation required |
| 1001 | Visual Studio installer process is running |
| 1003 | SSMS is in use |
| 1602 | Operation was canceled |
| 1618 | Another installation running |
| 1641 | Operation completed successfully, and reboot was initiated |
| 3010 | Operation completed successfully, but install requires reboot before it can be used |
| 5003 | Bootstrapper failed to download installer |
| 5004 | Operation was canceled |
| 5005 | Bootstrapper command-line parse error |
| 5007 | Operation was blocked - the computer doesn't meet the requirements |
| 8001 | Arm machine check failure |
| 8002 | Background download precheck failure |
| 8003 | Out of support selectable failure |
| 8004 | Target directory failure |
| 8005 | Verifying source payloads failure |
| 8006 | SSMS processes running |
| 8010 | Operating System not supported. Refer to the [system requirements](../system-requirements.md). |
| -1073720687 | Connectivity failure |
| -1073741510 | Microsoft Visual Studio Installer was terminated (by the user or external process) |
| Other<br />(for example:<br />-1, 1, 1603) | Failure condition occurred - check the logs for more information |

Each operation generates several log files in the `%TEMP%` directory that indicate the progress of the installation. Sort the folder by date and look for files that begin with `ssms_bootstrapper`, `ssms_client`, and `ssms_setup` for the bootstrapper, the installer app, and the setup engine, respectively.

[!INCLUDE [support](../includes/support.md)]

## Related content

- [Create an offline installation of SQL Server Management Studio](create-offline.md)
- [Workload and component IDs for SQL Server Management Studio](workload-component-ids.md)
