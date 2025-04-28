---
title: Enable the Time Entry Agent 
description: This article explains how system administrators can enable the Time Entry Agent on one or more environments in their organisation.
author: mohitmenon
ms.date: 04/28/2025
ms.topic: how-to
ms.custom: 
  - bap-ai-copilot 
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Enable Time Entry Agent on an environment

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

The Time Entry Agent is available as a **Production Ready Preview** on Dynamics 365 Project Operations environments with **version 4.140.0.239 or higher**. This feature must first be enabled on Project Operations environments by system administrators, before being available for use by team members to log their time entries. The following steps must be completed to enable the feature:
- Create your organisation's Agent user (**optional**, but recommended step)
- Initiate Power Automate Flows in sequence (this gives the agent the ability to complete certain actions on behalf of team members)
- Enable the "Time and Expense Agent" feature flag 
- Publish the Agent from Microsoft Copilot Studio to users in your organisation

Each step has been described in detail below.


## Create your organisation's Agent user 

While this step is **not mandatory**, it is recommended that a dedicated Agent user is created for the purpose of configuring and enabling Agents in an organisation. Alternatively, if your organisation already has a dedicated user for similar purposes, with the **System Administrator** role assigned then you may skip this step and go directly to the next section: [**Initiate Power Automate Flows for your agent**](enable-time-entry-agent.md#initiate-power-automate-flows).

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
> The role assignment step is only necessary if a new agent user is being created to enable the Time Entry Agent. This step must be repeated for every new environment on which the Time Entry Agent is being enabled, even if the same user is being used across them. The role assignment step is not required if an existing system administrator user is being used instead of a new agent user.

The agent user now has the necessary privileges to log in to view the Power Automate Flows that must be enabled in the next step of this process.

## Initiate Power Automate Flows

The Time Entry Agent has been given the ability to perform a series of actions (like creating time entries, sending team members alerts, etc). Each of these actions requires one or more Power Automate Flows to be initiated and turned on to work smoothly. To view and initiate these flows, follow these steps.

1. Navigate to [Power Automate](https://make.powerautomate.com) and select the desired environment from the picker.
2. Select **Solutions** from the menu on the left.
3. Click **Project Service Agent** to view more details about this solution.
4. You may either navigate to the **Cloud Flows** section of the menu or filter under **All** using the **Type** column where Type must contain the value _"Cloud Flow"_.

:::image type="content" source="../media/filterflows.png" alt-text="Screenshot that shows how to filter Cloud Flows from Solution page.":::

### Steps to be followed for each flow

There are **12** Power Automate flows (cloud flows) that must be initiated in this order (starting from number 1 to 12).
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
- Open the Power Automate Flow by selecting it and click **Edit**.
- This will open a new tab with details of the Power Automate flow.
- Switch to **Old Designer** if the New Designer is selected by default. _(You may be shown a pop-up asking to save your flow before switching. You can select "Switch without saving" and continue)_
- A flow may have one or more **Connection references** that may require authentication using credentials. To do so, select **Fix connection** and proceed to sign in with the agent user/assigned admin user credentials.
- Once all connection references (if multiple) are authenticated (with a green tick), you may proceed to **Save** the flow.
- After saving, use the arrow button to navigate back to the flow details. Finally, select **Turn ON** to activate the flow.
- Wait a few seconds after selecting this, until the "Turn off" option is visible. This implies that the flow has now been activated or turned on.
- Now close the current tab and switch back to the tab where the Cloud Flows within Project Service Agent solution were visible.
- Continue the same process with the next flow, based on the order listed above.


