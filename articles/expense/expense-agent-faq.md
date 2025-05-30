---
title: Expense Entry feature of the Time and Expense Agent FAQ (preview)
description: Get answers to frequently asked questions about the Expense Entry feature of the Time and Expense Agent.
author: alexeiantao
ms.date: 05/13/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: alexeiantao
---

# Expense Entry feature of the Time and Expense Agent FAQ (preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

This article provides answers to frequently asked questions about the Expense Entry feature of the Time and Expense Agent. It also describes known issues that affect the agent and explains how to work around them.

## Agent enablement and configuration

### How do I enable/disable the agent?

To enable/disable the agent, go to the configuration page in Expense Management parameters.

### Can I enable/disable the agent for selected legal entities and provide custom configurations?

Yes, the agent can be enabled/disabled for selected legal entities. Configurations are unique to each legal entity.

### Why doesn't the Expense Entry feature of the Time and Expense Agent appear in Expense Management parameters in finance and operations apps?

The Expense Entry feature of the Time and Expense Agent is available as of version 10.0.44 of finance and operations apps. Enable the **Agent Management** feature in the **Feature Management** workspace (**Workspaces** \> **Feature Management**).

### Why isn't the Expense Entry solution shown?

The solution is part of the **Copilot for finance and operations** package (version 1.0.3033.5 or later). Update it from the Microsoft Power Platform admin center. Learn more in the Copilot documentation.

## Setup and configuration

### How do I update the shared mailbox address ID for expense usage?

Sign in to [Power Apps](https://make.powerapps.com/), update the variable in **DefaultSolution**, and then publish all customizations.

### How do I update environment variables?

Sign in to [Power Apps](https://make.powerapps.com/), go to **DefaultSolution**, and update the following values:

- Expense agent Shared Mailbox ID
- Finance and operations Instance Url
- Expense agent Shared Mailbox Address ID

### I don't know which connectors are used for the Expense Entry feature of the Time and Expense Agent. How do I add them?

The Expense Entry feature of the Time and Expense Agent uses the following connectors:

- Microsoft Copilot Studio
- Dataverse
- Office 365 Users
- Office 365 Outlook
- Microsoft Teams

To add a connector, sign in to [Power Apps](https://make.powerapps.com/), select your environment, go to **Connections** \> **New connection**, and then select the connector.

### What should I do if Microsoft Purview Data Loss Prevention policy blocks connector access?

Ensure that the connectors are in the **Business** group and the allow list.

## Agent execution

### What should I do if the Expense Entry feature of the Time and Expense Agent isn't processing my email receipts?

Ensure that you're part of the correct legal entity and have active employment. In addition, verify that the agent is enabled for the legal entity.

### I followed the setup steps and have the required permissions, but emails still aren't processed. What should I do?

You might have to republish agents.

1. Sign in to [Power Apps](https://make.powerapps.com/).
1. Select **Environment** \> **Agents**, and then select **Expense Entry feature of the Time and Expense Agent** and **ExpenseAgent-Line**.
1. Publish both agents.
1. Publish the **Time and Expense Agent** solution.

### What should I do if Power Automate flows stop working?

Flows might be in a disabled state because of repeated failures. In this case, turn them on manually. If any connections require reauthentication, reconnect them.

### Flows are running, but expenses aren't processed. What should I do?

Here are some possible causes:

- The Expense Entry feature of the Time and Expense Agent isn't enabled for the legal entity.
- Users don't have employment in the legal entity.
- Connectors are disconnected.
- The Copilot Studio license is missing.

### I updated the Outlook folder, but the agent still uses the old folder. What should I do?

Reconnect the **Office 365 Outlook** connector, and republish the solution.

## Email and receipt processing

### What file formats and sizes does the agent support?

The agent supports JPEG, PNG, and PDF files. The recommended file size is less than 2 megabytes (MB). Larger file sizes are supported only for JPEG and PDF files.

### Does the agent support multiple receipts in one email?

Yes.

### Can the agent read receipts that are embedded in the email body?

No.

### I have active employment and connections, but my receipt isn't being processed. What should I do?

Ensure that the receipt format and size are correct. The supported file types are JPEG, PNG, and PDF. The recommended file size is less than 2 MB.

### How do I determine whether an expense was created by the agent?

Add the **Expense Generated by** column on the web app's **Expense Reports** page.

### What should I do if I can't view the expense line for a forwarded receipt in the web app?

Processing can take 1–24 hours. Lines appear on reports, not in unattached expenses.

### How do I determine whether my receipt was processed?

Processed receipts are grouped into reports in the web app and shown in Teams. Errors trigger a fallback card that provides information about the failure.

### What should I do if I can't detach an expense line from a one-line adaptive card report?

The agent doesn't allow detachment of the only line on a one-line report. Use the web app to delete the report.

## Microsoft Teams integration

### What should I do if the adaptive card for Expense isn't shown in Teams?

Ensure that the **Expense Entry feature of the Time and Expense Agent** Teams app is installed.

### I get no response when I select the adaptive card button. What should I do?

There is a one-day timeout. You can act on the next card or use the web app.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
