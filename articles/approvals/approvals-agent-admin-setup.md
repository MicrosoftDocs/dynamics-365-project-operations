---
title: Set up the Approvals Agent as an admin (preview)
description: Learn how to set up the Approvals Agent as an admin. 
author: abriccetti
ms.author: abriccetti
ms.date: 07/15/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Set up the Approvals Agent as an admin (preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

The Approvals Agent is available as a production-ready preview in Microsoft Dynamics 365 Project Operations environments that have **version 4.140.0.239 or later**. An admin must complete the following steps to enable the approvals functionality of the Time and Expense Agent:

1. Set up connections on the Microsoft Power Apps home page.
1. Activate the agent trigger.

## Set up connections on the Power Apps home page

To set up connections on the Power Apps home page, follow these steps.

1. Sign in to [Power Apps](https://make.powerapps.com).
1. Use the environment switcher at the top of the page to select the environment where the agents were installed.
1. In the left pane, select **Solutions**.
1. Filter the **Solutions** page for **Managed** solutions, and select **Project Service Agent**.

To view a list of connection references, follow these steps.

1. In the **Objects** pane, select **Connection references**.
1. Select the checkboxes for the **Microsoft Copilot Studio** and **Microsoft Dataverse** connection references.
1. On the command bar, select **Advanced** \> **Add to solution**.
1. Select **Common Data Services Default Solution**.
1. Select **Save**.

    ![Screenshot that highlights the user interface elements used to add connections to the Project Service Agent solution as described in the preceding steps.](media/agentsetup2.png)

1. After the connections are added to the default solution, select **Back to solutions** in the left pane.
1. Filter the **Solutions** page for **Unmanaged** solutions, and select **Common Data Services Default Solution**.
1. In the **Objects** pane, select **Connection references**.
1. The **Microsoft Copilot Studio** and **Microsoft Dataverse** connection references should be listed. Select the checkbox for **Microsoft Copilot Studio**, and then select **Edit** on the command bar.
1. In the dialog that appears, in the **Connection** section, select **New connection**.

    ![Screenshot that highlights the user interface elements used to add a new connection as described in the preceding steps.](media/agentsetup4.png)

1. A new tab appears and shows a list of connections. In the search field in the upper right, enter **Copilot Studio**.
1. In the search results, select the **Create** button (**+**) to the right of **Microsoft Copilot Studio**.

    ![Screenshot that shows Copilot Studio entered in the search field on the new tab and Microsoft Copilot Studio in the search results.](media/agentsetup5.png)

1. In the dialog that appears, select **Create** to create a connection to Copilot Studio, and sign in as the user that you want the agent to run as.

    > [!NOTE]
    > The user who signs in for these connection will by fthe user the agent acts as. This must be a real user with an Entra ID account (sign in must happen via OAuth and not as a service principal). Additionally, the user that you sign in as must have the **Time and Approval Agent** security role, or another role that provides the same or greater privileges.

1. Return to the previous tab, and repeat the preceding steps for the **Microsoft Dataverse** connection reference to create a connection to Microsoft Dataverse.
1. Return to the **Connection references** page for the **Common Data Services Default Solution** solution.
1. In the dialog, in the **Connection** section, select the correct user.

    ![Screenshot that shows a user selected under Connection in the dialog.](media/agentsetup7.png)

## Activate the agent trigger

To activate the cloud flow that acts as the agent trigger, follow these steps.

1. Return to the **Project Service Agent** solution.
1. In the **Objects** pane, select **Cloud flows**.
1. In the row for **Approvals Agent trigger**, select the three vertical dots, and then, on the menu, select **Turn on**.

    ![Screenshot that highlights the user interface elements used to turn on the Approvals Agent trigger cloud flow as described in the preceding steps.](media/agentsetup8.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
