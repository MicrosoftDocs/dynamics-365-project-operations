---
title: Set up and use policy authoring for the Approvals Agent (preview)
description: Learn how to use AI to analyze time, expense, and material policies, review recommended changes, and apply revised policies for the Approvals Agent.
author: abriccetti
ms.author: abriccetti
ms.date: 12/01/2026
ms.topic: how-to
ms.custom:
 - bap-template
ms.reviewer: johnmichalak
---

# Set up and use policy authoring for the Approvals Agent (preview)

[!INCLUDE [banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

The Policy Authoring feature for the Approvals Agent in Dynamics 365 Project Operations uses AI to analyze your policy documents and recommend changes that can improve the agent's effectiveness. Use policy authoring to identify unclear, conflicting, or unsupported rules in Time, Expense, and Material policies and prepare clearer policy text.

Policy authoring is advisory. It doesn't approve entries, change approval decisions, or automatically write policy documents to Microsoft Dataverse. You review the AI-generated recommendations and apply the revised policy through the existing policy document setup. The Approvals Agent can also use policies that you write without policy authoring.

## Before you begin

Policy authoring is available in Project Operations version 4.172.x.x. An admin user must publish the agent in Microsoft Copilot Studio and share it with the end users who need access. Users can access it in Microsoft Teams or directly in Copilot Studio.

Review the Copilot Studio prerequisites for publishing and sharing, including authentication and user access, in [Publish an agent](/microsoft-copilot-studio/agents-experience/publication-publish-agent) and [Share agents with other users and makers](/microsoft-copilot-studio/agents-experience/authoring-share-agent).

Prepare the policy document or text that you want to review. You can upload a document or paste its contents into the agent chat. Keep a separate policy for each entry type: Time, Expense, or Material. Write each policy as a numbered list of rules and identify the entry type at the beginning.

Review the data that the Approvals Agent receives for that entry type in [Set up policy documents for the Approvals Agent](approvals-agent-policy.md#data-for-the-approvals-agent). These *data signals* determine which checks the agent can perform. Some signals are available only when specific conditions are met, so review the **Conditions for inclusion** column as well.

Before you apply a revised policy to entries, an admin must configure the existing Approvals Agent. Learn more in [Set up the Approvals Agent using the agent deployment wizard](activate-approvals-agent-wizard.md) and [Approvals Agent overview](approvals-agent-intro.md). Those articles describe setup for entry classification. Publishing and sharing the agent for policy authoring is a separate task, described in the following section.

## Set up and access policy authoring

As an admin user, publish the agent and share it with the users who need to review policies:

1. Sign in to [Microsoft Copilot Studio](https://copilotstudio.microsoft.com) as an admin user and select the Project Operations environment.
1. Open the **Policy Authoring** agent. In Copilot Studio, it appears as **Policy Authoring(Prod Preview)**. The **(Prod Preview)** suffix indicates that the feature is a production-ready preview.
1. Select **Publish**, review the publishing details, and configure Microsoft Teams as a channel if users will access the agent there. Confirm publication and wait for it to complete. Learn more in [Publish an agent](/microsoft-copilot-studio/agents-experience/publication-publish-agent).
1. Share the published agent with the intended end users. Grant access to use the agent, not permission to edit its configuration. Follow the access prerequisites and sharing instructions in [Share agents with other users and makers](/microsoft-copilot-studio/agents-experience/authoring-share-agent).
1. Provide users with access to the agent in Teams or Copilot Studio, and verify that an intended end user can open it and submit policy text.

To review a policy in Teams, open the agent shared by your admin. To review it directly in Copilot Studio, open the shared agent and use its preview chat. Sharing access to policy authoring doesn't grant permission to change the policy documents in Project Operations.

## Submit a policy for analysis

To submit a policy for analysis, follow these steps:

1. Open policy authoring after you complete the setup.
1. Upload the policy document or paste its contents into the agent chat, and ask for a review. For example, enter "Review this Expense policy for use by the Approvals Agent," and provide the document or numbered rules.
1. Review the detected entry type. If the policy type is ambiguous, clarify whether it applies to Time, Expense, or Material entries.
1. Answer any questions about unclear thresholds, conflicting rules, or information that the Approvals Agent doesn't receive. Use the organization's intended policy requirements rather than accepting an inferred value.
1. Review the analysis and ask for further changes as needed.

## Review the recommended changes

Policy authoring checks the policy criteria against the Approvals Agent's data signals. The response includes an issues summary, a suggested changes table, and revised policy text. If any criteria are unsupported, it asks for your confirmation before providing the revised policy.

### Understand the issues summary

The summary identifies the entry type and groups the criteria into three categories:

| Category | Meaning | What to review |
| --- | --- | --- |
| A - Supported and clear | The criterion can be evaluated as written against available data signals. | Confirm that it still reflects the intended business requirement. |
| B - Supported but unclear | The criterion uses supported data, but its wording needs clarification. | Check that the suggested wording preserves its thresholds, comparisons, and logic. |
| C - Unsupported | The criterion depends on unavailable data or is too vague to evaluate. | Resolve the missing information or decide with the policy owner how to handle the requirement before accepting a revised policy. |

For example, "Flag expenses when the total cost is high" doesn't define a threshold. The policy owner must supply the intended amount and comparison. Policy authoring shouldn't decide what "high" means for your organization.

### Resolve unsupported or conflicting criteria

For each unsupported criterion, review the explanation and decide how to proceed with the responsible policy owner. Clarify vague wording or use available data only when doing so preserves the business requirement. If a requirement can't be evaluated with the available data, arrange human review rather than silently dropping it from the policy.

Policy authoring can't create missing data. Confirming a proposed change doesn't make an unsupported criterion enforceable. Don't remove or weaken a business control just to obtain a revised policy.

If rules contradict each other, clarify which rule takes precedence. Continue the conversation until the proposed policy reflects that decision. Check for contradictions yourself even if the analysis doesn't flag them.

### Check the revised policy

Compare the revised policy with the original, rule by rule. Verify that:

- Every business requirement is included, including any requirement that needs human review.
- Amounts, quantities, units, names, thresholds, and comparison operators retain their intended meaning.
- Conditions joined by AND or OR have explicit grouping and preserve the original logic.
- The policy applies to one entry type and doesn't depend on data that isn't available.

Review all AI-generated text before applying it. Policy authoring can miss issues or recommend wording that changes the meaning of a rule. Request corrections and review the result again before copying the final text.

## Apply and test the revised policy

Policy authoring doesn't save or upload the revised policy for you. After the policy owner reviews and accepts it, copy the text into the policy document for the relevant entry type.

To apply and test the revised policy, follow these steps:

1. Choose where the policy applies. For an org-wide policy, upload the revised document on the **Time and Expense Agent** tab of the **Project Parameters** page. For a project-specific policy, attach the revised document in the **Approvals Agent** section of the project record. Learn more in [Set up project-level policy documents for the Approvals Agent](approvals-agent-project-policy.md).
1. Confirm which policy the agent will use. A project's policy overrides the org-wide policy for the same entry type. The project must also have **Use approvals agent to review entries** set to **Yes**.
1. Use **Classify** mode while you test the revised policy. Review representative entries that should be **Ready for approval** and entries that should be **Needs review**, including boundary cases for thresholds and records with missing conditional data.
1. For records that were already classified and need another review, select the record on the **Time entries reviewed by Agent** page, and then select **Reassign to Agent**. Updated policies apply to entries submitted for classification after the policies are in place.
1. Compare the classifications and explanations with the expected outcomes. If they don't match your business requirements, revise the policy and repeat the review and testing.

> [!IMPORTANT]
> Test thoroughly before using **Classify and auto approve** mode. Accepting a policy authoring recommendation isn't evidence that the Approvals Agent will classify every entry correctly.

Learn more about classification modes and reevaluation in [Approvals Agent overview](approvals-agent-intro.md).

## Tips and limitations

- Use numbered rules, one entry type per policy, explicit thresholds and units, and clearly grouped conditions.
- Check conditional data availability. A supported signal isn't necessarily present on every entry.
- Treat the analysis as advice, not a guarantee of policy completeness or classification accuracy.
- Keep requests focused on approval policy review. Policy authoring doesn't handle unrelated tasks.
- Avoid criteria based on sensitive or protected personal attributes. Policy authoring might decline to rewrite such criteria.

Follow your organization's data policies when submitting policy text. Learn more about platform controls in [Security and governance in Copilot Studio](/microsoft-copilot-studio/security-and-governance).

## Related information

- [Approvals Agent overview](approvals-agent-intro.md)
- [Set up policy documents for the Approvals Agent](approvals-agent-policy.md)
- [Set up project-level policy documents for the Approvals Agent](approvals-agent-project-policy.md)
- [Responsible AI FAQ for the Approvals feature of the Time and Expense Agent](../responsible-ai/approvals-agent-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
