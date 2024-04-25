---
title: Use Copilot in time entry (preview)
description: This article explains how team members can use Copilot in time entry to complete their time entry each week.
author: mohitmenon
ms.date: 04/24/2024
ms.topic: how-to
ms.custom: 
  - bap-ai-copilot 
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Use Copilot in time entry (preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Copilot in time entry is designed to simplify the time entry experience by taking away the drudgery of navigating endless forms, that currently make this process so time consuming. This feature gives back time to project team members that they can instead use for high leverage tasks.

This Copilot in time entry feature currently has two primary capabilities:

- Log my time.
- Generate external comments.

## Enable or disable the Copilot in time entry feature

This feature is currently in preview and **can only be accessed on environments hosted in the "NAM" Azure region**. Confirm with your tenant admin before trying to access this feature.

To enable Copilot in time entry, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Ensure that you're using Project Operations version _4.103.0.X_ or later. This feature isn't available before this version.
1. On the left navigation, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. A list of organization units should appear. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Copilot in time entry** and then select **OK**.

   > [!NOTE]
   > To disable Copilot in time entry, follow the enable steps and select **Disable Copilot in time entry** in step 7.

## Interactive Copilot chat experience

Both of the Copilot capabilities in this feature can only be accessed by using the interactive Copilot chat experience. Since this Copilot chat experience is currently in preview, it may not be enabled on your environment.

- Select the Copilot icon from the top menu bar, next to the user icon.
- This step makes the Copilot sidecar visible along with a message stating _"Get started with Copilot by typing your request in chat"_.
- To collapse this sidecar, similarly select the Copilot icon once again.

   > [!NOTE]
   > Please work with your system administrator and complete steps to [enable Copilot chat for your environment](/power-apps/maker/model-driven-apps/add-ai-copilot#enable-copilot-for-model-driven-apps-feature-for-your-environment) if the Copilot icon isn't visible.

## Log time using Copilot

This capability takes a user's existing project task assignments for the current week and suggests draft time entries that can be created based on those assignments. Copilot ensures there isn't duplication of entries when the user has pre-existing time entries in that week.

Follow these steps to log time using Copilot:

1. Navigate to the **Time Entries** page.
1. Begin a chat conversation by activating the Copilot sidecar (select the Copilot icon).
1. Type _Log my time_ or _Create time entries_ in the chat window and select the Enter key.
1. Copilot responds with _"Working on it"_ while it scans through your project assignments and then respond with suggested time entries for the current week, after removing any duplicates. To learn more about how to create resource assignments, see [Create resource assignments](../project-management/create-assignments.md).
1. Expand the section for each project to review suggested time entries. To create them, select **Create entries**.
1. Copilot responds with a confirmation of creating time entries and requests the user to **refresh** the time entry grid to view latest changes.
1. The user can now make any necessary modifications to these draft time entries before submitting them for approval.

   > [!NOTE]
   > Copilot will only suggest time entries for the **current week**, not for older weeks. It is advised to use Copilot to complete logging time entries before the end of the week.
   > The time entry grid will not refresh automatically after Copilot creates new time entries. The user must refresh the grid to view any updates.


## Generate external comments using Copilot

External (customer facing) comments are often a crucial detail added to individual time entries and are even mandatory for some users to be able to submit time entries for approval. The current process of creating and modifying these comments requires opening a new form for each time entry. This makes the process highly time consuming and can lead to inaccuracies in submitted comments. 

Copilot aims to simplify this process in two ways:
- Generating **external comment** by using details like Project, Project Task, Role, and Duration of a time entry (kept under 100 characters).
- Providing an effective interface to view and modify all comments together, without needing individual forms for each entry.

Follow these steps to generate external comments using Copilot:

1. Navigate to the **Time Entries** page.
1. Begin a chat conversation by activating the Copilot sidecar (select the Copilot icon).
1. Type _Generate comments_ or _Add external comments_ in chat window and select the Enter key.
1. Copilot responds with _"Working on it"_ while it uses details like Project, Project Task, Role, and Durations for each time entry to generate a generic, first draft of external comments.
1. Copilot responds with the generated external comments for each time entry. Each generated comment is displayed as an editable text box and can be immediately modified.
1. Once you have reviewed the generated comments and made necessary modifications to them, select **Save all**.
1. Copilot sends a confirmation of saving comments for all time entries.  **Refresh** the time entry grid to view latest changes.

To view previously saved external comments, type _View comments_ in the chat window and Copilot displays all previously saved comments without a Copilot icon. These comments can similarly be reviewed and modified before saving.
   

   > [!NOTE]
   > Copilot does not generate or over-write any pre-existing external comments that are linked to a time entry. Such comments are still displayed, but without a Copilot icon to indicate that they were not currently generated by Copilot.

  ## More Resources

- [Responsible AI FAQs for Copilot in time entry](../responsible-ai/copilot-in-time-entry-faqs.md)

> [!IMPORTANT]
Depending on where your environment is hosted, you might need to allow data movement across regions to use them. If your environment is hosted in a region that requires data movement across regions to use copilots and generative AI features, tenant administrator need to consent to the terms of use on the Move data across regions checkbox in the Power Platform admin center. [Learn more](/power-platform/admin/geographical-availability-copilot#enable-data-movement-across-regions) how data movement works across regions. 


