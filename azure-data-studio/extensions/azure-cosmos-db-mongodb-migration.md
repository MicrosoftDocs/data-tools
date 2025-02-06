---
title: "Azure Cosmos DB for MongoDB Migration Extension (Preview)"
titleSuffix: Azure Data Studio
description: Perform assessments and migrate data from MongoDB to Azure Cosmos DB for MongoDB using the Azure Data Studio extension and Azure Database Migration Service.
author: sandnair
ms.author: sandnair
ms.reviewer: sidandrews
ms.date: 02/06/2025
ms.service: azure-data-studio
ms.subservice: migration-extension
ms.topic: how-to
ms.custom:
  - ignite-2023
# CustomerIntent: As a database developer, I want to use the migration extension, so that I can evaluate and then eventually migrate my existing data to vCore-based Azure Cosmos DB for MongoDB.
---

# Azure Cosmos DB for MongoDB migration extension for Azure Data Studio (preview)

[!INCLUDE [azure-data-studio-deprecation](../includes/azure-data-studio-deprecation.md)]

The Azure Cosmos DB for MongoDB migration extension helps you in migrating your MongoDB workloads to Azure Cosmos DB. You can use this extension to:

- Run an end-to-end assessment on your workload and find out the necessary actions you need to take to migrate your workloads to vCore-based Azure Cosmos DB for MongoDB.
- Perform the migration operation with selected databases and collections to vCore-based Azure Cosmos DB for MongoDB.

> [!IMPORTANT]
> Currently this extension doesn't support the following scenarios:
>
> - Migration where source  or target account are Private Endpoint enabled.
> - Online/Offline Migrations for RU-based Azure Cosmos DB for MongoDB.
>
> For more information on alternate solutions for the API for MongoDB vCore, see [migration options](/azure/cosmos-db/mongodb/vcore/migration-options).

## Prerequisites

- An existing vCore-based Azure Cosmos DB for MongoDB  account.
  - If you don't have an Azure subscription, [create an account for free](https://azure.microsoft.com/free).
- Latest version of [Azure Data Studio](..//download-azure-data-studio.md).
- [MongoDB](https://www.mongodb.com/) running version 3.2 or higher.
- Add firewall exceptions to the source MongoDB and vCore-based  Azure Cosmos DB for MongoDB target account to accept connections from global Azure datacenters.
- If you're using Database Migration Service for the first time, make sure that the [Microsoft.DataMigration resource provider is registered in your subscription](#register-microsoftdatamigration-resource-provider-in-your-subscription).

## Prepare

Before starting the migration, carry out up-front planning and decision-making about your migration before you actually move any data.

- For more information about premigration planning for the API for MongoDB vCore, see [premigration steps for vCore-based Azure Cosmos DB for MongoDB](/azure/cosmos-db/mongodb/vcore),
- For more information about premigration planning for the API for MongoDB RU, see [premigration steps for RU-based Azure Cosmos DB for MongoDB](/azure/cosmos-db/mongodb/pre-migration-steps)

### Register Microsoft.DataMigration resource provider in your subscription

To ensure that the Microsoft.DataMigration resource provider is registered in your subscription, you can follow these steps:

Azure portal:

1. Go to the Azure portal and navigate to your subscription.
2. In the left-hand menu, select Resource providers under Settings.
3. Search for Microsoft.DataMigration in the search box at the top.
4. If it is not registered, select it and click on the Register button.

Azure CLI:

1. Open the Azure Cloud Shell or your local terminal.
2. Run the following command to register the resource provider:

```azurecli
az provider register --namespace Microsoft.DataMigration
```

PowerShell:

1. Open the Azure Cloud Shell or your local PowerShell.
2. Run the following command to register the resource provider:

```powershell
Register-AzResourceProvider -ProviderNamespace "Microsoft.DataMigration"
```

## Install the extension

Install the Azure Cosmos DB for MongoDB migration extension in Azure Data Studio before you begin your migration.

1. Open the **extensions manager** in Azure Data Studio. Either select the extensions icon or select **Extensions** in the View menu.

1. Enter `Cosmos` in the search bar.

1. Select the **Azure Cosmos DB Migration for MongoDB** extension and view its details.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/extension-install.png" lightbox="media/azure-cosmos-db-mongodb-migration/extension-install.png" alt-text="Screenshot of Azure Cosmos DB for MongoDB migration extension install button.":::

1. Select **Install**.

## Configure extension settings

You can configure some extension settings after installing the extension. This step is optional. If no settings are explicitly configured, the extension uses default settings.

1. Go to extensions and select **Azure Cosmos DB Migration for MongoDB**, select the **manage settings icon**, and then select extension settings.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/extension-settings.png" lightbox="media/azure-cosmos-db-mongodb-migration/extension-settings.png" alt-text="Screenshot of extension settings selection.":::

1. Under extension settings for this extension, provide the `Assessment path` to change the location where the assessment metadata is stored. If left blank, the default location is used.

## Connect to the MongoDB source

Use the extension for the first time to connect to the existing MongoDB source instance. Ensure that you have the connection credentials for the source ready before starting this section.

1. Locate the connections icon in the menu bar, and select **New Connection**.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/new-connection.png" lightbox="media/azure-cosmos-db-mongodb-migration/new-connection.png" alt-text="Screenshot of the connections menu bar in the extension.":::

1. In the **Connection** pane, fill out the following fields:

    | | Value |
    | --- | --- |
    | **Connection type** | `Azure Cosmos DB for MongoDB` |
    | **Connection string/Parameters** | *Use the connection string or parameters for your existing source MongoDB instance.* |
    | **Server group** | `Default` |
    | **Name (optional)** | *Provide a unique name for this connection.* |

1. Select **Connect**.

1. Open the *context menu* for the new connection in the **Connections** pane. Then, select **Manage**.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/manage.png" lightbox="media/azure-cosmos-db-mongodb-migration/manage.png" alt-text="Screenshot of the Manage database screen.":::

1. Select **Azure Cosmos DB Migration**.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/landing-page.png" lightbox="media/azure-cosmos-db-mongodb-migration/landing-page.png" alt-text="Screenshot of the Migration Assessment database screen.":::

## Run an assessment

The assessment examines your current MongoDB data estate and utilization. The assessment feature then generates a comprehensive report that helps you identify the necessary actions to take before migrating your workloads to Azure Cosmos DB for MongoDB.

1. Locate and navigate to the **Dashboard** tab. Then, select **Assess and Migrate Databases(s)**.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/dashboard.png" lightbox="media/azure-cosmos-db-mongodb-migration/dashboard.png" alt-text="Screenshot of the Dashboard tab within the migration feature of the extension.":::

1. Complete the wizard to provide details to the extension so that it can perform an assessment.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/validate-credentials.png" lightbox="media/azure-cosmos-db-mongodb-migration/validate-credentials.png" alt-text="Screenshot of assessment details before credentials are validated.":::

    1. In the **Assessment name** field, enter a title.

    1. Select the target Azure Cosmos DB for MongoDB account from the **Offering** dropdown.

    1. Provide the path to **MongoDB Logs**.

        > [!TIP]
        > This is an optional field, however specifying the logs path results in more granular findings at the collection level. When the log folder isn't specified, the tool uses details from the `serverStatus` command to perform the assessment.
        >
        > The `serverStatus` command returns feature usage only since the last restart, so you would need to ensure that sufficient time has passed since the last server restart to get an assessment that accurately reflects your actual workload.

    1. Provide the path to **Data assessment logs**.
    
        > [!TIP]
        > Although this field is optional, providing data assessment logs can yield more detailed insights about the workload. These logs are obtained by scanning data and reading verbose logs. The data assessment runs independently as a CLI before initiating the migration assessment, and the resulting JSON is then supplied here. Download the data assessment CLI [here](https://aka.ms/MongoMigrationDataAssessment).


    1. Select **Run validation** to validate the assessment inputs.

1. Once the validation is successful, select **Start assessment** to run the assessment.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/start-assessment.png" lightbox="media/azure-cosmos-db-mongodb-migration/start-assessment.png" alt-text="Screenshot of assessment details after credentials are validated.":::

1. Depending on the size of your source server, the assessment takes a few minutes. Wait for the assessment to complete before continuing.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/assessment-in-progress.png" lightbox="media/azure-cosmos-db-mongodb-migration/assessment-in-progress.png" alt-text="Screenshot of a new assessment in progress.":::

1. After the assessment is complete, you should now have an assessment report.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/assessment-report.png" lightbox="media/azure-cosmos-db-mongodb-migration/assessment-report.png" alt-text="Screenshot of the new assessment report for the source MongoDB instance.":::

1. In the assessment report, select the instance name to review a list of server-wide issues. Select a specific database to view issues that are only applicable to the selected database.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/assessment-for-selected-database.png" lightbox="media/azure-cosmos-db-mongodb-migration/assessment-for-selected-database.png" alt-text="Screenshot of the new assessment report for the selected database within the source MongoDB instance.":::

1. Select **Download Report** to get a consolidated downloadable report.

1. Study the assessment report to identify any actions you need to take for a seamless migration of your workloads on Azure Cosmos DB for MongoDB. Before moving to the next step, ensure that all blocking issues reported in the assessment are handled. If there are any unresolved issues, you can exit the process and handle them later. Once the issues are resolved, you can come back and restart the assessment and migration process.

## Perform a migration

Now, use the assessment report to perform a migration of your data from your source MongoDB instance to your target vCore-based Azure Cosmos DB for MongoDB account.

1. In the assessment report screen, select any databases you plan to migrate. Then, select **Next**.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/select-database-for-migration.png" lightbox="media/azure-cosmos-db-mongodb-migration/select-database-for-migration.png" alt-text="Screenshot of the database selected for migration.":::

1. Narrow down the lists to Select the target Azure Cosmos DB for MongoDB account by filtering by subscription and then resource group. Then provide connection credentials necessary to connect to the account.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/select-target-account.png" lightbox="media/azure-cosmos-db-mongodb-migration/select-target-account.png" alt-text="Screenshot of the selection of a target Azure Cosmos DB for MongoDB account.":::

1. Select **Test connection** to validate the credentials for the Azure Cosmos DB for MongoDB account. Select **Next** to navigate to the mapping of collections from the source to the target.

1. Choose either **Skip** or **Migrate** for each collection in the list of mappings. Collections that already exist in the target are automatically marked with an icon and set to **Skip** by default. Select **Next** to configure the Azure Database Migration Service (DMS).

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/collection-mapping.png" lightbox="media/azure-cosmos-db-mongodb-migration/collection-mapping.png" alt-text="Screenshot of the mapping of collections from the source to the target.":::

    > [!WARNING]
    > Opting to **Migrate** an existing collection will overwrite the entire collection, resulting in irrecoverable data loss. Please exercise caution when choosing this option.

1. Choose an existing Azure Database Migration Service instance from the dropdown or select **Create New** to create a new migration service. Azure Database Migration Service is a service that migrates data to and from Azure data platforms by using cloud infrastructure for data transfer, instead of relying on local resources.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/select-migration-service.png" lightbox="media/azure-cosmos-db-mongodb-migration/select-migration-service.png" alt-text="Screenshot of the option to choose a migration service.":::

1. Select the migration mode that's most appropriate for your use case.
    - **Online migration** copies collection data, ensuring updates are also replicated during the process. This method is advantageous with minimal downtime, allowing continuous operations for business continuity. Use this option when ongoing operations are crucial, and reducing downtime is a priority.
    - **Offline migration** captures a snapshot of the database at the beginning, offering a simpler and predictable approach. It works well when using a static copy of the database is acceptable, and real-time updates aren't essential.

> [!IMPORTANT]
> To ensure successful online migrations from MongoDB, ChangeStream must be enabled on the source MongoDB server. Without ChangeStream, any modifications made to the data after the initial migration will not be captured in the target system, potentially causing data inconsistencies. Therefore, use the online migration mode only if ChangeStream is enabled on your source MongoDB server.

1. Select **Next** to view the migration summary. Once you reviewed and confirmed the details, select **Create Schema** to create resources on the target account.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/view-summary.png" lightbox="media/azure-cosmos-db-mongodb-migration/view-summary.png" alt-text="Screenshot of option to view migration summary.":::

1. Select **Start Migration** to initiate the data transfer using the selected migration service.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/start-migration.png" lightbox="media/azure-cosmos-db-mongodb-migration/start-migration.png" alt-text="Screenshot of the option to start a migration using the migration service.":::
1. In the Confirm Settings pop-up, verify that your firewall settings meet the requirements. Select **OK** to confirm.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/connection-confirmation.png" lightbox="media/azure-cosmos-db-mongodb-migration/connection-confirmation.png" alt-text="Screenshot of the Confirm Settings pop-up, to verify your firewall settings.":::



The data migration tasks are run on Azure Database Migration Service hence you aren't required to be connected to the source and target environments during the data migration. The status is updated on the dashboard at frequent intervals

 >[!NOTE]
 > If you selected more than 50 collections to migrate, the migration job will be batched into multiple jobs on the migration service, each containing max of 50 collections.

1. Monitor the migration status on the dashboard page once the jobs are initialized.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/monitoring-dashboard.png" lightbox="media/azure-cosmos-db-mongodb-migration/monitoring-dashboard.png" alt-text="Screenshot of dashboard with migration status.":::

1. To view more details, select a specific migration from the list of migrations.

### Monitoring Offline migrations

The status is automatically updated once all data migration tasks are finished.

:::image type="content" source="media/azure-cosmos-db-mongodb-migration/monitoring-collections-list.png" lightbox="media/azure-cosmos-db-mongodb-migration/monitoring-collections-list.png" alt-text="Screenshot of collections with migration status.":::

Once the data is successfully copied from the source to the target, offline migrations status indicates success.

:::image type="content" source="media/azure-cosmos-db-mongodb-migration/migration-success.png" lightbox="media/azure-cosmos-db-mongodb-migration/migration-success.png" alt-text="Screenshot of success in migration status.":::

- Change the connection string in your applications to point to the target account.

### Monitoring Online migrations

Online migrations, unlike offline migrations, don't automatically complete. Instead, they run continuously until they're manually finalized by selecting **Cutover**.

:::image type="content" source="media/azure-cosmos-db-mongodb-migration/monitoring-online-migration.png" lightbox="media/azure-cosmos-db-mongodb-migration/monitoring-online-migration.png" alt-text="Screenshot of online migration status.":::

To complete the online migration, follow these steps in the given order:
1. The **Cutover** button is enabled once the Initial Data Load is completed for all collections. The migration is currently in the replication phase, continuously copying updates from the source instance to the target instance to keep it up-to-date with the latest changes.

   
3. When ready to perform the migration cutover, stop all incoming transactions to the source collections being migrated.
1. Monitor the replication changes in the table and wait until the 'Replication Changes Played' metric stabilizes. A stable 'Replication Changes Played' metric indicates that all updates from the source are successfully copied to the target.
1. Select **Cutover** when the replication gap is minimal for all collections and the 'Replication Changes Played' metric is stable.
1. Manually validate that the row count is the same between the source and target collections.
1. In the pop-up dialog. Select **Complete Cutover**.  
    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/monitoring-online-migration-cutover.png" lightbox="media/azure-cosmos-db-mongodb-migration/monitoring-online-migration-cutover.png" alt-text="Screenshot of online migration cutover pop-up.":::
    >[!NOTE]
    >Performing the cutover operation without validating that the source and target are synced may result in data loss.
1. Wait for the status to change to **Succeeded**.
1. Update the connection string in your applications to point to the target account.

## View past migrations and assessments

It's often useful to review past assessments and migrations. The extension provides an interface to review summaries of past assessment and migrations. The extension also provides the capability to review detailed historical assessment reports.

1. To view past migrations, select the **Migrations** tab in the toolbar. The migrations list contains all migrations that were initiated on the current machine. You can select on a specific migration in the list to get more details.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/migrations-list.png" lightbox="media/azure-cosmos-db-mongodb-migration/migrations-list.png" alt-text="Screenshot of the list of all migrations created using the extension.":::

1. To view past assessments, select the **Assessments** tab in the toolbar. The assessments list contains all assessments that were initiated on the current machine.

    :::image type="content" source="media/azure-cosmos-db-mongodb-migration/assessments-list.png" lightbox="media/azure-cosmos-db-mongodb-migration/assessments-list.png" alt-text="Screenshot of the list of all assessments performed using the extension.":::

## Next step

> [!div class="nextstepaction"]
> [Review FAQ for the Azure Cosmos DB for MongoDB migration extension](azure-cosmos-db-mongodb-migration-faq.yml)
