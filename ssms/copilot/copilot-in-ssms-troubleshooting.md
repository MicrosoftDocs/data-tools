---
title: "Troubleshooting"
titleSuffix: Copilot in SQL Server Management Studio
description: Learn how to troubleshoot issues with Copilot in SQL Server Management Studio.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 06/13/2025
ms.service: sql-server-management-studio
ms.topic: concept-article
ms.collection:
  - ce-skilling-ai-copilot
# CustomerIntent: As a database administrator or database developer, I want to understand how to troubleshoot issues with Copilot in SQL Server Management Studio.
---

# Troubleshooting issues with Copilot in SQL Server Management Studio

## General logging

In scenarios where more details are needed to investigate a problem, you can view Copilot commands in the output window using **View** > **Output** and selecting **Copilot** from the dropdown list. Alternatively, you can save the information using the `/log` command in the prompt box.

## Configuration

If you enter the endpoint and deployment values in the first-run experience (initial dialog when you first launch Copilot) and the progress bar repeats, check your browser for a Microsoft Entra authentication dialog.

## Log capture

If you get an error after entering the endpoint and deployment values in the first-run experience (initial dialog when you first launch Copilot), use the list of error messages to troubleshoot further, or capture logs in the output window.

1. Go to **Tools > Options > Copilot** to enter the endpoint and deployment values, then select **OK**.
1. No validation occurs in this dialog.
1. Before you open Copilot, go to **View > Output** to open the output viewer.
1. Select the **Copilot** button on the toolbar to launch Copilot in SSMS.
1. Upon launch, you're prompted to authenticate to Azure, unless you're using an API Key.
1. If you don't see the prompt to authenticate, check your browser for a Microsoft Entra authentication dialog.
1. If you see an error in the Copilot chat, select **Copilot** from the dropdown list in the output viewer.
1. The information in the output viewer can be used for further troubleshooting.

## Test access

Use the Azure Command-Line Interfact (CLI) to verify you have access to the Azure OpenAI resources. The Azure CLI must be installed on the same machine as SQL Server Management Studio (SSMS). If the Azure OpenAI resources use Microsoft Entra authentication, you must use `az login` to [log in to Azure](/cli/azure/reference-index) before you run the PowerShell script. The script requires the name of the resource group in which the Azure OpenAI resources are hosted, and the name of the endpoint resource. If the script completes successfully, the available Azure OpenAI models are listed as the output.

```powershell
# Set your Azure OpenAI resource values
$resourceGroup = "msdocs-azuresql-rg-$randomIdentifier"
$resourceName = "copilot-in-ssms"

# ---- Get the endpoint ----
$endpoint = az cognitiveservices account show `
    --name $resourceName `
    --resource-group $resourceGroup `
    --query "properties.endpoint" `
    --output tsv

if (-not $endpoint) {
    Write-Host "Couldn't retrieve endpoint. Check resource group/name." -ForegroundColor Red
    exit 1
}

# ---- Get an API key for the resource ----
$apiKey = az cognitiveservices account keys list `
    --name $resourceName `
    --resource-group $resourceGroup `
    --query "key1" `
    --output tsv

if (-not $apiKey) {
    Write-Host "Couldn't retrieve API key. Check permissions." -ForegroundColor Red
    exit 1
}

# ---- Make a request to /openai/models ----
$headers = @{
    "api-key" = $apiKey
    "Content-Type" = "application/json"
}
$url = "$endpoint/openai/models?api-version=2024-02-01"

try {
    $response = Invoke-RestMethod -Method Get -Uri $url -Headers $headers
    Write-Host "✅ Successfully connected to Azure OpenAI endpoint and listed models:" -ForegroundColor Green
    $response.data | Select-Object id
}
catch {
    Write-Host "❌ Failed to connect or authenticate with Azure OpenAI endpoint." -ForegroundColor Red
    Write-Host $_.Exception.Message
    exit 1
}
```

## Error messages

| Error | Next steps |
| --- | --- |
| Invalid URI: the format of the URI could not be determined | Ensure the values for endpoint and deployment aren't accidentally swapped. |
| Unknown endpoint: `'https://value-for-endpoint.openai.azure.com/'`. Please verify the endpoint. | Confirm you have the correct value for the Azure OpenAI endpoint. |
| The API deployment for this resource does not exist. | If the deployment was created in the last five (5) minutes, wait and then try again. |
| | Confirm you have the correct value for the Azure OpenAI deployment. |
| | Confirm there are no blank spaces at the beginning or end of the deployment name. |
| | If the value for the deployment is correct and the deployment was recently created, wait a few minutes and try again. |
| Access denied due to invalid subscription key or wrong API endpoint. Make sure to provide a valid API key for an active subscription and use the correct regional API endpoint for your resource. | Confirm the configuration of your deployment and whether it uses Microsoft Entra authentication or API key. This error can appear if your deployment uses Microsoft Entra authentication and you enter an API key. |
| | If your deployment uses an API key, confirm the API key you have is correct and didn't rotate to a new value. |
| HTTP 400 error | The deployment isn't configured with the `gpt-4o` model. |
| HTTP 429 error | The endpoint has been throttled. |
