---
title: Use Copilot in time entry
description: This article explains how team members can use Copilot in time entry to complete their time entry each week.
author: mohitmenon
ms.date: 04/24/2024
ms.topic: how-to
ms.custom: 
  - bap-ai-copilot 
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Use Copilot in time entry

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

Copilot in time entry is designed to simplify the time entry experience and make it less time consuming by significantly reducing the number of pages that project team members must open. The time that the feature helps save can instead be used for high-leverage tasks.

The Copilot in time entry feature currently has two primary capabilities:

- Log time.
- Generate external comments.

## Availability of Copilot in time entry feature

- Copilot in time entry is available as a preview feature for **environments hosted in United States**, having a Project Operations version starting from _4.103.0.x_ (feature is not available before this version) and up to _4.108.X.X_.
- The feature will be **ON by default in all regions** from Project Operations version _4.120.X.X_ onwards.

Contact your tenant administrator to confirm that your environment meets these requirements. 

## Enable or disable the Copilot in time entry feature

To enable Copilot in time entry, follow these steps.

1. Ensure that you meet the availability criteria to use this feature (see previous section).
1. Sign in to Dynamics 365 Project Operations.
1. On the left navigation, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. A list of organization units should appear. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Copilot in time entry**, and then select **OK**.
2. If instead you see the text **Disable Copilot in time entry**, this implies that the feature is already enabled.

> [!NOTE]
> To disable Copilot in time entry, follow the same steps, but select **Disable Copilot in time entry** in step 7.

## Interactive Copilot chat experience

You can access both Copilot capabilities of this feature only by using the interactive Copilot chat experience. Because the Copilot chat experience is currently in preview, it might not be enabled on your environment.

- On the top menu bar, select the Copilot icon next to the user icon to expand the Copilot sidecar. The following message is shown: "Get started with Copilot by typing your request in chat."
- To collapse the sidecar, select the Copilot icon again.

> [!NOTE]
> If the Copilot icon isn't visible, work with your system administrator to [enable Copilot chat for your environment](/power-apps/maker/model-driven-apps/add-ai-copilot#enable-copilot-for-model-driven-apps-feature-for-your-environment).

## Log time by using Copilot

Based on a user's existing project task assignments for the current week, this capability suggests draft time entries that can be created. If the user has preexisting time entries in that week, Copilot ensures that they aren't duplicated.

Follow these steps to log time by using Copilot.

1. Open the **Time Entries** page.
1. Begin a chat conversation by selecting the Copilot icon to expand the Copilot sidecar.
1. In the chat window, enter _Log my time_ or _Create time entries_. Then select the **Enter** key.

    Copilot responds, "Working on it," and begins to scan your project assignments. It then responds with the suggested time entries for the current week. (It first removes any duplicate entries.) [Learn more about how to create resource assignments.](../project-management/create-assignments.md)

1. Expand the section for each project to review the suggested time entries. To create time entries, select **Create entries**.

    Copilot responds with a confirmation that time entries are being created. It also prompts you to refresh the time entry grid to view the latest changes.

1. Refresh the time entry grid.
1. You can now make any necessary modifications to the draft time entries before you submit them for approval.

> [!NOTE]
> Copilot suggests time entries only for the current week, not for earlier weeks. We recommend that you use Copilot to finish logging time entries before the end of the week.
>
> The time entry grid isn't automatically refreshed after Copilot creates new time entries. To view any updates, you must manually refresh the grid.

## Generate external comments by using Copilot

External (customer-facing) comments are often crucial details that are added to individual time entries. Some users might even be unable to submit time entries for approval until they add these comments.

In the current process for creating and modifying external comments, users must open a new page for each time entry. Therefore, the process is very time consuming and can lead to inaccuracies in the submitted comments.

Copilot helps simplify this process in two ways:

- It generates external comments by using details such as the **Project**, **Project Task**, **Role**, and **Duration** values of a time entry. (The generated comments are kept under 100 characters.)
- It provides an effective interface where users can view and modify all comments together, without having to open a separate page for each entry.

Follow these steps to generate external comments by using Copilot.

1. Open the **Time Entries** page.
1. Begin a chat conversation by selecting the Copilot icon to expand the Copilot sidecar.
1. In the chat window, enter _Generate comments_ or _Add external comments_. Then select the **Enter** key.

    Copilot first responds, "Working on it," and begins to use details such as the **Project**, **Project Task**, **Role**, and **Duration** values of each time entry to generate a generic first draft of the external comments. It then responds with the generated external comments for each time entry. Each generated comment is shown as an editable text box and can immediately be modified.

1. Review the generated comments, and make any necessary modifications to them. When you finish, select **Save all**.

    Copilot responds with a confirmation that comments are being saved for all time entries.
    
1. Refresh the time entry grid to view the latest changes.

To view previously saved external comments, enter _View comments_ in the chat window. Copilot shows all previously saved comments. Notice that there's no Copilot icon for them. You can review, modify, and then save these comments in a similar way.

> [!NOTE]
> Copilot doesn't generate or overwrite any preexisting external comments that are linked to a time entry. Those comments are still shown, but the absence of a Copilot icon indicates that Copilot didn't generate them.

## More resources

- [Copilot in time entry responsible AI FAQ](../responsible-ai/copilot-in-time-entry-faqs.md)

> [!IMPORTANT]
Depending on where your environment is hosted, you might have to allow data movement across regions to use copilots and generative AI features. If your environment is hosted in a region that requires data movement across regions to use copilots and generative AI features, your tenant administrator must consent to the terms of use and select the **Move data across regions** checkbox in the Power Platform admin center. [Learn more about how data movement across regions works.](/power-platform/admin/geographical-availability-copilot#enable-data-movement-across-regions)
