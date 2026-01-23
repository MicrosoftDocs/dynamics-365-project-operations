---
title: Synchronize resource capacity
description: This article provides information about how to synchronize a resource's capacity across calendars and projects.
author: tulsij
ms.author: dishantpopli
ms.date: 01/23/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.search.form: ProjProjectsListPage
ms.reviewer: johnmichalak
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898

---

# Synchronize resource capacity

[!include [banner](../includes/banner.md)]

The resource synchronization processes help guarantee that information for the calendar and base calendar trickles down into project resource scheduling. If you change the calendar, the processes make the required updates to the scheduling of project resources. The processes also help improve performance, because the calendar's resource information is synchronized in advance. Therefore, updates to resource scheduling information occur more quickly. Schedule the processes as a batch instead of one at a time. Otherwise, there's a risk that someone forgets the inclusive dates when the information was last synchronized. If inclusive dates aren't used, gaps can occur during date synchronization.

:::image type="content" source="./media/projectresourcing04-1024x471.jpg" alt-text="Screenshot of calendar synchronization process flow.":::

## Synchronize resource capacity roll-ups

The synchronization process is designed to synchronize all resource calendar information. This information includes base calendar information about any changes to the project's Resource calendar capacity table. If you add new resources in the project, synchronization helps guarantee that the updated calendar information is available. You can perform this synchronization at any time.

Use a batch. The options are available during synchronization of capacity reservations.

1. Select **Project management and accounting** &gt; **Periodic** &gt; **Capacity synchronization** &gt; **Synchronize resources capacity roll-ups**.
1. Set the options in the following table.

    | Option      | Description |
    |-------------|-------------|
    | Period code | Optionally select the General ledger date interval code to set the start and end dates for the synchronization process for resource capacity roll-ups. |
    | Start date  | Enter the start date for the synchronization process for resource capacity roll-ups. |
    | End date    | Enter the end date for the synchronization process for resource capacity roll-ups. |

:::image type="content" source="./media/projectresourcing09.jpg" alt-text="Screenshot of the synchronization process dialog box.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
