---
title: Expense Agent (Preview) deployment using Dynamics 365 Agent Deployment tool
description: Learn about setting up Expense Agent using the D365 Agent Deployment tool
author: ajitchandran
ms.author: ajitchandran
ms.date: 01/16/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak 

---

# Expense Agent (Preview) deployment using Dynamics 365 Agent Deployment tool

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies to Dynamics 365 Project Operations Integrated with ERP and Dynamics 365 Project Operations for manufacturing**_

> [!NOTE]
> Community interest groups have now moved from Yammer to Microsoft Viva Engage. To join the Expense Management Viva Engage community and take part in the latest discussions, click [**here**](https://engage.cloud.microsoft/main/org/microsoft.com/groups/eyJfdHlwZSI6Ikdyb3VwIiwiaWQiOiIyMzc5MzM4OTU2ODAifQ) and request for access.

> [!IMPORTANT]
>
> - This feature is a production-ready preview.
> - Production-ready previews are subject to [supplemental terms of use](https://go.microsoft.com/fwlink/?linkid=2189520).

This document walks you through the intuitive wizard experience designed to streamline setup, providing all pre-requisites, detailed instructions, and direct links to relevant settings in one centralized location.

> [!NOTE]
> To run the agent deployment wizard, go to the [Dynamics 365 Agent Deployment tool](https://aka.ms/InstallD365Agents) in Power Platform admin center.
> This tool is continuously evolving, with ongoing automation of additional steps to reduce manual effort. This document will be updated with the latest enhancements, making it your single source for all Expense Agent setup-related guidance.

Administrators can now complete the entire process without navigating between platforms—everything you need is consolidated here for efficiency and simplicity.

It is recommended to go through the pre-requisites before running the wizard. You will find more details [Agent Deployment tool](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/copilot/agent-deployment)

##Steps to setup Expense Agent
Note: All screens shown are for indicative purposes and might differ from actual screens due to updated features or options.

1. Login to [Power Platform Admin Center](https://admin.powerplatform.com) using an **Admin User**(Recommended) or 
1. Navigate to **Copilot** > **Dynamics 365**, where you'll see all available agents. Alternatively, go to [Agent Deployment Tool](https://aka.ms/InstallD365Agents)
1. Click **Select Environment** and choose the target environment for Expense Agent setup.
1. Click the **Add** button next to Expense Agent to launch the wizard.

   :::image type="content" source="media/Agent Deployment tool in PPAC.png" alt-text="Screenshot of the Agent deployment tool in PPAC":::

1. On the overview page, review the high-level steps required to set up the Expense Agent (optional but recommended). Then click **Next**.
1. Check all pre-requisites before proceeding. Ensuring they are met will help have a smooth setup experience.<br>
   - **Finance and operations environment:** You need at least version 10.0.44 (10.0.2263.167 and later) or 10.0.45 (10.0.2345.102 and later) or 10.0.46 (10.0.2428.69) of the finance and operations environment to install the agent.<br>
   - Enable Copilot in Power Platform admin center.<br>
   - Enable Copilot Studio message consumption and billing: The link would take you to the PPAC where consumption and billing can be set.<br>
   - Refresh virtual entities (optional but recommended for Expense Agent). Though optional, refreshing virtual entities before the next steps is highly recommended. Expect this to take around 10 minutes. If you see a "completed with errors" message, retry by clicking **Refresh** until you get "Refresh completed successfully."<br>
1. On click of **Next**, select the **Expense Agent user ID** that is already created
1. [Assign the needed licenses, roles to the Expense Agent](https://learn.microsoft.com/en-us/dynamics365/project-operations/expense/expense-agent-setup#step-3-create-an-expense-agent-user-for-agent-execution) and click **Next**
1. Create connections and activate flows: Click the + button beside each connection, select Create, pick the Expense Agent user account, and allow access. Repeat for all connections.
   > [!NOTE] Create connections using the **Expense Agent user only.**

   :::image type="content" source="media/Connect the agent.png" alt-text="Screenshot of the step to create connections and activate flows":::

1. Once done, click **Add connections** to the agent.

   :::image type="content" source="media/Adding Connections.png" alt-text="Screenshot of successfully adding connections to the agent":::
   
1. The next step is to activate flows—click **Activate flows.** If there are any errors while activating the flows, retry by clicking **Activate flows**

   :::image type="content" source="media/Flows Activated.png" alt-text="Screenshot of successfully activating flows to the agent":::
   
1. Click **Next** once all flows are activated
1.	The last step is to update the environment variables.<br>
    - Enter the folder path from the shared mailbox (Enter Inbox if none created) and, <br>
    - The shared mailbox email address. Refer to the [parameter table](https://learn.microsoft.com/en-us/dynamics365/project-operations/expense/expense-agent-setup#information-you-need-to-create-the-installation-file) for details.
	
     :::image type="content" source="media/Update environment variables.png" alt-text="Screenshot of updating the environment variable for the agent":::
   
1. Click on **Update environment details** to save and then Next to complete the setup of the Expense Agent.
   
   :::image type="content" source="media/Setup completed.png" alt-text="Screenshot of successful deployment of expense agent":::
   
## Related Information

- [Expense Agent overview](/dynamics365/project-operations/expense/expense-agent-setup)
- Expense Agent Configuration
- [Installation and Setup of the Expense Agent](/dynamics365/project-operations/expense/expense-agent-setup)
- [Expense Agent FAQs](/dynamics365/project-operations/expense/expense-agent-faq)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
