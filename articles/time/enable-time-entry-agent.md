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

# Enable Time Entry Agent for a Project Operations environment

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

The Time Entry Agent is now available as a **Production Ready Preview** for Dynamics 365 Project Operations customers. This feature can be enabled on Project Operations environments by system administrators by completing the following setup instructions:
- Create your organisation's Agent user (optional, but recommended step)
- Initiate Power Automate Flows in sequence (this gives the agent the ability to complete certain actions on behalf of team members)
- Publish the Agent to users in your organisation
- Enable the feature flag 


## Create your organisation's Agent user

While this step is not mandatory, it is recommended that a dedicated Agent user is created for the purpose of configuring and enabling Agents in an organisation. This can be done from the [Power Platform Admin Portal](https://admin.powerplatform.microsoft.com/) by following the [Dataverse User Creation Guide](https://learn.microsoft.com/en-us/power-platform/admin/create-users).
After creating this new user, ensure that the user is provided with the following licenses:
- **Power Automate Free:** This is required to view and enable the set of Power Automate flows that the agent requires.
- **Microsoft Teams Enterprise**: The flows send alerts to team members using MS Teams.
- **Office 365 E5 license**: Primarily for Outlook calendar access.

