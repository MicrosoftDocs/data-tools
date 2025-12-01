---
title: "Alert Properties - New Alert (General Page)"
description: Use the New Alert (General) page to view and modify the general properties of SQL Server Agent alerts.
author: rwestMSFT
ms.author: randolphwest
ms.date: 12/01/2025
ms.service: sql-server-management-studio
ms.topic: ui-reference
ms.collection:
  - data-tools
f1_keywords:
  - "sql13.ag.alert.general.f1"
---

# SQL Server Agent alert properties - New Alert (General page)

[!INCLUDE [SQL Server](../includes/applies-to-version/sqlserver.md)]

[!INCLUDE [sql-server-agent-azure-sql-managed-instance-support](../includes/sql-server-agent-azure-sql-managed-instance-support.md)]

Use this page to view and modify the general properties of [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent alerts.

## Options

#### Name

Change the name of the alert.

#### Enable

Enable the alert. When the alert isn't enabled, the actions specified in the alert don't occur.

#### Type

Select the type of alert:

- **SQL Server event alert** responds to messages in the Windows event log.
- **SQL Server performance condition alert** responds to a specific condition in a performance counter.
- **WMI event alert** responds to a Windows Management Instrumentation (WMI) event.

## SQL Server event alert options

#### Database name

Specify a database for the event, or **all databases** to respond to a message regardless of the database where the event occurs.

#### Error number

Specify that this event responds to an error, and specify the error number.

#### Severity

Specify that this event responds to any message with a specific severity level, and specify the severity level.

#### Raise alert when message contains

Filter events by a specific string. When this option is selected, the alert only responds to events that contain a specific string.

#### Message text

Specify the string to use to filter events.

## SQL Server performance condition alerts

#### Object

Specify the performance object to monitor.

#### Counter

Specify the counter within the performance object to monitor.

#### Instance

Specify the instance of the counter to monitor.

#### Alert if counter

Specify the behavior of the counter that the alert responds to. For example, you might want the alert to respond to a condition where the value of the **Free space in `tempdb` (KB)** counter falls below a certain value, or you might want the alert to respond to a condition where the **SQL Compilations/sec** rises above a certain value.

#### Value

Specify a value for the counter.

## WMI event alert options

#### Namespace

Specify the namespace to use for the WMI Query Language (WQL) statement. Only namespaces on the computer that runs [!INCLUDE [ssNoVersion](../includes/ssnoversion-md.md)] Agent are supported.

#### Query

Specify the WQL statement that identifies the event that the alert responds to.

## Related content

- [SQL Server Agent alerts](alerts.md)
- [Use WQL with the WMI Provider for Server Events](/sql/relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events)
- [Create an Alert Using an Error Number](create-an-alert-using-an-error-number.md)
- [Create an Alert Using Severity Level](create-an-alert-using-severity-level.md)
