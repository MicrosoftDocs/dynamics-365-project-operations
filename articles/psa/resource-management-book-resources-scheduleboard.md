---
title: Use the Schedule Board to book project resources
description: This article provides information about how to book resources.
author: ruhercul
ms.custom: 
  - dyn365-projectservice
ms.date: 03/28/2019
ms.topic: article
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---

# Use the Schedule Board to book project resources

[!include [banner](../includes/psa-now-project-operations.md)]

In addition to booking resources on a project from within a project, you can hard-book or soft-book resources from the Schedule Board.

Before you can book from the Schedule Board, you must create or generate resource requirements. Follow these steps to create resource requirements from the Schedule Board.

1. If the **Booking Requirements** pane at the bottom of the page is collapsed, select the expander control to expand it.
2. In the **Booking Requirements** pane, on the **Project** tab, select the requirement to book.

    ![Requirement selected on the Project tab.](media/Resource-Management-image73.png)

3. Select **Find Availability** to filter the bookable resources and view the available resources. 
4. Select one or more resources from the Schedule Board. 
5. In the **Create Resource Booking** pane on the right side of the page, enter the booking information, and then select **Book and exit**.

    ![Create Resource Booking pane for the selected bookable resource.](media/Resource-Management-image74.png)

6. While the requirement is selected in the **Create Resource Booking** pane, select one or more cells of a resource to create the booking.

    ![Multiple cells selected for a resource.](media/Resource-Management-image75.png)

7. Select **Book**.

The requirement is fulfilled by using the selected resource. In the **Booking Requirements** pane, notice that the requirement has been updated, and the resource is shown as booked on the project.

![Resource booked on the project.](media/Resource-Management-image76.png)


# Enabling and Disabling the new Schedule Board
Starting from the October 2023 early access release, the new Universal Resource Scheduling (URS) schedule board will be made available. For releases where the new board is on by default administrators will be able to re-enable the legacy schedule board. You will need to set the solution setting `msdyn_EnableOldScheduleBoard` to true. You can do so using the XRMUtility, or through a solution by [adding the settings solution component](/power-apps/maker/data-platform/create-edit-configure-settings#adding-an-existing-setting-environment-value).

An example of the [XRM Utility](/power-apps/developer/model-driven-apps/clientapi/reference/xrm-utility/getglobalcontext) command to change this setting:

```javascript
//Check the value of the setting
Xrm.Utility.getGlobalContext().getCurrentAppSettings()["msdyn_EnableOldScheduleBoard"] 

//Enable the legacy schedule board 
 Xrm.Utility.getGlobalContext().saveSettingValue("msdyn_EnableOldScheduleBoard", true, {overrideScope: 1}).then(() => {a = "success"}, (error) => {a = error})
 ```

Once the legacy schedule board has been enabled in your environment, users can switch between the legacy experience and the new experience directly on the schedule board. Please note, the legacy schedule board is on a path to deprecation and the ability to revert to the old board will not be supported long term.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
