---
title: Set up the Approvals Agent using the Dynamics 365 Agent Deployment Tool (preview)
description: Learn how to set up the Approvals Agent as an admin using the Dynamics 365 Agent Deployment Tool.
author: abriccetti
ms.author: abriccetti
ms.date: 05/20/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Set up the Approvals Agent using the Dynamics 365 Agent Deployment Tool (preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

This document provides an intuitive wizard experience designed to streamline setup. It provides all prerequisites, detailed instructions, and direct links to relevant settings in one centralized location. To instead manually configure the agent, refer to [Set up the Approvals Agent as an admin](approvals-agent-admin-setup.md)

> [!NOTE]
> To run the agent deployment wizard, go to the [Dynamics 365 Agent Deployment tool](https://aka.ms/InstallD365Agents) in Power Platform admin center.
>
> This tool is continuously evolving, with ongoing automation of other steps to reduce manual effort. This document is updated with the latest enhancements, making it your single source for all Approvals Agent setup-related guidance.

Administrators can now complete the entire process without navigating between platforms. For efficiency and simplicity, everything you need is consolidated here.

Review the prerequisites before running the wizard. Learn more about the prerequisites in [Agent Deployment tool](/dynamics365/fin-ops-core/dev-itpro/copilot/agent-deployment).

## Set up the Approvals Agent

To set up the approvals agent, follow these steps:

1. Sign in to [Power Platform admin center](https://admin.powerplatform.com) by using an **Admin User** (recommended).
1. Go to **Copilot** > **Dynamics 365** to see all available agents. Alternatively, go to [Agent Deployment Tool](https://aka.ms/InstallD365Agents).
1. Select **Select Environment** and choose the target environment for Approvals Agent setup.
1. Select **Add** next to Approvals Agent to launch the wizard.
1. On the overview page, review the high-level steps required to set up the Approvals Agent (optional but recommended). Then select **Next**.
1. Check all prerequisites before proceeding. Ensuring they're met helps you have a smooth setup experience. Then select **Next**.
1. On this page, enter the user ID for the user you want to act as the agent. Then ensure that the selected user has the required roles and licenses and select **Next**.
1. To set up the required connection references, select the + button beside each connection, select Create, pick the same user account from the previous step, and allow access. Repeat for both connections.
1. The selected user should now appear in the drop down menus for each connection. Select that user for each.
1. The **Activate flows** button should now be enabled. Select this button to activate the approvals agent trigger flow, and select **Next**.
1. Here select the link to *Microsoft Copilot Studio: Agents*, find the Approvals agent from the *My Agents* list, open it and ensure that it is published. Then select **Complete** and **Next** back at the agent deployment tool.

This completes the admin setup of the approvals agent. To configure the agent, refer to [Approvals Agent Overview](approvals-agent-intro.md).
