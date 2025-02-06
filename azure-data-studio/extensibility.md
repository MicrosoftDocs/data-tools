---
title: Adding More Functionality Through Extensibility
description: Learn about the extensibility model and key extensibility areas for extending the functionality of Azure Data Studio
author: croblesm
ms.author: roblescarlos
ms.reviewer: randolphwest, maghan
ms.date: 02/06/2025
ms.service: azure-data-studio
ms.topic: conceptual
ms.custom:
  - extensibility
---

# Azure Data Studio extensibility

[!INCLUDE [azure-data-studio-deprecation](includes/azure-data-studio-deprecation.md)]

Azure Data Studio has several extensibility mechanisms to customize the user experience and make those customizations available to the entire user community. The core Azure Data Studio platform is built upon Visual Studio Code, so most of the Visual Studio Code extensibility APIs are available. Additionally, we've provided other extensibility points for data management-specific activities.

Some of the key extensibility points are:

- Visual Studio Code extensibility APIs
- Azure Data Studio extension authoring tools
- Manage Dashboard tab panel contributions
- Insights with Action experience
- Azure Data Studio extensibility APIs
- Custom Data Provider APIs

## Visual Studio Code extensibility APIs

Because the core Azure Data Studio platform is built upon Visual Studio Code, details about the Visual Studio Code extensibility APIs are found in the [Extension Authoring](https://code.visualstudio.com/docs/extensions/overview) and [Extension API](https://code.visualstudio.com/docs/extensionAPI/overview) documentation on the Visual Studio Code website.

> [!NOTE]  
> Azure Data Studio releases align with a recent VS Code version. However, the included VS Code engine might not be the current VS Code release. For example, in November 2020, the VS Code engine in Azure Data Studio was 1.48, and the current VS Code version is 1.51. The error message "Unable to install extension '\<name\>' as it isn't compatible with VS Code \<version\>" when installing an extension is caused by an extension that has a later VS Code engine version defined in the package manifest (`package.json`). You can verify the VS Code engine version in your Azure Data Studio through the **Help** menu under **About**.

## Manage Dashboard tab panel contributions

For details, see [Contribution Points](#contribution-points) and [Context Variables](#context-variables).

## Azure Data Studio extensibility APIs

For details, see [Extensibility APIs](extensibility-apis.md).

## Contribution points

This section covers the various contribution points defined in the package.json extension manifest.

The IntelliSense is supported inside azuredatastudio.

### Dashboard contribution points

Contribute a tab, container, and/or insight widget to the dashboard.

:::image type="content" source="media/extensibility/dashboard-page.png" alt-text="Screenshot of the dashboard." lightbox="media/extensibility/dashboard-page.png":::

#### dashboard.tabs

Dashboard.tabs creates the tab sections inside the dashboard page. It expects an object or an array of objects.

```json
"dashboard.tabs": [
    {
        "id": "test-tab1",
        "title": "Test 1",
        "description": "The test 1 displays a list of widgets.",
        "when": "connectionProvider == 'MSSQL' && !mssql:iscloud",
        "alwaysShow": true,
        "container": {
            ...
        }
    }
]
```

#### dashboard.containers

Instead of specifying the dashboard container inline (inside the dashboard tab), you can register containers using dashboard.containers. It accepts an object or an array of objects.

```json
"dashboard.containers": [
    {
        "id": "innerTab1",
        "widgets-container": [
            {
                "widget": {
                    "query-data-store-db-insight": {}
                }
            },
            {
                "widget": {
                    "explorer-widget": {}
                }
            }
        ]
    },
    {
        "id": "innerTab2",
        "webview-container": {}
    },
    {
        "id": "innerTab3",
        "grid-container": [
            {
                "name": "widget 1",
                "widget": {
                    "explorer-widget": {}
                },
                "row": 0,
                "col": 0
            },
            {
                "name": "widget 2",
                "widget": {
                    "tasks-widget": {
                        "backup",
                        "restore",
                        "configureDashboard",
                        "newQuery"
                    }
                },
                "row": 0,
                "col": 1
            },
            {
                "name": "Webview 1",
                "webview": {
                    "id": "google"
                },
                "row": 1,
                "col": 0,
                "colspan": 2
            },
            {
                "name": "widget 3",
                "widget": {
                    "explorer-widget": {}
                },
```

To refer to registered container, specify the ID of the container.

```json
"dashboard.tabs": [
    {
        "id": "test-tab1",
        "title": "Test 1",
        "description": "The test 1 displays a list of widgets.",
        "when": "connectionProvider == 'MSSQL' && !mssql:iscloud",
        "alwaysShow": true,
        "container": {
            "id": "innerTab1"
        }
    }
]
```

#### dashboard.insights

You can register insights using dashboard.insights. This is similar to [Tutorial: Build a custom insight widget](./tutorial-build-custom-insight-sql-server.md). It accepts an object or an array of objects.

```json
"dashboard.insights": {
    "id": "my-widget",
    "type": {
        "count": {
            "dataDirection": "vertical",
            "dataType": "number",
            "legendPosition": "none",
            "labelFirstColumn": false,
            "columnsAsLabels": false
        }
    },
    "queryFile": "{your file folder}/activeSession.sql"
}
```

### Dashboard container types

There are currently four supported container types:

#### widgets-container

:::image type="content" source="media/extensibility/widgets-container.png" alt-text="Screenshot of widgets container." lightbox="media/extensibility/widgets-container.png":::

The list of widgets that will be displayed in the container is a flow layout that accepts this list.

```json
"container": {
    "widgets-container": [
        {
            "widget": {
                "query-data-store-db-insight": {}
            }
        },
        {
            "widget": {
                "explorer-widget": {}
            }
        }
    ]
}
```

#### webview-container

:::image type="content" source="media/extensibility/webview-container.png" alt-text="Screenshot of the Webview container" lightbox="media/extensibility/webview-container.png":::

The webview is displayed in the entire container. It expects webview ID to be the same is tab ID.

```json
"container": {
    "webview-container": {}
}
```

#### grid-container

:::image type="content" source="media/extensibility/grid-container.png" alt-text="Screenshot of the grid container" lightbox="media/extensibility/grid-container.png":::

The list of widgets or webviews that are displayed in the grid layout. The grid layout is a 2x2 grid layout that accepts this list.

```json
"container": {
    "grid-container": [
        {
            "name": "widget 1",
            "widget": {
                "explorer-widget": {}
            },
            "row": 0,
            "col": 0
        },
        {
            "name": "widget 2",
            "widget": {
                "tasks-widget": {
                    "backup",
                    "restore",
                    "configureDashboard",
                    "newQuery"
                }
            },
            "row": 0,
            "col": 1
        },
        {
            "name": "Webview 1",
            "webview": {
                "id": "google"
            },
            "row": 1,
            "col": 0,
            "colspan": 2
        },
        {
            "name": "widget 3",
            "widget": {
                "explorer-widget": {}
            },
            "row": 0,
            "col": 3,
            "rowspan": 2
        }
    ]
}
```

#### nav-section

:::image type="content" source="media/extensibility/nav-section.png" alt-text="Screenshot of the Nav section screen":::

The navigation section is displayed in the container. It expects an array of objects.

```json
"container": {
    "nav-section": [
        {
            "id": "innerTab1",
            "title": "inner-tab1",
            "icon": {
                "light": "./icons/tab1Icon.svg",
                "dark": "./icons/tab1Icon_dark.svg"
            },
            "container": {
                ...
            }
        },
        {
            "id": "innerTab2",
            "title": "inner-tab2",
            "icon": {
                "light": "./icons/tab2Icon.svg",
                "dark": "./icons/tab2Icon_dark.svg"
            },
            "container": {
                ...
            }
        }
    ]
}
```

## Context variables

For general information about context in Visual Studio Code and later Azure Data Studio, see [Extensibility](https://code.visualstudio.com/docs/extensionAPI/extension-points#_example).

In Azure Data Studio, we have specific context around database connections available for extensions.

### Dashboard

In the dashboard, we provide the following context variables:

| Context Variable     | Description                                                                                                                            |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| `connectionProvider` | A string of the identifier for the provider of the current connection. Ex. `connectionProvider == 'MSSQL'`.                            |
| `serverName`         | A string of the server name of the current connection. Ex. `serverName == 'localhost'`.                                                |
| `databaseName`       | A string of the database name of the current connection. Ex. `databaseName == 'master'`.                                               |
| `connection`         | The full connection profile object for the current connection (IConnectionProfile)                                                     |
| `dashboardContext`   | A string of the context of the page the dashboard is currently on. Either 'database' or 'server'. Ex. `dashboardContext == 'database'` |

## Related content

- [Extensibility APIs](extensibility-apis.md)
- [Download Azure Data Studio](download-azure-data-studio.md)
