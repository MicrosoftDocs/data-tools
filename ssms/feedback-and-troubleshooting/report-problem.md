---
title: Report a Problem with SQL Server Management Studio
description: Learn how to report a problem with SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest
ms.date: 12/01/2025
ms.service: sql-server-management-studio
ms.topic: troubleshooting-general
ms.collection:
  - data-tools
---

# Report a problem with SQL Server Management Studio

You can report a problem from SQL Server Management Studio (SSMS) using the **Help** > **Send Feedback** > **Report a Problem...** menu or by using the [SSMS user feedback site](https://aka.ms/ssms-feedback). When reporting an issue, search the site first to see if a similar issue exists. On the **Enter your problem** page, enter a title that concisely describes the issue, and include a description of the problem. Select **Search** to find similar issues.

A list of similar feedback tickets is displayed on the **Recommended solution** page. Review the existing feedback tickets to determine if there's one that describes the same problem you're experiencing. If an existing feedback ticket exists, select **This is exactly my problem** to upvote the feedback item. Select **Go to details and discussion** to add a comment that describes your scenario, or provides additional information about the problem.

If you can't find a similar problem, select **Can't find the solution**. On the **Submit a ticket** page, include step-by-step detailed instructions in the **Description** that explicitly describe how to recreate the problem. For any error message, include the entire text and use the **Show Details** button in the error dialog to capture complete details about the error to add to the item description. Select **Submit** when finished.

## Ticket status

After you report an issue, the status button indicates where the issue is in its lifecycle. As we review the issue and move it along the workflow, we update the status. The various statuses are listed here, along with a description of their meaning.

| Status | Description |
| --- | --- |
| **New** | The suggestion is newly reported, and no action has been taken yet. |
| **Triaged** | Your ticket is assigned to the appropriate engineering team for review. |
| **Under Investigation** | Engineers are actively investigating your problem to find a resolution. |
| **Needs More Info** | We need more diagnostic information from you so that we move go forward with the investigation. |
| **Under Consideration** | We review the problem for community impact and prioritize it accordingly. If the community impact isn't clear or significant, we continue to monitor the feedback item. |
| **Fixed - Pending Release** | We have a fix for the problem and it's available in an upcoming release. When the fix is available, the status updates to **Closed - Fixed**. |
| **Closed - Fixed** | We released a fix for the problem. |
| **Closed - Duplicate** | Your issue was reported in another feedback item. A link is provided for you to track the original problem report. |
| **Closed - Lower Priority** | To focus on bringing everyone in the community the best value, we prioritize issues with the highest customer impact. Although we're unable to address the issue at this time, all feedback is valuable and helps improve SSMS. |
| **Closed - Not a Bug** | The reported functionality isn't a problem in the current release, or exists by design. |
| **Closed - Not Enough Info** | We don't have enough information to investigate the issue. We reconsider feedback when the requested information is made available. |
| **Closed - Other Product** | The issue applies to another product. See the comment that includes the product and any related links. |

## Related content

- [Suggest a feature or improvement for SQL Server Management Studio](suggest-feature.md)
