---
title: Use the Schedule Board to book project resources
description: This article provides information about how to book resources.
author: tulsij
ms.author: dishantpopli
ms.custom: 
  - dyn365-projectservice
  - bap-template
  - evergreen
ms.date: 01/23/2026
ms.update-cycle: 1095-days
ms.topic: how-to
ms.reviewer: johnmichalak
---

# Use the Schedule Board to book project resources

[!include [banner](../includes/psa-now-project-operations.md)]

In addition to booking resources on a project from within a project, you can hard-book or soft-book resources from the Schedule Board.

Before you can book from the Schedule Board, you must create or generate resource requirements. Follow these steps to create resource requirements from the Schedule Board.

1. If the **Booking Requirements** pane at the bottom of the page is collapsed, select the expander control to expand it.
1. In the **Booking Requirements** pane, on the **Project** tab, select the requirement to book.

    :::image type="content" source="media/Resource-Management-image73.png" alt-text="Screenshot of a requirement selected on the Project tab.":::

1. Select **Find Availability** to filter the bookable resources and view the available resources.
1. Select one or more resources from the Schedule Board.
1. In the **Create Resource Booking** pane on the right side of the page, enter the booking information, and then select **Book and exit**.

    :::image type="content" source="media/Resource-Management-image74.png" alt-text="Screenshot of the Create Resource Booking pane for the selected bookable resource.":::

1. While the requirement is selected in the **Create Resource Booking** pane, select one or more cells of a resource to create the booking.

    :::image type="content" source="media/Resource-Management-image75.png" alt-text="Screenshot of multiple cells selected for a resource.":::

1. Select **Book**.

The requirement is fulfilled by using the selected resource. In the **Booking Requirements** pane, notice that the requirement is updated, and the resource is shown as booked on the project.

:::image type="content" source="media/Resource-Management-image76.png" alt-text="Screenshot of a resource booked on the project.":::

## Enabling and disabling the new Schedule Board

In the October 2023 early access release, the new Universal Resource Scheduling (URS) schedule board is available. For releases where the new board is turned on by default, administrators can re-enable the legacy schedule board. Set the solution setting `msdyn_EnableOldScheduleBoard` to **true**. To change `msdyn_EnableOldScheduleBoard`, use the XRMUtility or through a solution by [adding the settings solution component](/power-apps/maker/data-platform/create-edit-configure-settings#adding-an-existing-setting-environment-value).

An example of the [XRM Utility](/power-apps/developer/model-driven-apps/clientapi/reference/xrm-utility/getglobalcontext) command to change this setting:

```javascript
//Check the value of the setting
Xrm.Utility.getGlobalContext().getCurrentAppSettings()["msdyn_EnableOldScheduleBoard"] 

//Enable the legacy schedule board 
 Xrm.Utility.getGlobalContext().saveSettingValue("msdyn_EnableOldScheduleBoard", true, {overrideScope: 1}).then(() => {a = "success"}, (error) => {a = error})
 ```

When you enable the legacy schedule board in your environment, users can switch between the legacy experience and the new experience directly on the schedule board.

> [!NOTE]
> The legacy schedule board is on a path to deprecation, and the ability to revert to the old board won't be supported long term.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
