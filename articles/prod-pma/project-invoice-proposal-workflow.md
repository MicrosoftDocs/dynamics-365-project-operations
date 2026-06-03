---
title: Project invoice proposal workflows
description: Learn how to enable optional workflows for approval of customer invoice proposals
author: ryansandness
ms.author: ryansandness
ms.date: 06/03/2026
ms.topic: how-to
ms.custom:
  - bap-template
ms.reviewer: johnmichalak
---

# Project invoice proposal workflows

_**Applies To:** Project Operations for manufacturing-based scenarios_

[!include [banner](../includes/banner.md)]

The project invoice proposal workflow lets organizations require formal approval before a project invoice proposal can be posted as a customer invoice. This process provides a consistent, auditable way to review invoice amounts, project details, and billing accuracy before the invoice is sent to the customer.

When you enable the workflow, a project accountant creates an invoice proposal and submits it for approval. The workflow routes the proposal to the configured approvers, such as a Project Manager or finance controller, who can approve, reject, or request changes. You can post the invoice proposal only after the workflow is fully approved.

## Create a project invoice proposal workflow

To create a project invoice proposal workflow, follow these steps:

1. Go to **Project management and accounting** > **Setup** > **Project management and accounting workflows**.
1. Select **New**.
1. In the list of workflow types, select **Review project invoice proposals**.
1. The workflow editor opens after authenticating. Include an **Invoice proposal approval** element onto the canvas and connect it to the **Start** node.
1. Include a **Post invoice** node between the **Invoice proposal approval** and **End** nodes with everything connected.
1. Configure any properties within the two workflow elements as required.
1. Select **Save and close**.
1. When prompted, activate the workflow to make it available for use.

## Enable the project invoice proposal workflow

You must enable the workflow for each legal entity.

To enable the project invoice proposal workflow, follow these steps:

1. Go to Project management and accounting > Setup > Project management and accounting parameters.
1. Select the **Invoice** tab.
1. Enable the option to **Enable processing invoice proposals in workflow**.

## Recover an invoice proposal stuck in a failed workflow

If the workflow engine encounters an error, such as a misconfiguration or a missing approver assignment, the invoice proposal can get stuck in **Error** or **Unrecoverable** status. In this state, the proposal is locked and the project accountant can't edit, delete, or resubmit it.

Starting with version 10.0.48, users with the appropriate security role can reset a stuck invoice proposal back to Draft status.

To recover an invoice proposal stuck in a failed workflow, follow these steps:

1. Go to **Project management and accounting** > **Periodic** > **Project invoices** > **Reset invoice proposal workflow status**. You can see this menu item only if workflow is enabled in the legal entity.
1. The page lists all invoice proposals in the current legal entity whose workflow is in an Error or Unrecoverable state.
1. Select one or more invoice proposals to reset.
1. Select **Reset to draft** and confirm.

The selected proposals return to Draft status. Workflow history is preserved for audit purposes. Before resubmitting, investigate and resolve the underlying cause of the failure to prevent it from recurring.

## Related articles

- [Manage project invoice proposals](/dynamics365/project-operations/prod-pma/project-invoicing)
- [Workflow system overview](/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system)
- [Configure approval processes in a workflow](/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow)
- [Actions in workflow approval processes](/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
