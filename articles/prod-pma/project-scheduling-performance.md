---
title: Project resource scheduling performance (preview)
description: This article provides information about how to improve the performance of resource scheduling for a large number of projects.
author: Yowelle
ms.date: 09/07/2023
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
[!include [banner](../includes/preview-banner.md)]


Performance issues related to resource scheduling can occur when the number of projects reaches into the thousands. To improve resource scheduling performance, a feature is available that allows users to reduce the time that it takes to launch the resource availability page. Specifically, this feature removes the resource capacity roll-up synchronization process and uses the **ResProjectResource** table to speed up the resource lookup. The **ResRollup** table is no longer used.

This feature is enabled by default in release 10.0.36 or later. Changes have been made in this release to let the feature be enabled and not block previous behavior. It's suggested that if you see the warning message telling you to run the **Populate project resources across all companies** batch job, that you do so and complete the update to finish enabling the feature. 

> [!IMPORTANT]
> If there is a dependency on either the resource capacity roll-up synchronization process or the **ResProjectResource** table, don't use this feature.

## Enable resource scheduling performance enhancement
To enable resource scheduling performance enhancement, complete the following steps.

1. Go to **Feature management** > **All**, and in the feature list, locate **Enable project resource scheduling performance enhancement feature**.
2. Select **Enable now**.

  > [!NOTE]
  > If you can't find the feature in the list, select **Check for updates** to refresh the list.

3. Refresh your browser, and then go to **Project management and accounting** > **Periodic** > **Project resources** > **Synchronize resource calendars capacity across all companies**.
4. Set **Remove existing capacity records** to **Yes** to remove previous data. If you want to generate incremental data, set it to **No**.
5. In the **Period code** field, select the period in which data should be generated. If you select a period code, you don't need to define the start and end date.
6. If you leave the **Period code** field blank, select specific start and end dates to generate data.
7. Select **OK**.

This batch job is used to populate resources associated calendars' capacity hours. When you run this batch job, a start and end date is required. As time progresses and you need to schedule beyond the batch job end date, then the batch job needs to be run again and set the end date to the next appropriate date. If you have made any changes to the calendar time, such as adding a holiday or modifying the working hours for a specific date, you need to run the batch job again to reflect those changes.

   > [!NOTE]
   > This will distribute general data to the **ResCalendarCapacity** table across all companies in your environment, so the batch job only needs to be run in one legal entity. The data in this batch job is needed to calculate resource capacity through the associated calendar.

8. Go to **Project management and accounting** > **Periodic** > **Project resources** > **Populate project resources across all companies** and then select **OK**. This is the one-time data upgrade script for general data in the **ResProjectResource**, **ResCalendarDateTimeRange**, and **ResEffectiveDateTimeRange** tables. Values for the **PSAPRojSchedRole.RootActivity** field are also updated. If this isn't run, you'll receive a warning when you try to run resource scheduling operations.
 
## Turn off resource scheduling performance enhancement
It's recommended you don't turn off this feature. If a critical issue is found, you can follow these steps to disable the feature. 

1. Go to **Feature management** > **All**  and search for **Enable project resource scheduling performance enhancement feature**.
2. Select the feature, and then select the **Disable** button.
3. Refresh your browser.
4. Go to **Project management and accounting** > **Periodic** > **Capacity synchronization** > **Synchronize resource capacity roll-ups**.
5. On the **Capacity roll-up synchronization** page, set **Remove existing capacity records** to **Yes** to remove previous data. If you want to generate incremental data, set it to **No**.
6. In the **Period code** field, select the period in which data should be generated. If you select a period code, a start and end date don't need to be defined.
7. If you leave the **Period code** field blank, select specific start and end dates to generate data.
8. Select **OK**.

> [!NOTE]
> This will distribute general data to the **ResRollup** table across all companies in your environment, so the batch job only needs to be run in one legal entity. This batch job is needed for all **Resource Availability** views. If this batch job isn't run, the **ResRollup** data will be generated on the fly, which can take time.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
