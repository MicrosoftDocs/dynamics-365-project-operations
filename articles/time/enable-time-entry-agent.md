---
title: Enable the Time Entry Agent (Production Ready Preview)
description: This article explains how system administrators can enable the Time Entry Agent on one or more environments in their organisation.
author: mohitmenon
ms.date: 04/28/2025
ms.topic: how-to
ms.custom: 
  - bap-ai-copilot 
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Enable Time Entry Agent (Production Ready Preview) on an environment

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

The Time Entry Agent is available as a **Production Ready Preview** on Dynamics 365 Project Operations environments with **version 4.140.0.239 or higher**. This feature must first be enabled on Project Operations environments by system administrators, before being available for use by team members to log their time entries. The following steps must be completed to enable the feature:
- Create your organisation's Agent user (**optional**, but recommended step)
- Activate Power Automate Flows required by the agent (this gives the agent the ability to complete certain actions on behalf of team members)
- Enable the "Time and Expense Agent" feature flag 
- Publish the Agent from Microsoft Copilot Studio to users in your organisation

Each step has been described in detail below.


## Create your organisation's Agent user 

While this step is **not mandatory**, it is recommended that a dedicated Agent user is created for the purpose of configuring and enabling Agents in an organisation. Alternatively, if your organisation already has a dedicated user for similar purposes, with the **System Administrator** role assigned then you may skip this step and go to the next section: **Initiate Power Automate Flows for your agent**.

To continue with creating a dedicated agent user, complete this process by navigating to [Power Platform Admin Portal](https://admin.powerplatform.microsoft.com/) and following steps documented in the [Dataverse User Creation Guide](https://learn.microsoft.com/en-us/power-platform/admin/create-users). 

After creating this new user, ensure that the user is provided with the following licenses (all are required):
- **Power Automate Free:** This is required to view and enable the set of Power Automate flows that the agent requires.
- **Microsoft Teams Enterprise**: The flows send alerts to team members using MS Teams.
- **Office 365 E5 license**: Primarily for Outlook calendar access.

### Assign the agent user with a required role

A new "Time and Approvals Agent" role has been created to provide the agent user with the necessary rights to enable and publish the Time Entry Agent. To assign this role to your agent user, follow these steps:
1. Navigate to [Power Platform Admin Portal](https://admin.powerplatform.microsoft.com/) and select the desired environment from the environment picker on the top-right.
2. Within the **Access** tile, select *See all* under **Users**.
3. Select the agent user to which you want to assign this role.
4. Select **Manage roles** and select the *Time and Approval Agent* check box from the list. Click **Save**.

> [!IMPORTANT]
> The role assignment step is only necessary if a new agent user is being created to enable the Time Entry Agent. This step must be repeated for every new environment on which the Time Entry Agent is being enabled, even if the same user is being used across them. 
> The role assignment step is not required if an existing system administrator user is being used instead of a new agent user.

The agent user now has the necessary privileges to log in to view the Power Automate Flows that must be enabled in the next step of this process.

## Activate Power Automate Flows required by the agent

The Time Entry Agent has been given the ability to perform a series of actions (like creating time entries, sending team members alerts, etc). Each of these actions requires one or more Power Automate Flows to be initiated and turned on to work smoothly. To view and initiate these flows, follow these steps.

1. Sign in to [Power Automate](https://make.powerautomate.com) using the agent user or dedicated system administrator's credentials.
2. Select the desired environment from the picker.
3. Select **Solutions** from the menu on the left.
4. Click **Project Service Agent** to view more details about this solution.
5. You may either navigate to the **Cloud Flows** section of the menu or filter under **All** using the **Type** column where Type must contain the value _"Cloud Flow"_.

:::image type="content" source="../media/filterflows.png" alt-text="Screenshot that shows how to filter Cloud Flows from Solution page.":::

### Steps to be followed for each flow

There are **12** Power Automate flows (cloud flows) that must be **activated in this order** _(starting from number 1 to 12)_.
1. Create or Update User Configuration for Time Entry Copilot
2. Get Time Entries
3. Filter Duplicates
4. Import from Sources and Filter _(Parent of Flow 3)_
5. Import from Grid and Filter _(Parent of Flow 3)_
6. Send Summary and Daywise Adaptive Card
7. Create Time Entries and Notify _(Parent of Flow 6)_
8. Time Agent Periodic Import Child
9. Time Agent Periodic Import _(Parent of Flow 8)_
10. Generate External Comments
11. Send Missing Time Entries Alert
12. Generate External Comments and Send Missing Time Entries Alert _(Parent of Flow 11)_

Each flow has a similar sequence of steps that need to be completed, before moving to the next flow. These steps are:
1. Open the Power Automate Flow by selecting it and click **Edit**.
1. This will open a new tab with details of the Power Automate flow.
1. A flow may have one or more **Connection references** marked in red that may require authentication. To do so, switch to **Old Designer** using the toggle on the top-right, if the New Designer is selected by default. _(You may be shown a pop-up asking to save your flow before switching. You can select "Switch without saving" and continue)_ 
1. Select **Fix connection** and proceed to sign in with the agent user/assigned admin user credentials.
1. Once all connection references (if multiple) are authenticated (with a green tick), you may proceed to **Save** the flow.
:::image type="content" source="../media/3authenticatedconnectionreferenceexample.png" alt-text="Screenshot that shows all connection references in green or authenticated."::: 
:::image type="content" source="../media/4savedflowreadytogo.png" alt-text="Screenshot that shows that the flow has been saved.":::

1. After saving, use the arrow button to navigate back to the flow details. Finally, select **Turn ON** to activate the flow.
:::image type="content" source="../media/5turnonflow.png" alt-text="Screenshot that showing the turn on button for a flow.":::

1. Wait a few seconds after selecting this, until the "Turn off" option is visible. This implies that the flow has now been activated or turned on.
:::image type="content" source="../media/6turnoffvisible.png" alt-text="Screenshot showing the turn off button visible, implies that flow is ON.":::

1. Now close the current tab and switch back to the tab where the Cloud Flows within Project Service Agent solution were visible.
1. Continue the same process with the next flow, based on the order listed above.

> [!IMPORTANT]
> Please note that it is essential to activate all flows in the order shown above. Do not try to activate a later flow before the previous one(s) is or are turned ON.  

Once these steps have been completed for all 12 flows, the agent user or admin user may proceed to the next step of enabling the feature flag.

## Enable Time and Expense Agent feature 

To enable the feature, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations using a system administrator.
1. Ensure that you're using Project Operations version **__4.140.0.X__ or later**. 
1. On the left navigation, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. A list of organization units should appear. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, select the **Feature Control** drop-down.
1. Select **Enable Time and Expense Agent (Production Ready Preview)**, and then select **OK**. This feature can also be disabled at any time post enabling.

## Publish the agent from Microsoft Copilot Studio

Now that you've initiated all the Power Automate Flows and enabled the feature parameter, the last step for an administrator is to publish the agent to users in your organisation from Microsoft Copilot Studio.

> [!IMPORTANT]
> Before beginning this step, ensure that all flows are in the "ON" state at the end of these steps. If any one of the flows is still not "ON", this may lead to the Time Entry Agent not functioning as expected. If the "Create or Update User Configuration for Time Entry Copilot" flow is OFF, the agent cannot even be published.

To publish the agent, follow these steps.

1. Navigate to [Power Apps Maker Portal](https://make.powerapps.com) and select the desired environment from the environment picker on the top-right.
1. Select **Agents** from the menu on the left (If this option isn't visible, try **More**->**Agents**).
1. Under **All**, click **Time Entry Agent (Preview)**. This will open a new tab for this agent on Microsoft Copilot Studio.
1. You may see a **Consent confirmation** message on the right, under _Test your agent_ section. Hit **Confirm** here.
1. Click **Publish** to publish this agent bot first. A pop-up window may appear to inform you of some "potential risks", view them and select **Publish**. 
:::image type="content" source="../media/publishingagent.png" alt-text="Screenshot showing agent publish is in progress.":::

### Make Teams app available to users
1. Once publishing is complete, navigate to the **Channels** tab of the agent. Select **Teams + Microsoft 365**.
1. A pop-up window appears, where you may **uncheck** "Make agent available in Microsoft 365 Copilot Chat" and then select **Add channel**.
1. A confirmation message that says _"The channel was added"_ should show on top of the screen.
1. Now, to make this agent available to end users (team members) as a Teams app - select **Availability Options**. Under "Show in the store", you can select **Show to everyone in my org** to make this available across a broader audience.
1. If the system administrator user being used so far is not a **Global Administrator** then they must select **Submit for admin approval**. A Global Administrator's approval will be required to share the agent as a Teams app to users in this organisation.

### Get approval from Global Administrator
- Log in with global administrator credentials to [Teams Admin Center](https://admin.teams.microsoft.com).
- Navigate to **Teams apps** -> **Manage apps**
- Search for "Time Entry Agent" under **All apps** section. This will show up as having **Blocked** status.
- Select **Publish**. 
- Next, navigate to **Teams apps** -> **Setup policies**.
- Select **Global (org-wide default)** and click **Add apps**.
- Search for "Time Entry Agent (Preview)" and add this app, then click **Save**.

> [!IMPORTANT]
> The admin approval step for your Teams app may take **up to 12 hours** in some cases. So it is recommended to wait at least that long before notifying team members that they can access the agent through Teams.

Once all the steps covered in this page have been completed successfully, team members in your organisation will able to view and use the Time Entry Agent in the form of a Teams app. Refer to the [next section](use-time-entry-agent-in-teams.md) for how team members can start using the agent.

 [!INCLUDE[footer-include](../includes/footer-banner.md)]



