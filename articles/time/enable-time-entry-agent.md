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
- Publish the Agent to users in your organisation

Each step has been described in detail below.


## Create your organisation's Agent user 

While this step is **not mandatory**, it is recommended that a dedicated Agent user is created for the purpose of configuring and enabling Agents in an organisation. Alternatively, if your organisation already has a dedicated user with the **System Administrator** role assigned then you may skip this step and go directly to the next section: **Activate Power Automate Flows for your agent**.

To continue with creating a dedicated agent user, complete this process by navigating to [Power Platform Admin Portal](https://admin.powerplatform.microsoft.com/) and following steps documented in the [Dataverse User Creation Guide](https://learn.microsoft.com/en-us/power-platform/admin/create-users). 

After creating this new user, ensure that the user is provided with the following licenses (all are required):
- **Power Automate Free:** This is required to view and enable the set of Power Automate flows that the agent requires.
- **Microsoft Teams Enterprise**: The flows send alerts to team members using MS Teams.
- **Office 365 E5 license**: Primarily for Outlook calendar access.

### Assign agent user with the required role

A new "Time and Approvals Agent" role has been created to provide the agent user with the necessary rights to enable and publish the Time Entry Agent. To assign this role to your agent user, follow these steps:
1. Navigate to [Power Platform Admin Portal](https://admin.powerplatform.microsoft.com/) and select the desired environment from the environment picker on the top-right.
2. Within the **Access** tile, select *See all* under **Users**.
3. Select the agent user to which you want to assign this role.
4. Select **Manage roles** and select the *Time and Approval Agent* check box from the list. Click **Save**.

The agent user now has the necessary privileges to log in to view the Power Automate Flows that must be enabled in the next step of this process.

## Initiate Power Automate Flows

The Time Entry Agent has been given the ability to perform a series of actions (like creating time entries, sending team members alerts, etc). Each of these actions requires certain Power Automate Flows to be initiated and turned on to work smoothly. 
