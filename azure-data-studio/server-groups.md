---
title: Server Groups
description: Learn how to group servers and databases into server groups and assign colors to the groups. You can drag and drop servers into the proper groups.
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest, maghan
ms.date: 02/06/2025
ms.update-cycle: 1825-days
ms.service: azure-data-studio
ms.topic: article
ms.collection:
  - data-tools
ms.custom:
  - updatefrequency5
---

# Server groups in Azure Data Studio

[!INCLUDE [azure-data-studio-deprecation](includes/azure-data-studio-deprecation.md)]

Server groups provide a way to organize your connections to the servers and databases you work with. When you create server groups, the configuration details are saved into *User Settings*.

## Create and edit server groups

1. Click **New Server Group** at the top of the *SERVERS* sidebar.
2. Enter a group name and select a color for the group. Optionally, add a description.

   ![add server group](./media/server-groups/add-server-group.png)

To edit an existing server group, right-click the group, and select **Edit Server Group**.

To edit available server group colors, edit the *Server Groups* values in [User Settings](settings.md).

> [!TIP]
> You can drag and drop servers between different Server Groups.



## Additional resources
- [Workspace and User settings](settings.md)
