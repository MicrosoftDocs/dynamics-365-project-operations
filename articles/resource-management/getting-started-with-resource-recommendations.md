---
# required metadata

title: Prerequisites to use resource recommendations (preview)
description: This article explains how to use the resource recommendations feature for the first time.
author: mohitmenon
ms.date: 03/19/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Prerequisites to use resource recommendations (preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

[!INCLUDE [preview-banner](../includes/preview-banner.md)]

## Enable the resource recommendations feature

To enable resource recommendations, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Ensure that you're using Project Operations version _4.91.0.X_ or later. The resource recommendations feature is available only in these versions. Project Operations version _4.103.0.X_ or later provides multi-factor recommendations. Versions before _4.91.0.X_ provide recommendations that are based on only one factor (**Relevant past experience**).
1. On the left navigation, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. A list of organization units should appear. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Resource Recommendation Engine Feature**, and then select **OK**.

After you complete this procedure, the next step is to activate four dataflows as described in the next section.

## Have your system administrator activate dataflows 

After you enable the resource recommendations feature, your system administrator must activate four [dataflows](/power-apps/maker/data-platform/create-and-use-dataflows). Ensure that this system administrator has "Global Admin" rights. This mandatory, one-time step must be completed for every new environment where the feature is enabled. The four dataflows prepare the data infrastructure that's required to generate optimal recommendations for any new project team member.

To activate the dataflows, have your system administrator follow these steps.

1. Sign in to your Project Operations environment as System Administrator.
1. Open a new tab in the same browser window, and sign in to the [Power Apps portal](https://make.powerapps.com) as System Administrator. For more information about the Power Apps portal, see [Sign in to Power Apps](/power-apps/maker/canvas-apps/sign-in-to-power-apps).
1. In the **Environments** section in the upper right, ensure that the environment that you're signed in to is selected.

    To view the environment name, go to your environment, select the profile symbol, and copy the environment name from the upper left of the dialog box that appears.

1. On the left navigation pane, select **Dataflows**. If this option isn't directly visible, select **More**, and then select **Dataflows**.
1. Select the **My Dataflows** tab. This tab should list the following dataflows (in addition to any pre-existing items):

    - **1. Resource Recommendation - Daily KPE**
    - **2. Resource Recommendation - Weekly Scoring Indexing**
    - **3. Resource Recommendation - Weekly Add Time Summary**
    - **4. Resource Recommendation - Weekly Update Time Summary**
1. If no Dataflows are visible under "My Dataflows" or "All Dataflows", refer to the next section.

> [!IMPORTANT]
> Every dataflow has a number as a prefix. The numbers indicate the order that the dataflows must be activated in. Make sure that they're activated **only in the specified order**.

## Handling missing Dataflows

If no Dataflows are visible under "My Dataflows" or "All Dataflows", this could be due to the ownership of the Dataflow being with a different global system administrator account. To confirm this, follow these steps:
1. On the left navigation pane, select **Solutions**.
2. Set the filter to **All** and look for the Display Name **Project Operations** (Name must be _ProjectService_). Select this solution.
3. The list of **Objects** will include **Dataflows**. Select this and you will see a list of all Dataflows (including the ones required for this feature).
4. Identify the _Owner_ for each Dataflow.
5. If this owner is not a _System User_, navigate back to **Home** and select **Dataflows** from the left navigation pane.
6. Go to **All Dataflows** and search for the name of the Owner identified in the previous step.
7. Select the owner from the list that appears, this should make all 4 dataflows visible.
8. Select the overflow symbol (three dots) for each Dataflow and select **Change Owner**. Select your own account as the new owner and confirm this.
9. Once you have completed these steps for all 4 dataflows, they will now be visible under **My Dataflows** and you can continue to activate each one of them.



## Activate a dataflow

1. Start with the first dataflow, **1. Resource Recommendation - Daily KPE**. Select the overflow symbol (three dots), and then select **Edit**. You're taken to a Power Query page that shows details of the selected dataflow.
1. Select the **EnvironmentName** parameter. Then, in the space that's provided for **Current Value**, replace the placeholder text (_\{\{envName\}\}_) with the URL of the environment that's being used, **without the "https://"** (for example, enter _recommend.crm.dynamics.com_).
1. In the **Queries** pane, select the first item after **EnvironmentName** and **Name**. This item must have a warning symbol (exclamation point) next to it. For the first dataflow, this item is **msdyn\_projecttask**.
1. You receive the following error message: "Credentials are required to connect to the CommonDataService source." Select **Configure Connection**.
1. If you're following these steps for the first time, a **Connect to data source** dialog box appears. In this dialog box, the **Connection** field is set to _Create a new connection_, the **Connection Source** field is set to the name of your environment, and the **Authentication Kind** field is set to _Organizational account_. (The following image shows an example.) Select **Sign in**, and enter your System Administrator user credentials again. Then, after sign-in is completed, select **Connect**. If you receive any error messages, select **Refresh** on the toolbar.

    :::image type="content" source="media/RRConfigureConnection.png" alt-text="Screenshot of the Connect to data source dialog box.":::

    If you aren't following these steps for the first time, no dialog box appears, and you can select **Connect** directly.

1. Select **Next**. The page that appears has a **Publish** button. This button might take up to two minutes to become available.

    :::image type="content" source="media/RRDataflowPublish.png" alt-text="Screenshot that shows the Publish button for the dataflow.":::

1. Select **Publish**. You're redirected back to the **Dataflows** page.
1. Repeat steps 1 through 7 for the remaining dataflows, in order of their numerical prefix.

## Complete the prerequisites

When every dataflow has a green check mark in its **Last refresh** column, all prerequisites are ready to use this feature. (The following image shows an example.)

:::image type="content" source="media/RRLastRefreshCompleteV2.png" alt-text="Screenshot of the Dataflows page where the last refresh is completed for every dataflow.":::

Depending on the number of projects and tasks in your environment, it might take **up to 24 hours** for all dataflows to complete their refresh.

If any dataflows fail to refresh, submit a support ticket to get help.

> [!NOTE]
> If the System Administrator user account that was used to activate the dataflows for the first time is deleted or deactivated, the preceding steps must be repeated by using new, active System Administrator credentials.

For more information about how to use the feature, see [Get recommendations for a project team member](./get-recommendations-for-project-team-members.md).
