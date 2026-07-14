---
title: Set up the Approvals Agent using the agent deployment wizard (preview)
description: Learn how to set up the Approvals Agent using the agent deployment wizard.
author: abriccetti
ms.author: abriccetti
ms.date: 05/21/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Set up the Approvals Agent by using the agent deployment wizard (preview)

[!INCLUDE [banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

This article explains how to set up the Approvals Agent by using the agent deployment wizard. To manually configure the agent, see [Set up the Approvals Agent as an admin](approvals-agent-admin-setup.md).

> [!NOTE]
> The agent deployment wizard is continuously evolving, with ongoing automation of other steps to reduce manual effort. This document is updated with the latest enhancements, making it your single source for all Approvals Agent setup-related guidance.

The agent deployment wizard consolidates everything Administrators need to complete the setup process without navigating between platforms.

Review the prerequisites before running the wizard. Learn more about the prerequisites in [Agent Deployment tool](/dynamics365/fin-ops-core/dev-itpro/copilot/agent-deployment).

## Set up the Approvals Agent

To set up the Approvals Agent, follow these steps:

1. Sign in to [Power Platform admin center](https://admin.powerplatform.com) by using an **Admin User** (recommended).
1. Go to **Copilot** > **Dynamics 365** to see all available agents. Alternatively, go to [Agent Deployment Tool](https://aka.ms/InstallD365Agents).
1. Select **Select Environment** and choose the target environment for Approvals Agent setup.
1. Select **Add** next to Approvals Agent to launch the wizard.
1. On the overview page, review the high-level steps required to set up the Approvals Agent (optional but recommended), and then select **Next**.
1. Ensure you meet all prerequisites before proceeding, and then select **Next**.
1. Enter the user ID for the user you want to act as the agent. Ensure that the selected user has the required roles and licenses and select **Next**.
1. To set up the required connection references, select the plus (+) button next to each connection, select **Create**, select the same user account from the previous step, and allow access. Repeat for both connections.
1. The selected user appears in the drop-down menus for each connection. Select that user for each.
1. To activate the approvals agent trigger flow, select **Activate flows**, and then select **Next**.
1. Select the link to **Microsoft Copilot Studio: Agents**. In **My Agents**, find and open the Approvals Agent, and ensure that it's published. Then select **Complete** in Copilot Studio. Return to the agent deployment tool and select **Next**.

Learn more about configuring the Approvals Agent in the [Approvals Agent overview](approvals-agent-intro.md) article.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
