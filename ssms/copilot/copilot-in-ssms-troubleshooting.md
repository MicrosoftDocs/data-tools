---
title: "Troubleshooting"
titleSuffix: Copilot in SQL Server Management Studio
description: Learn how to troubleshoot issues with Copilot in SQL Server Management Studio.
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 05/19/2025
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

## Error messages

| Error | Next steps |
| --- | --- |
| Invalid URI: the format of the URI could not be determined | Ensure the values for endpoint and deployment haven't been swapped accidentally. |
| Unknown endpoint: `'https://value_for_endpoint_here'`. Please verify the endpoint. | Confirm you have the correct value for the Azure OpenAI endpoint. |
| The API deployment for this resource does not exist. | If the deployment was created in the last five (5) minutes, wait and then try again. |
| | Confirm you have the correct value for the Azure OpenAI deployment. |
| | Confirm there are no blank spaces at the beginning or end of the deployment name. |
| | If the value for the deployment is correct and the deployment was just created, wait a few minutes and try again. |
| Access denied due to invalid subscription key or wrong API endpoint. Make sure to provide a valid API key for an active subscription and use the correct regional API endpoint for your resource. | Confirm the configuration of your deployment and whether it uses Microsoft Entra authentication or API key. This error can appear if your deployment uses Microsoft Entra authentication and you enter an API key. |
| | If your deployment uses an API key, confirm the API key you have is correct and that hasn't been rotated to a new value. |
| HTTP 429 error | The endpoint has been throttled. |
