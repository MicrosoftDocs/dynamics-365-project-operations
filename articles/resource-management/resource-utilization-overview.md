---
title: Resource utilization overview
description: This article provides information about resource utilization in Project Operations.
author: ruhercul
ms.date: 11/05/2020
ms.topic: overview
ms.reviewer: johnmichalak
ms.author: ruhercul

---

# Resource utilization overview

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Resources can have a target billable utilization. This target utilization is defined as an attribute on a resource's default role or set on the record of the individual bookable resource. Utilization calculations are based on the actual hours that resources have reported by using approved time entries.

The following formulas are used to calculate utilization:

  - Billable utilization = Chargeable actual hours ÷ Resource capacity
  - Non-billable utilization = Actual time with billing type ID = Non-chargeable, Complementary, or Not available ÷ Resource capacity
  - Internal = Actual time with no sales contract ÷ Resource capacity
  - Resource capacity = Resource work hours – Out-of-office – Non-working days

You can find the **Resource Utilization** view in the **Resources** pane.

Each cell in the grid represents the billable utilization percentage of the resource in a period, such as a day, week, or month. The following formulas are used to color the cells:

  - **Green**: Billable utilization >= Resource target utilization
  - **Yellow**: Target utilization – 20 <= Billable utilization < Target utilization
  - **Red**: Billable utilization < Target utilization – 20

Because the **Resource Utilization** view is based on the Schedule Board, you can use the filtering capabilities of the Schedule Board to filter your results.

The grid requires that you set a target utilization on either the role or the individual resource. To do this setup, go to **Resources** > **Resource roles**.

Additionally, a default role must be assigned to each bookable resource. Go to **Resources** > **Resources**. On the **Project Service** tab, verify that a resource role is defined, and that the **Is Default** field is set to **Yes**. You can add additional roles where **Is Default** = **No**. The role where the **Is Default** = **Yes** is used to evaluate the resource's utilization against the target for that role.

On the **Project Service** tab, you can also set an individual target utilization for the resource. The utilization calculation then uses that target utilization to evaluate the resource's target instead of the target of the resource's default role.

Utilization is only shown for a resource if that resource has approved, chargeable time during the period shown in the grid.


[!INCLUDE[footer-include](../includes/footer-banner.md)]