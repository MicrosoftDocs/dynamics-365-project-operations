---
title: Expense Agent deployment using Dynamics 365 Agent Deployment tool (Preview)
description: Learn about setting up Expense Agent using the Dynamics 365 Agent Deployment tool
author: ajitchandran
ms.author: ajitchandran
ms.date: 01/27/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak 

---

# Deploy Expense Agent using Dynamics 365 Agent Deployment tool (Preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies to Dynamics 365 Project Operations Integrated with ERP and Dynamics 365 Project Operations for manufacturing**_

> [!NOTE]
> Community interest groups have now moved from Yammer to Microsoft Viva Engage. To join the Expense Management Viva Engage community and take part in the latest discussions, go to the [Expense Management (Web, Mobile & Expense Agent) community](https://engage.cloud.microsoft/main/org/microsoft.com/groups/eyJfdHlwZSI6Ikdyb3VwIiwiaWQiOiIyMzc5MzM4OTU2ODAifQ) and select **Join**.

This document provides an intuitive wizard experience designed to streamline setup. It provides all prerequisites, detailed instructions, and direct links to relevant settings in one centralized location.

> [!NOTE]
> To run the agent deployment wizard, go to the [Dynamics 365 Agent Deployment tool](https://aka.ms/InstallD365Agents) in Power Platform admin center.
>
> This tool is continuously evolving, with ongoing automation of other steps to reduce manual effort. This document is updated with the latest enhancements, making it your single source for all Expense Agent setup-related guidance.

Administrators can now complete the entire process without navigating between platforms. For efficiency and simplicity, everything you need is consolidated here.

Review the prerequisites before running the wizard. Learn more about the prerequisites in [Agent Deployment tool](/dynamics365/fin-ops-core/dev-itpro/copilot/agent-deployment).

## Set up Expense Agent

> [!NOTE]
> All screens shown are for indicative purposes and might differ from actual screens due to updated features or options.

To set up Expense Agent, follow these steps:

1. Sign in to [Power Platform admin center](https://admin.powerplatform.com) by using an **Admin User** (recommended).
1. Go to **Copilot** > **Dynamics 365** to see all available agents. Alternatively, go to [Agent Deployment Tool](https://aka.ms/InstallD365Agents).
1. Select **Select Environment** and choose the target environment for Expense Agent setup.
1. Select **Add** next to Expense Agent to launch the wizard.

   :::image type="content" source="media/agent-deployment-tool.png" alt-text="Screenshot of the Agent deployment tool in Power Platform admin center.":::

1. On the overview page, review the high-level steps required to set up the Expense Agent (optional but recommended). Then select **Next**.
1. Check all prerequisites before proceeding. Ensuring they're met helps you have a smooth setup experience.

   - **Finance and operations environment:** You need at least version 10.0.44 (10.0.2263.175 and later), 10.0.45 (10.0.2345.115 and later), or 10.0.46 (10.0.2428.69) of the finance and operations environment to install the agent.
   - Install Copilot for Finance and Operations app and should be 1.0.3231.4 or later. [Click here](https://review.learn.microsoft.com/en-us/dynamics365/project-operations/expense/expense-agent-setup?branch=main#step-1-install-copilot-for-finance-and-operations-apps) to know more on steps to install the app 
   - Enable Copilot in Power Platform admin center.
   - Enable Copilot Studio message consumption and billing: The link takes you to the Power Platform admin center where you can set consumption and billing.
   - Refresh virtual entities (optional but recommended for Expense Agent). Though optional, refreshing virtual entity before the next steps is highly recommended. Expect this step to take around 10 minutes. If you see a "completed with errors" message, retry by selecting **Refresh** until you get "Refresh completed successfully."

1. Select **Next**, and then select the **Expense Agent user ID** that you already created.
1. [Assign the needed licenses and roles to the Expense Agent](/dynamics365/project-operations/expense/expense-agent-setup#step-3-create-an-expense-agent-user-for-agent-execution) and select **Next**.
1. Create connections and activate flows: Select the + button beside each connection, select **Create**, pick the Expense Agent user account, and allow access. Repeat for all connections.

   > [!NOTE]
   > Create connections by using the **Expense Agent user only.**

   :::image type="content" source="media/connect-the-agent.png" alt-text="Screenshot of the step to create connections and activate flows.":::

1. When done, select **Add connections** to the agent.

   :::image type="content" source="media/adding-connections.png" alt-text="Screenshot of successfully adding connections to the agent.":::

1. The next step is to activate flows - select **Activate flows.** If there are any errors while activating the flows, retry by selecting **Activate flows**.

   :::image type="content" source="media/flows-activated.png" alt-text="Screenshot of successfully activating flows to the agent.":::

1. Select **Next** once all flows are activated.
1. The last step is to update the environment variables.

   - Enter the folder path from the shared mailbox (enter Inbox if none created).
   - Enter the shared mailbox email address. Refer to the [parameter table](/dynamics365/project-operations/expense/expense-agent-setup#information-you-need-to-create-the-installation-file) for details.

     :::image type="content" source="media/update-environment-variables.png" alt-text="Screenshot of updating the environment variable for the agent.":::

1. Select **Update environment details** to save and then **Next** to complete the setup of the Expense Agent.

   :::image type="content" source="media/setup-completed.png" alt-text="Screenshot of successful deployment of expense agent.":::

## Related information

- [Expense Agent overview](/dynamics365/project-operations/expense/expense-agent-setup)
- Expense Agent Configuration
- [Installation and Setup of the Expense Agent](/dynamics365/project-operations/expense/expense-agent-setup)
- [Expense Agent FAQs](/dynamics365/project-operations/expense/expense-agent-faq)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
