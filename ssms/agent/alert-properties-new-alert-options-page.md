---
title: "Alert Properties - New Alert (Options Page)"
description: Use the New Alert (Options) page to view and modify options for SQL Server Agent alerts.
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/01/2025
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.ag.alert.options.f1"
---

# SQL Server Agent alert properties - New Alert (Options page)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

Use this page to view and modify options for [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent alerts.

## Options

#### E-mail

Include error text from the event, if any, in e-mail notifications.

#### Pager

Include error text from the event, if any, in pager notifications.

#### Net send

Include error text from the event, if any, in net send notifications.

#### Additional notification message to send

Type any additional text to include in notification messages.

#### Delay between responses

Specify a delay for repeated occurrences of the event. Some events might occur frequently during a short period of time. In this case, you might want to know that the event has occurred, but you might not want a response for every event. Use this option to specify a time-out. With a delay, after the alert responds to an event, [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent waits for the delay specified before responding again, regardless of whether the event occurs during the delay.

#### Minutes

Specify a delay in minutes. To respond every time the event occurs, specify 0 minutes and 0 seconds.

#### Seconds

Specify a delay in seconds. To respond every time the event occurs, specify 0 minutes and 0 seconds.

## Related content

- [SQL Server Agent alerts](alerts.md)
