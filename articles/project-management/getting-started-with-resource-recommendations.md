---
# required metadata

title: Get recommendations for a project team member
description: This article provides information about steps to be completed in order to use the resource recommendations feature for the first time.
author: mohitmenon
ms.date: 10/01/2024
ms.topic: article
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Pre-requisites to use this feature

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_


## Enabling the resource recommendations feature

To enable resource recommendations, first follow these steps:

1.	Sign in to Microsoft **Dynamics 365 Project Operations**.
2.	In the left navigation, change the area to **Settings**.
3.	In the **General** section, select **Parameters**.
4.	You should see a list of organization units. Double-tap (or double-click) the Organization Units row for the columns that aren't links.
5.	On the **Project Parameters** page, in the **Feature Control** field, select Feature Control.
6.	Select **Enable Resource Recommendations Feature**.

## Get system administrator to activate dataflows 

Once you have completed this step, you must now activate 4 [dataflows](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/create-and-use-dataflows) with the help of your System Administrator. This is a mandatory, one-time step that must be completed on every new environment on which this feature is to be enabled. These workflows prepare the data infrastructure that is required to generate optimal recommendations for any new project team member.

To activate these dataflows, have your System Administrator complete the following steps:

1. Sign in to your Microsoft **Dynamics 365 Project Operations** environment.
2. Open a new tab and sign in to the [**Power Apps Portal**](make.powerapps.com). For more information on the Power Apps portal, please refer to [this page](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/sign-in-to-power-apps).
3. In the **Environments** section on the top-right, ensure that the environment you are logged into is selected.
4. Now use the left navigation pane, to select **Dataflows**. If this is not directly visible, then select **More** and then Dataflows.
5. Select the **All Dataflows** tab, this should display a list of 4 dataflows. Each Dataflow has a number as prefix, this is to indicate the order in which they need to be activated.
6. Start with the first dataflow, **1. Resource Recommendation - Daily KPE**. Click the overflow icon (three dots) and select **Edit**.
7. This navigates you to a Power Query page, with details for the selected dataflow. Select the **_EnvironmentName_ parameter** and enter the URL of the environment being used. _(Eg: demo-testing.crm.dynamics.com)_ within the space provided for **Current Value** and click **Manage Parameter**.
8. ...
9. ...
10. ...
11. Now Repeat Steps 6 to 10 for the remaining 3 dataflows, in order of their numbering.
12. Tracking completion of dataflows.
13. Once all 4 workflows are complete, you can now start getting recommendations for project team members. Refer to **Next Section** for more details on how to use the feature.
