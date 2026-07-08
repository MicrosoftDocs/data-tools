---
title: Designate an Events Forwarding Server
description: Configure event forwarding in SQL Server to send events to a designated server. Learn how to set up an events forwarding server using SQL Server Management Studio.
author: rwestMSFT
ms.author: randolphwest
ms.date: 07/08/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
helpviewer_keywords:
  - "event forwarding servers [SQL Server]"
  - "events [SQL Server], forwarding"
  - "alerts [SQL Server], forwarded events"
# customer intent: As a SQL Server admin, I want to forward events based on severity level, so that I can focus on the most critical issues from a central server.
---

# Designate an events forwarding server

[!INCLUDE [SQL Server SQL MI](../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

This article describes how to designate a server to which [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] forward events by using [!INCLUDE [ssmanstudiofull-md](../includes/ssmanstudiofull-md.md)].

Event forwarding applies to events forwarded between servers, not to events forwarded between instances of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] hosted on a single computer. To receive forwarded events, the alerts management server must be a default instance of [!INCLUDE [ssnoversion-md](../includes/ssnoversion-md.md)].

## Permissions

Requires membership in the **sysadmin** fixed server role.

<a id="SSMSProcedure"></a>

## Use SQL Server Management Studio

1. In **Object Explorer**, select the plus sign to expand the server from which you want to forward events to another server.

1. Right-click **SQL Server Agent** and select **Properties**.

1. In the **SQL Server Agent Properties - *\<server_name>*** dialog box, under **Select a page**, select **Advanced**.

1. Under **SQL Server event forwarding**, select the **Forward events to a different server** check box.

1. In the **Server** list, select a server. Under **Events**, select one of the following options:

   - Select **Unhandled events** to forward only the events that local alerts don't handle.

   - Select **All events** to forward all events regardless of whether local alerts handle them.

1. In the **If event has severity at or above** list, select the severity level at which you want to forward events to the selected server.

1. When finished, select **OK**.

## Related content

- [SQL Server Agent Properties (Advanced Page)](sql-server-agent-properties-advanced-page.md)
- [Monitor and Respond to Events](monitor-and-respond-to-events.md)
