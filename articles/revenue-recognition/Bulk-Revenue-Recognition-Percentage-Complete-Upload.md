---
title: Bulk update revenue recognition completion percentages
description: Learn how to update revenue recognition completion percentages in bulk using Excel Add-in and Data Management Framework (DMF)
author: sarangkusare
ms.date: 10/22/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: sarangkusare
---

# Bulk update revenue recognition completion percentages

[!INCLUDE [banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations for manufacturing_

Organizations that use the **Manual Percentage Complete** method for revenue recognition often need to update completion percentages across a large number of projects before posting revenue recognition.

The Bulk Revenue Recognition Completion Percentage feature enables organizations to maintain manual revenue recognition percentages for multiple projects through Excel and Data Management Framework (DMF). By supporting bulk updates, the feature reduces administrative effort and improves the efficiency of period-end revenue recognition processes.

Before this feature, users had to open individual projects and manually update completion percentages one project at a time. This process could be time-consuming and error-prone when managing large project portfolios.

This feature introduces a revenue recognition completion percentage entity that supports bulk maintenance of completion percentages through the Excel Add-in and Data Management Framework (DMF).

This feature provides the following benefits:

- Reduces manual effort required to maintain revenue recognition percentages.
- Enables updates for multiple projects in a single operation.
- Supports period-end processing activities.
- Improves efficiency for finance and project accounting teams.
- Eliminates the need to navigate to individual projects for updates.

This feature is available starting in version **10.0.50** and is also available in version **10.0.49** through a backport.

## Prerequisites

This feature applies to:

- Project Operations Integrated deployments
- Project Operations Manufacturing deployments

Before using this feature, ensure you meet the following prerequisites:

- Revenue recognition is configured.
- Projects use the Manual Percentage Complete method.
- Revenue recognition periods are generated.
- Users have appropriate access to the Revenue Recognition Completion Percentage entity.

## Process flow

The following process is typically used during period-end activities.

### Step 1: Generate revenue recognition periods

Run the Revenue Recognition batch process for active projects.

This process creates revenue recognition period records that you can update.

### Step 2: Update completion percentages

Update completion percentages by using either:

- Excel Add-in
- Data Management Framework (DMF)

Update the required values and save the changes.

### Step 3: Refresh the application

If you completed updates through Excel, refresh the Revenue Recognition page to view the latest values.

### Step 4: Post revenue recognition

After you update and review the completion percentages, run the Revenue Recognition posting process.

## Update completion percentages by using Excel

The Excel add-in provides an interactive experience for updating multiple projects simultaneously. 

To update completion percentages by using Excel, follow these steps:

1. Open the Revenue Recognition Completion Percentage entity.
1. Select **Open in Excel** > **Project revenue recognition completion percentages**.
1. Export the available records.
1. Update the completion percentage values.
1. Publish the changes back to Dynamics 365.
1. Refresh the application to verify the updates.

## Update completion percentages by using Data Management Framework

You can use the Data Management Framework for larger update scenarios.

To update completion percentages by using Data Management Framework, follow these steps:

1. Create an import project.
1. Select the Revenue Recognition Completion Percentage entity.
1. Upload the source file.
1. Validate the data.
1. Run the import job.
1. Review the execution results.

## Entity behavior

Only revenue recognition periods with a status of **Created** are available for update.

This behavior ensures that users can modify only records that are eligible for revenue recognition adjustments.

Revenue recognition periods that progress beyond the Created status aren't returned for update.

## Best practices

- Generate revenue recognition periods before exporting data.
- Review and validate completion percentages before posting revenue recognition.
- Use the Excel add-in for day-to-day updates.
- Use DMF for large-volume updates.
- Establish review and approval controls for period-end updates.

## Common problems

| Problem | Resolution |
| ----- | ---------- |
| No records are available for update | Verify that revenue recognition periods are generated and are in Created status. |
| Updated values aren't visible | Refresh the application after publishing changes from Excel. |
| Import validation errors occur | Verify project identifiers and completion percentage values. |
| Records can't be updated | Verify that the revenue recognition period status is Created. |
