---
title: Set up project-level policy documents for the Approvals Agent (preview)
description: Learn how to attach time, expense, and material policy documents to individual projects so the Approvals Agent uses project-specific policies instead of the org-wide policies. 
author: abriccetti
ms.author: abriccetti
ms.date: 07/21/2026
ms.topic: how-to
ms.custom: 
 - bap-template
ms.reviewer: johnmichalak
---

# Set up project-level policy documents for the Approvals Agent (preview)

[!INCLUDE [banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

By default, the Approvals Agent classifies submitted time, expense, and material records by using the org-wide policy documents that an admin uploads on the **Time and Expense Agent** tab of the **Project Parameters** page. You can now attach policy documents to an individual project. When a project has a policy document for an entry type, the agent uses that project's policy document to classify records of that type instead of the org-wide policy document.

This capability lets you apply project-specific rules, for example, stricter receipt requirements or different not-to-exceed guidance, without changing the policies that apply to every other project in the environment.

## How project-level policy documents work

- You can attach Time, Expense, and Material policy documents to a project independently. Attach any combination of the three. You don't need to provide all of them.
- For each entry type, if the project has a policy document, the agent uses it to classify records of that type on that project.
- If the project doesn't have a policy document for an entry type, the agent falls back to the org-wide policy document for that type. For example, if you attach only a time policy document to a project, the agent uses the project's time policy for time entries, but it continues to use the organization-wide policies for that project's expense and material entries.
- If neither a project-level nor an org-wide policy document exists for an entry type, the agent doesn't classify records of that type. Learn more in [Approvals Agent overview](approvals-agent-intro.md).
- The project must still be in scope for the agent. The **Use approvals agent to review entries** flag on the project must be set to **Yes** for the agent to receive and classify that project's entries.

## Attach a policy document to a project

To attach policy documents to a project, follow these steps:

1. Open the project record that you want to add policy documents to.
1. Go to the **Approvals Agent** section of the project record.
1. Attach a policy document for each entry type that you want the project to use its own policy for **Time**, **Expense**, or **Material**. You can attach one, two, or all three.
1. Save the project record.

The agent applies the project's policy documents to entries that are submitted for classification after the policies are in place. To re-evaluate records that were already classified so that they're checked against the updated policy, select the record on the **Time entries reviewed by Agent** page, and then select **Reassign to Agent**.

> [!NOTE]
> To view and edit the policy documents that are associated with a project, a user needs **Read** and **Create** access to the **Approval Classification Policy** table in Microsoft Dataverse. These permissions are included in the out-of-the-box **Project Manager** security role. If a user has a custom security role, add these privileges to that role before the user manages project-level policy documents.

## Related information

- [Approvals Agent overview](approvals-agent-intro.md)
- [Set up policy documents for the Approvals Agent](approvals-agent-policy.md)
- [Customize data sent to the Approvals Agent](approvals-agent-customization.md)
- [Set up the Approvals Agent using the agent deployment wizard](activate-approvals-agent-wizard.md)
- [Set up the Approvals Agent as an admin](approvals-agent-admin-setup.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
