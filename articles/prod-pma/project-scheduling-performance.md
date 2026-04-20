---
title: Project resource scheduling performance
description: Learn how to resolve resource scheduling performance issues. This guide explains how to enable features that speed up resource availability and reduce sync times.
author: Yowelle
ms.date: 01/30/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: andchoi
ms.dyn365.ops.version: 10.0.14
ms.search.validFrom: 2020-09-01
---
# Project resource scheduling performance

[!include [banner](../includes/banner.md)]

Performance problems related to resource scheduling can happen when the number of projects reaches into the thousands. To improve resource scheduling performance, a feature is available that reduces the time it takes to launch the resource availability page. This feature removes the resource capacity roll-up synchronization process and uses the **ResProjectResource** table to speed up the resource lookup. The **ResRollup** table is no longer used.

This feature is enabled by default in release 10.0.36 or later. Changes in this release let you enable the feature without blocking previous behavior. If you see the warning message that tells you to run the **Populate project resources across all companies** batch job, run the batch job and complete the update to finish enabling the feature.

> [!IMPORTANT]
> Don't use this feature if there's a dependency on either the resource capacity roll-up synchronization process or the **ResProjectResource** table.

## Enable resource scheduling performance enhancement

To enable resource scheduling performance enhancement, complete the following steps.

1. Go to **Feature management** > **All**, and in the feature list, locate **Enable project resource scheduling performance enhancement feature**.
1. Select **Enable now**.

  > [!NOTE]
  > If you can't find the feature in the list, select **Check for updates** to refresh the list.

1. Refresh your browser, and then go to **Project management and accounting** > **Periodic** > **Project resources** > **Synchronize resource calendars capacity across all companies**.
1. Set **Remove existing capacity records** to **Yes** to remove previous data. To generate incremental data, set it to **No**.
1. In the **Period code** field, select the period in which data should be generated. If you select a period code, you don't need to define the start and end date.
1. If you leave the **Period code** field blank, select specific start and end dates to generate data.
1. Select **OK**.

This batch job populates resources associated calendars' capacity hours. When you run this batch job, you need to provide a start and end date. As time progresses and you need to schedule beyond the batch job end date, run the batch job again and set the end date to the next appropriate date. If you make any changes to the calendar time, such as adding a holiday or modifying the working hours for a specific date, run the batch job again to reflect those changes.

   > [!NOTE]
   > This process distributes general data to the **ResCalendarCapacity** table across all companies in your environment, so you only need to run the batch job in one legal entity. The data in this batch job is needed to calculate resource capacity through the associated calendar.

1. Go to **Project management and accounting** > **Periodic** > **Project resources** > **Populate project resources across all companies** and then select **OK**. This process runs the one-time data upgrade script for general data in the **ResProjectResource**, **ResCalendarDateTimeRange**, and **ResEffectiveDateTimeRange** tables. It also updates values for the **PSAPRojSchedRole.RootActivity** field. If you don't run this process, you receive a warning when you try to run resource scheduling operations.

## Turn off resource scheduling performance enhancement

Don't turn off this feature. If you find a critical problem, you can follow these steps to disable the feature.

1. Go to **Feature management** > **All**  and search for **Enable project resource scheduling performance enhancement feature**.
1. Select the feature, and then select the **Disable** button.
1. Refresh your browser.
1. Go to **Project management and accounting** > **Periodic** > **Capacity synchronization** > **Synchronize resource capacity roll-ups**.
1. On the **Capacity roll-up synchronization** page, set **Remove existing capacity records** to **Yes** to remove previous data. If you want to generate incremental data, set it to **No**.
1. In the **Period code** field, select the period in which data should be generated. If you select a period code, a start and end date don't need to be defined.
1. If you leave the **Period code** field blank, select specific start and end dates to generate data.
1. Select **OK**.

> [!NOTE]
> This process distributes general data to the **ResRollup** table across all companies in your environment, so you only need to run the batch job in one legal entity. All **Resource Availability** views need this batch job. If you don't run this batch job, the system generates **ResRollup** data on the fly, which can take time.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
