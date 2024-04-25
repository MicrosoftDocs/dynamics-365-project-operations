---
# required metadata

title: Use Copilot in time entry (preview)
description: This article explains how team members can use Copilot to complete their time entry each week.
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

Copilot in time entry is designed to simplify the time entry experience and take away the drudgery of navigating endless forms, drop-down lists that currently make this process time consuming. This gives back time to project team members that they can instead use for high leverage tasks.

This Copilot feature currently has two primary capabilities:

- Log my time
- Generate external comments

## Enable or disable the Copilot in time entry feature

This feature is currently in preview state and **can only be accessed on environments hosted in the "NAM" Azure region**. Please confirm with your tenant admin before trying to access this feature.

To enable Copilot in time entry, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
2. Ensure that you're using Project Operations version _4.103.0.X_ or later. This feature is not available before this version.
3. On the left navigation, change the area to **Settings**.
4. In the **General** section, select **Parameters**.
5. A list of organization units should appear. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
6. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
7. Select **Enable Copilot in time entry** and then click **OK**.

   > [!NOTE]
   > To disable Copilot in time entry, follow the enable steps and select **Disable Copilot in time entry** in step 7.

## Interactive Copilot chat experience

Both of the Copilot capabilities in this feature can only be accessed by using the interactive Copilot chat experience. Since this Copilot chat experience is currently in preview state, it may not be enabled on your environment.

- Select the Copilot icon from the top menu bar, just next to the user icon.
- This makes the Copilot sidecar visible along with a message stating "Get started with Copilot by typing your request in chat."
- To collapse this sidecar, similarly click on the Copilot icon once again.

   > [!NOTE]
   > Please work with your system administrator and complete steps to [enable Copilot chat for your environment](https://learn.microsoft.com/power-apps/maker/model-driven-apps/add-ai-copilot#enable-copilot-for-model-driven-apps-feature-for-your-environment) if the Copilot icon is not visible. [test link V2](/powerapps-docs/maker/model-driven-apps/add-ai-copilot)

## Log time using Copilot

This capability takes a user's existing project task assignments for the current week and suggests draft time entries that can be created based on those assignments. Copilot will ensure there is no duplication of entries when the user has pre-existing time entries in that week.

Follow these steps to log time using Copilot:

1. Navigate to the **Time Entries** page.
2. Activate the Copilot sidecar (click Copilot icon) to begin a chat conversation.
3. Type _Log my time_ or _Create time entries_ in the chat window and hit enter.
4. Copilot will respond with _"Working on it"_, while it scans through your project assignments and then respond with suggested time entries for the current week, after removing any duplicates. Learn more about how to create resource assignments [here](../project-management/create-assignments.md).
5. Expand the section for each project tp review suggested time entries. To create them, select **Create entries**.
6. Copilot responds with a confirmation of creating time entries and requests the user to **refresh** the time entry grid to view latest changes.
7. The user can now make any necessary modifications to these draft time entries before submitting them for approval.

   > [!NOTE]
   > Copilot will only suggest time entries for the **current week**, not for older weeks. It is advised to use Copilot to complete logging time entries before the end of the week.
   > The time entry grid will not refresh automatically after Copilot creates new time entries. The user must refresh the grid to view any updates.


## Generate external comments using Copilot

External (customer facing) comments are often a crucial detail added to individual time entries and are even mandatory for some users to be able to submit time entries for approval. The current process of creating and modifying these comments requires opening a new form for each time entry. This makes the process highly time consuming and can lead to inaccuracies in submitted comments. 

Copilot aims to simplify this process in two ways:
- Generating **external comment** by using details like Project, Project Task, Role and Duration of a time entry (kept under 100 characters).
- Providing an effective interface to view and modify all comments together, without needing individual forms for each entry.

Follow these steps to generate external comments using Copilot:

1. Navigate to the **Time Entries** page.
2. Activate the Copilot sidecar (click Copilot icon) to begin a chat conversation.
3. Type _Generate comments_ or _Add external comments_ in chat window and hit Enter.
4. Copilot will respond with _"Working on it"_ while it uses details like Project, Project Task, Role and Durations for each time entry to generate a generic, first draft of external comments that can be linked to each time entry.
5. Copilot responds with the generated external comments for each time entry. Each generated comment is displayed as an editable text box and can be immediately modified.
6. Once you have reviewed the generated comments and made necessary modifications to them, click **Save all**.
7. Copilot will send a confirmation of saving comments for all time entries.  **Refresh** the time entry grid to view latest changes.

To view previously saved external comments, type _View comments_ in the chat window and Copilot will display all previously saved comments without a Copilot icon. These can similarly be reviewed and modified before saving.
   

   > [!NOTE]
   > Copilot does not generate or over-write any pre-existing external comments that are linked to a time entry. Such comments are still displayed, but without a Copilot icon to indicate that they were not currently generated by Copilot.

## Additional Resources

- [Responsible AI FAQs for Copilot in time entry](../responsible-ai/copilot-in-time-entry-faqs.md)

> [!IMPORTANT]
Depending on where your environment is hosted, you might need to allow data movement across regions to use them. If your environment is hosted in a region that requires data movement across regions to use copilots and generative AI features, tenant administrator need to consent to the terms of use on the Move data across regions checkbox in the Power Platform admin center. [Learn more](/power-platform/admin/geographical-availability-copilot#enable-data-movement-across-regions) how data movement works across regions. 


